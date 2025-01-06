---
fileClass: Overall, Read, PaperNote
purpose: 
read_status: ⬛ Not started
source_type: 📜Papers
paper_property: 
created:
updated:
tags: {% if tags.length > 0 -%}{%- for t in tags -%}{%- set replaced_tag = t.tag | lower | replace(" ", "-") -%}{{ "\n  - " ~ replaced_tag }}{%- endfor %}{%- endif %} 
---
*Imported: {{importDate | format("YYYY-MM-DD HH:mm")}}*

> [!paper_metadata]+ Metadata
> **Title**:: {{title}}  
{% for type, creators in creators | groupby("creatorType") -%}
{%- for creator in creators -%}
> **{{"First" if loop.first}}{{type | capitalize}}**::
{%- if creator.name %} {{creator.name}}  
{%- else %} {{creator.lastName}}, {{creator.firstName}}  
{%- endif %}  
{% endfor %}  
{%- endfor %}> **Year**:: {{date | format("YYYY")}}   
> **Citekey**:: {{citekey}} {%- if itemType %}  
> **itemType**:: {{itemType}}{%- endif %}{%- if itemType == "journalArticle" %}  
> **Journal**:: *{{publicationTitle}}* {%- endif %}{%- if volume %}  
> **Volume**:: {{volume}} {%- endif %}{%- if issue %}  
> **Issue**:: {{issue}} {%- endif %}{%- if itemType == "bookSection" %}  
> **Book**:: {{publicationTitle}} {%- endif %}{%- if publisher %}  
> **Publisher**:: {{publisher}} {%- endif %}{%- if place %}  
> **Location**:: {{place}} {%- endif %}{%- if pages %}   
> **Pages**:: {{pages}} {%- endif %}{%- if DOI %}  
> **DOI**:: {{DOI}} {%- endif %}{%- if ISBN %}  
> **ISBN**:: {{ISBN}} {%- endif %}

> [!paper_citation]- Citation
> **BibTeX**:: {{bibliography}}

> [!paper_link]+ Source
> **PaperSource**:: {% for attachment in attachments | filterby("path", "endswith", ".pdf") %}
> [{{attachment.title}}](file://{{attachment.path | replace(" ", "%20")}})  {% endfor %}

> [!paper_synthesis]- Synthesis
> **Contribution**:: 
> 
> **Related**:: {% for relation in relations | selectattr("citekey") %} [[@{{relation.citekey}}]]{%- if not loop.last -%}, {%- endif -%} {% endfor %}

> [!paper_abstract]- Abstract
> {% if abstractNote %}
> {{abstractNote}}
> {% endif %}

---
## Paragraph Index
{% persist "markdownNotes" %}
{% if markdownNotes %}
{{markdownNotes}}
{% endif %}
{% endpersist %}

---
## Reading notes
{% persist "annotations" %}

{%-
    set zoteroColors = {
	"#2ea8e5": "blue",
        "#a3fc77": "green",
        "#a28ae5": "purple",
        "#ff6666": "red",
        "#ffd400": "yellow",
        "#f19837": "orange",
        "#aaaaaa": "gray",
        "#e56eee": "magenta"
    }
-%}

{%-
   set colorHeading = {
	    "yellow": "💡 Assumptions, Questions, Goals, Problems 🤯",
	    "orange": "📙 Background information, Prerequisites",
	    "green": "👽 Interesting point, Facts, Examples 🤗",
		"blue": "💎 Main findings, Results, Conclusions 🧐",	
		"purple": "💷Experimental details or Methods 👨‍🔬",
		"magenta": "🎆 Important references, literature to read 📄",
		"red": "🚨 Disagree with author 🤨",
		"gray": "✒️ Vocabulary, Names, Dates, Definitions 📌"
   }
-%}

{%- macro calloutHeader(type) -%}
    {%- switch type -%}
        {%- case "highlight" -%}
        Quote
        {%- case "image" -%}
        Image
        {%- default -%}
        Note
    {%- endswitch -%}
{%- endmacro %}

{%- set newAnnot = [] -%}
{%- set newAnnotations = [] -%}
{%- set annotations = annotations | filterby("date", "dateafter", lastImportDate) %}

{% if annotations.length > 0 %}

{%- for annot in annotations -%}

    {%- if annot.color in zoteroColors -%}
        {%- set customColor = zoteroColors[annot.color] -%}
    {%- elif annot.colorCategory|lower in colorHeading -%}
    	{%- set customColor = annot.colorCategory|lower -%}
    {%- else -%}
	    {%- set customColor = "other" -%}
    {%- endif -%}

    {%- set newAnnotations = (newAnnotations.push({"annotation": annot, "customColor": customColor}), newAnnotations) -%}

{%- endfor -%}

{#- INSERT ANNOTATIONS -#}
{#- Loops through each of the available colors and only inserts matching annotations -#}
{#- This is a workaround for inserting categories in a predefined order (instead of using groupby & the order in which they appear in the PDF) -#}

{%- for color, heading in colorHeading -%}
{%- for entry in newAnnotations | filterby ("customColor", "startswith", color) -%}
{%- set annot = entry.annotation -%}

{%- if entry and loop.first %}

### {{colorHeading[color]}}
{%- endif %}

> [!paper_highlight{{"_" + color if color != "other"}}]+ {{calloutHeader(annot.type)}} ([page. {{annot.pageLabel}}](zotero://open-pdf/library/items/{{annot.attachment.itemKey}}?page={{annot.pageLabel}}&annotation={{annot.id}}))

{%- if annot.annotatedText %}
{{annot.annotatedText}} 

{% if annot.hashTags %}{{annot.hashTags}}{% endif -%}
{%- endif %}
{%- if annot.imageRelativePath %}
![[{{annot.imageRelativePath}}]]
{% if annot.hashTags %}{{annot.hashTags}}{% endif -%}
{%- endif %}
{%- if annot.ocrText %}
{{annot.ocrText}}
{%- endif %}
{%- if annot.comment %}
{{annot.comment}}
{%- endif -%}
{%- endfor -%}
{%- endfor -%}
{% endif %}
{% endpersist %}