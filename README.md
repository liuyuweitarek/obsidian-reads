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
	See more in [Syncing Notes with GitHub](./System/Documents/Features/Syncing%20Notes%20with%20GitHub.md).
7. **(Optional)** [Login Zotero](https://www.zotero.org/) for backing up literature.
## Workflows

Please see the [Paper Reading WorkFlow](./System/Documents/Workflows/Paper%20Reading%20WorkFlow.md).
## Features

This section outlines the features available in the current project, including their usage, recommended hotkeys, and purposes.

Not all features will suit every user's needs, and you may have alternative approaches to achieve the same goals. Pull requests are always welcome. Feel free to enable only the features you require and focus on learning those.

**Obsidian**

- [x] [Syncing Notes with GitHub](./System/Documents/Features/Syncing%20Notes%20with%20GitHub.md)

- [x] [Import Literature from Zotero](./System/Documents/Features/Import%20Literature%20from%20Zotero.md)

- [x] [Note Properties Management](https://youtu.be/qi4Uz7TZLOM?si=x3g8RJoYi-bRlcw0)

- [x] [Command Palette Commands for Adding Template Note](https://youtu.be/LrQVQ37y6IU?si=VSkvdPPK1wPrilAr)

**Zotero** 

- [x] Transcript Underlined Content 

- [x] [Add New Citation Format](https://www.zotero.org/support/preferences/cite)

## Related Plugins

**These Obsidian plugins are pre-installed if you selected "Trust Author of this Vault" when first launching this vault.**

If certain Obsidian features are not functioning, or you want to customize the system by adding your own plugins, here is a complete list of plugins used in this project and the features they support. This helps simplify debugging and modification.

- [Syncing Notes with GitHub](./System/Documents/Features/Syncing%20Notes%20with%20GitHub.md)
	1. [Git](https://github.com/Vinzent03/obsidian-git) - `2.31.1`
	
- [Import Literature from Zotero](./System/Documents/Import%20Literature%20from%20Zotero.md)
	1. [Zotero Integration](https://github.com/mgmeyers/obsidian-zotero-integration)- `3.1.14` 
	3. [Templater](https://github.com/SilentVoid13/Templater) - `1.18.3`

- [Note Properties Management](https://youtu.be/qi4Uz7TZLOM?si=x3g8RJoYi-bRlcw0)
	1. [Metadata Menu](https://github.com/mdelobelle/metadatamenu) - `0.8.7`
	2. [Dataview](https://github.com/blacksmithgu/obsidian-dataview) - `0.5.67`

- [Command Palette Commands for Adding Template Note](https://youtu.be/LrQVQ37y6IU?si=VSkvdPPK1wPrilAr)
	1. [QuickAdd](https://github.com/chhoumann/quickadd) - `1.11.5`
	2. [Templater](https://github.com/SilentVoid13/Templater) - `1.18.3`
	3. [Metadata Menu](https://github.com/mdelobelle/metadatamenu) - `0.8.7`
	4. [Dataview](https://github.com/blacksmithgu/obsidian-dataview) - `0.5.67`








