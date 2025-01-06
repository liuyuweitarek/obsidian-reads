# Paper Reading WorkFlow

This workflow is inspired by [Wang's Obsidian share](https://youtu.be/dwiCE7mu3kY?si=Ja2zn0NESeUpW454), where notes are classified into four types: red, blue, yellow, and orange. 

It integrates Zotero and Obsidian seamlessly, leveraging plugins like Zotero Integration, DataviewJS, Templater, and Git to streamline note-taking and management. 

## **Philosophy**

🟥**Red Note** (Core/Raw note)
- Annotate BibTeX / Paper source(use [[Paper|Template]])
- Record paragraph understanding using [[Taxonomy#Meaning of Highlight Colors|color block]] for annotation.
- Consider creating academic tags in Zotero.(refer to [[Taxonomy#Scholar Tags|scholar tags named rule]]). 

🟦**Blue Note** (Paragraph note)
- Record understanding of paragraphs.
- Consider creating academic tags in Obsidian (refer to [[Taxonomy#Scholar Tags|scholar tags named rule]]).
	**Since blue notes are in Obsidian, carefully name the tags based on your field understanding to ensure retrievability.**
- (Optional) Registered concept / related note / Yellow Note

🟨**Yellow Note(Index note for Registered concept)**
- Merge reliable sources to understand the various perspectives on domains or terminology.

🟧**Orange Note**(Chewing note)
- Brainstorm research topics.
- Explore areas for advancement.
- Answer previously unresolved questions.
- Capture highly insightful ideas.

## **Empirical Steps**

**Step 1. Download papers through Zotero Connector**.
    
  - Zotero collection folder structure
    ```text
    My Library
      | - Books
      | - (Based on Project/Purpose, e.g., ExplorePhD)
      | - Learning&Implementation
    ```

**Step 2. Read papers in Zotero.**
1. Taking color-coded note in Zotero based on [[Taxonomy#Meaning of Highlight Colors]].
2. Build scholar tags. (refer to [[Taxonomy#Scholar Tags]]). 
3. Create special tags

**Step 3. Red Note: Import notes from Zotero to Obsidian.**
	
**(Before importing, make sure your Zotero opened.)**
	
1. `Ctrl + P > type "zotero" > select "Zotero: Import Paper" > type the paper's title} in Zotero bar.`
  Noted that:
	- The "import bar" <mark class="hltr-cyan">allows selecting multiple references simultaneously.</mark>
    - Notes are initially placed in the `Staged` folder.

2. Filled in properties:
    - **Purpose:** Related thoughts or notes driving you to read this paper.
    - **Read Status:**
      - 🟦Browsing: Still reading and building the red note.
      - 🟧Processing: Starting to build blue or index notes.
    - Paper Properties
    - Created/Updated Date
    - Scholar Tags

**Step 4. Blue Note: Refine Note Granularity and Define Scholar Tags**

1. `Ctrl + P > type "quick" > Quick Add: Add Blue Note > type filename`.
    - Filename be like `{{@citekey}}.chapter-section.paragraph`, e.g. `@liuExamplepaper2025.1.2` or `@liuExamplepaper2025.2-1.2`
    - Links are appended to current file's cursor.(usually is in `Red note#"Paragraph Index`)

2. Fill in note propertyies.
    - **BibTeX:** copy from origin paper
    - `content::{source_paper_content}`
    - `note::{your_note_content}`
    - Ensure scholar tag is searchable.

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
 

**Step 6. Yellow Note: Build Indexing Note**

1. `Ctrl + P > type "quick" > Quick Add: Add Yellow Note > type filename`
    - Filename would be the concept or the question, e.g., `Social Mindfulness` or `Is having more model parameters always better`.
    - Create the tag, e.g., `IndexOf-Social-Mindfulness` or `IndexOf-is-having-more-model-parameters-always-better`.

2. For filtering notes: 
    - Use [DataviewJS](https://blacksmithgu.github.io/obsidian-dataview/api/code-reference/#dvparagraphtext) queries.
        E.g., Query  "🟦Piece Note" and target scholar tag.
        ```dataviewjs
        const pages = dv.pages('"Reads/Papers" and #Your_Tag_Name');
        
        for(var i = 0; i < pages.length; i++){
          dv.header(2, pages[i].file.link);
         	dv.paragraph(pages[i].content);
         	dv.paragraph(pages[i].note);
        } 
        ```
    - View by graph, and search by scholar tag.

**Step 7. Orange Note: Build Chewing Note**

1. Follow similar steps as Yellow Notes.

2. Purpose: Brainstorm insights and research directions.

#workflow 

#paper-reading