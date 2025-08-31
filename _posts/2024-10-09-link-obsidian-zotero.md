---
title: 'Link Zotero and Obsidian'
date: 2024-10-09
permalink: 
tags:
  - Zotero
  - Obsidian
  - Citation
---

### How to link Zotero and Obsidian

How to cite Zotero'item in Obsidian's note.

### Install

It needs to install one plugin in Zotero and two plugins in Obsidian.

1. Install [Better BibTeX for Zotero](https://retorque.re/zotero-better-bibtex/installation/) plugin in Zotero
2. Install Zotero Integration, Pandoc Reference List plugins in Obsidian

### Configuration

After installing plugins in Obsidian, additional configuration is required for both plugins.

### Zotero Integraion

1. In __Citation Formats__, add a citation style you want. __Name__ is just a name for you to choose from in command palette when you add a citation later.
2. Set the __Output Format__ to __Pandoc__. So, the actual styling task is done by __Pandoc Reference List__ plugin.

### Pandoc Reference List

1. Enable __Pull bibliography from Zotero__.

2. In __Citation style__, choose actual citation style you want. In this example, we choose APA 7 edition.

[//]: # (![[Pasted image 20241008162718.png]])

### Usage

To cite a reference in Obsidian, 
1. Click __Open command palette__. Create a hotkey for this for convenience.
2. Chose __Zotero Integration: APA__. This is the name we configured in the __Zotero Integration__ setting.
3. Zotero citation window would show up just like it would in MS Word.
5. Type the name of reference.
6. in-text citation is added like this in the note.
   Abernathy & Utterback (1978)
7. Click __Open command palette__, choose Pandoc Reference List: Show reference list, then the referents would show up on the right panel8. 
8. Copy the contents of __References__, and paste them in the note.

### References

Signal Processing with Paul (Director). (2024, July 16). _How to use Zotero in Obsidian_ [Video recording]. [https://www.youtube.com/watch?v=8yMko1m8XSQ](https://www.youtube.com/watch?v=8yMko1m8XSQ)

Better BibTeX for Zotero. (n.d.). Retrieved October 9, 2024, from https://retorque.re/zotero-better-bibtex/
