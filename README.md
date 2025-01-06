# Obsidian Reads

This is part of my note-taking system, integrated with [Obsidian](https://obsidian.md/) and [Zotero](https://www.zotero.org/).

Zotero focuses on "recording initial readings", while Obsidian emphasizes "secondary digestion and understanding" as well as "linking concepts".
## Installation

1. Open a new private repository, which is **recommended** for privacy on GitHub.
    
    In [this repository](https://github.com/liuyuweitarek/obsidian-reads), click on the **"__Use this template__"** button to create your own repository.

2. Clone your repository to your local machine.

3. Install [Obsidian](https://obsidian.md/) and [Zotero](https://www.zotero.org/).

4. Install the Zotero plugins into Zotero.	
  
   - Open Zotero, and go to `Tools > Add-ons`. 
  
   - Drag the files in the `System/Zotero/plugin_sources` into the Zotero Add-ons panel.
   
	**Note: Some plugin versions are not compatible with each other. To ensure system stability and reproducibility, I have stored the source files in the directory `System/Zotero/plugin_sources`.**  My Zotero version is `6.0.36`.
    
    Below are the plugins used, along with their versions and sources			
	
  	| Plugin | Version | Source Link |
  	| ------------------------ | ------- | ----------- |
  	| Night for Zotero         | `0.4.23`  | [Source](https://github.com/tefkah/zotero-night)      |
  	| Better BibTex for Zotero | `6.7.140` | [Source](https://retorque.re/zotero-better-bibtex/)     |
  	| ZotFile | `5.1.2`| [Source](https://zotfile.com/) |
  	| Zotero PDF Translate | `1.0.23` | [Source](https://github.com/windingwind/zotero-pdf-translate#readme)|

	**Tips for system stability and debugging:**
	
      1. **Disable Zotero's automatic add-on updates** to avoid unexpected system failures. 
      
          Go to `Tools > Add-ons > Update Add-ons` and uncheck `Check for updates automatically`.
  
      2. If certain Zotero features are not functioning, check the source links above and explore the "GitHub Releases" for other versions or review "GitHub Issues" for debugging.

5. Install the "[Zotero Connector](https://www.zotero.org/download/connectors)" for your browser.   
6. **(Optional)** Configure github information for online backup. 
7. **(Optional)** Configure zotero information for backing up literature.
## Workflows

Please see the [Paper Reading WorkFlow](./System/Documents/Workflows/Paper%20Reading%20WorkFlow.md).

If you handle other knowledge sources, such as meeting discussions, and need to ensure privacy, refer to the guide: [Creating Notes for Knowledge Inputs with Privacy Requirements.md]().
## Features

This section outlines the features available in the current project, including their usage, recommended hotkeys, and purposes.

Not all features will suit every user's needs, and you may have alternative approaches to achieve the same goals. Pull requests are always welcome. Feel free to enable only the features you require and focus on learning those.

**Obsidian Features**

- [x] [Syncing Notes with GitHub](./System/Documents/Features/Syncing%20Notes%20with%20GitHub.md)

- [ ] [Import Literature from Zotero]()

- [ ] [Command Palette Commands for Adding Template Note]()

- [ ] [Note Properties Management]()

- [ ] [Query Notes Based on Note Properties]()  

**Zotero Features** 

- [ ] [Transcript Underlined Content](./System/Documents/Transcript%20underlined%20content.md) 

- [ ] [Add New Citation Format](./System/Documents/Add%20New%20Citation%20Format.md)

## Related Plugins

**These Obsidian plugins are pre-installed if you selected "Trust Author of this Vault" when first launching this vault.**

If certain Obsidian features are not functioning, or you want to customize the system by adding your own plugins, here is a complete list of plugins used in this project and the features they support. This helps simplify debugging and modification.

- [Command Palette Commands for Adding Template Note]()
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
- [Syncing Notes with GitHub](./System/Documents/Features/Syncing%20Notes%20with%20GitHub.md)
	1. [Git](https://github.com/Vinzent03/obsidian-git) - `2.31.1`








