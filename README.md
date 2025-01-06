# Obsidian Reads

This is part of my note-taking system, integrated with [Obsidian](https://obsidian.md/) and [Zotero](https://www.zotero.org/).

Zotero focuses on "recording initial readings", while Obsidian emphasizes "secondary digestion and understanding" as well as "linking concepts".

TODO
- [ ] Update taxonomy link to github link
- [ ] usgae notes 
## Installation

1. Open an new private repository, which is **suggested** for the privacy on Github.
    
    In [this repository](https://github.com/liuyuweitarek/obsidian-reads), click on the **"__Use this template__"** button to create your own repository.

2. Clone your repository to your local machine.

3. Install the [Obsidian](https://obsidian.md/) and [Zotero](https://www.zotero.org/).

4. Install the Zotero plugins into Zotero.	
  
   - Open Zotero, and go to `Tools > Add-ons`. 
  
   - Drag the files in the folder `System/Zotero/plugin_sources` into Zotero Add-ons panel.
   
	**Note: Some plugin versions are not compatible with each other. To ensure system stability and reproducibility, I have stored the source files in the directory `System/Zotero/plugin_sources`.**  My Zotero version is `6.0.36`.
    
    Below are the plugins used, along with their versions and sources			
	
  	| Plugin | Version | Source Link |
  	| ------------------------ | ------- | ----------- |
  	| Night for Zotero         | `0.4.23`  | [Source](https://github.com/tefkah/zotero-night)      |
  	| Better BibTex for Zotero | `6.7.140` | [Source](https://retorque.re/zotero-better-bibtex/)     |
  	| ZotFile | `5.1.2`| [Source](https://zotfile.com/) |
  	| Zotero PDF Translate | `1.0.23` | [Source](https://github.com/windingwind/zotero-pdf-translate#readme)|

	Besides, here are few more tips for system stability and debugging:
	
      1. It is recommended to **disable Zotero's automatic add-on updates** to avoid unexpected system failures.  
      
          Go to `Tools > Add-ons > Update Add-ons` and uncheck `Check for updates automatically`.
  
      2. If certain Zotero features are not functioning, check the source link above and go to "GitHub Releases" for other versions or review "GitHub Issues" for debugging.

5. Install "[Zotero Connector](https://www.zotero.org/download/connectors)" to your browser.   
6. **(Optional)** Configure github information for online backup.
7. **(Optional)** Configure zotero information for backup literatures.
## Workflows

### Paper Input Flow

Based on [Wang's obsidian share](https://youtu.be/dwiCE7mu3kY?si=Ja2zn0NESeUpW454), I also organize literature note into red/blue/yellow/orange notes.

**Philosophy**

🟥**Red Note** (Core/Raw note)
- Annotate BibTeX / Paper source([[Paper|Template]] will do this)
- Record paragraph understanding (using [[Taxonomy#Meaning of Highlight Colors|color block]] for annotation).
- Consider creating academic tags in Zotero.(read [[Taxonomy#Scholar Tags|scholar tags named rule]]). Zotero also provide tag column for filled in. 

🟦**Blue Note (Paragraph note)**
- Record understanding of paragraph
- Consider creating academic tags in Obsidian.(read  [[Taxonomy#Scholar Tags|scholar tags named rule]]).
	Due to blue notes have been in obsidian, you should seriously name the tag based on your understanding of the field. Make sure these notes are retrievable.
- (Optional) Registered concept / related note / Yellow Note

🟨**Yellow Note(Index note for Registered concept)**
- Merge reliable sources and understand the various perspectives on domains or terminology.

🟧**Orange Note**(Chewing note)
- Come up to mind research topics
- Areas for advancement
- Answers to previously unanswerable questions
- Highly insightful

**Empirical Steps**

**Step 1. Download papers through Zotero Connector**
    
  - Zotero collection folder structure
    ```text
    My Library
      | - Books
      | - (Based on Project/Purpose, e.g. ExplorePhD)
      | - Learning&Implementation
    ```

**Step 2. Reading Papers in Zotero**
1. Taking color note in Zotero based on [[Taxonomy#Meaning of Highlight Colors]].
2. Build scholar tags. [[Taxonomy#Scholar Tags]] 
3. Build special tags

**Step 3. (Red Note) Import the Note from Zotero to Obsidian**
	
(Make sure your Zotero is opened.)
	
1. `Ctrl + P > type "zotero" > select "Zotero: Import Paper" > Type {Paper's Title} in Zotero Bar`
  Noted that:
    1. Zotero integration will pop out an "import bar", you <mark class="hltr-cyan">can select more than one references</mark> at the same time.
    2. Note will be put into the  `Staged` folder first.

2. Filled in properties
    - Purpose: related thought/note taht drive me to read this paper.
    - Read Status
      - 🟦Browsing: Means that I still watching and build red note
      - 🟧Processing: Means that I start to build blue note or index note
    - Paper Property
    - Created/Updated Date
    - Scholar Tags(scholar)
	

**Step 4. (Blue Note) Modify Note Granularity / Define Scholar Tags**

1. `Ctrl + P > type "quick" > Quick Add: Add Blue Note > type filename`
    - Filename be like `{{@citekey}}.chapter-section.paragraph`, e.g. `@liuExamplepaper2025.1.2` or `@liuExamplepaper2025.2-1.2`
    - This will append link into current file's cursor.(usually is in `Red note#"Paragraph Index`)

2. Fill in note property
    - BibTeX: copy from origin paper
    - `content::{source_paper_content}`
    - `note::{your_note_content}`
    - Make sure your scholar tag is searchable!)

3. Registed(link yellow note here)

**Step 5. View Note Relationship**

1. `Ctrl + Alt + G > Graph view: Open Graph view`
    - Filter: 
        search bar: `["source_type":📜Paper] - path:"System/Templates"` 
        - [ ] Tags
        - [ ] Attachments
        - [x] Existing files only
        - [x] Orphans
    - Groups
      
        ["paper_property":🟥Core Note]
        
        ["paper_property":🟦Piece Note]
        
        ["paper_property":🟨Index Note]
        
        ["paper_property":🟧Chewing Note]
 

**Step 6. (Yellow Note) Build Indexing Note**

1. `Ctrl + P > type "quick" > Quick Add: Add Yellow Note > type filename`
    - Filename would be the concept or the question. e.g. `Social Mindfulness` or `Is having more model parameters always better`
    - Build Tag. e.g. `IndexOf-Social-Mindfulness` or `IndexOf-is-having-more-model-parameters-always-better`

2. Fast ways for filtering notes: 
    - Query  "🟦Piece Note" with scholar tag through [Dataviewjs](https://blacksmithgu.github.io/obsidian-dataview/api/code-reference/#dvparagraphtext) plugin query.
        e.g. 
        ```dataviewjs
        const pages = dv.pages('"Reads/Papers" and #Your_Tag_Name');
        
        for(var i = 0; i < pages.length; i++){
          dv.header(2, pages[i].file.link);
         	dv.paragraph(pages[i].content);
         	dv.paragraph(pages[i].note);
        } 
        ```
    - View by graph, also search by scholar tag.

**Step 7. (Orange Note) Build Chewing Note**(Orange Note)

1. `Ctrl + P > type "quick" > Quick Add: Add Orange Note > type filename`
    - Filename would be the concept or the question. e.g. `Social Mindfulness` or `Is having more model parameters always better`
    - Build Tag. e.g. `ChewingOf-Social-Mindfulness` or `ChewingOf-is-having-more-model-parameters-always-better`

2. Purpose
    - Come up to mind research topics
    - Areas for advancement
    - Answers to previously unanswerable questions
    - Highly insightful

### Build your own Input Flow

Take **Meeting Notes** for example and apply to __private-sensitive situations__.

## Features

This section lists the enabled features in current project, their usage, suggested hotkeys, and purposes.

Since not every feature suit everyone's needs, or you might have a better way to achieve the goal, PRs are always welcome, feel free to select and enable only the features you need and focus on learning those.

**Obsidian Features**

- [x] [Backup with Github](./System/Documents/Backup%20with%20Github.md)

- [x] [Import Literature from Zotero](./System/Documents/Import%20Literature%20from%20Zotero.md)

- [ ] [Command Palette commands for Adding Template Note]()

- [ ] Note Properties Management

- [ ] Query notes based on note properties  

**Zotero Features** 

- [x] [Transcript Underlined Content](./System/Documents/Transcript%20underlined%20content.md) 

- [x] [Add New Citation Format](./System/Documents/Add%20New%20Citation%20Format.md)

## Related Plugins

**These obsidian plugins have already been installed once you start using this system.**

Just in case some Obsidian features are not working, or you want to add your own plugin to build your own system, I list all obsidian plugins used in this project here and features they provide.

- [Command Palette commands for Adding Template Note]()
	1. QuickAdd
	2. Templater
- [Import Literature from Zotero](./System/Documents/Import%20Literature%20from%20Zotero.md)
	1. Zotero Integration 
	2. QuickAdd
	3. Templater
	
- [Note Properties Management]()
	1. Metadata Menu
- [Query notes based on note properties]()
	1. Dataview
	2. Metadata Menu
- [AI Helper]()
	1. Text Generator

- [Backup with Github]()
	1. [Git](https://github.com/Vinzent03/obsidian-git) - `2.31.1`








