---
id: I4vsY3q3vnRfMhKb
title: Docusaurus
desc: ''
updated: 1640390173114
created: 1627044913994
---
# Deploy documents and blog with Docusaurus

Tutorial `Docusaurus in 5 min` from [Docusaurus](https://tutorial.docusaurus.io/docs/intro)

Introduction docs of `Docuraurus`. Read more at [link](https://docusaurus.io/docs)

Playground to test Docusaurus in browser, without installing anything. Read more at [link](https://docusaurus.io/docs/playground)

It is easy to transalte a Docusaurus site with its internationalization (i18n) support. Read more at [link](https://docusaurus.io/docs/i18n/introduction)

## Thoughts

My thoughts on Version: 2.0.0-beta.13

Pros:
- generate documents as a Single Page Application (SPA), dark mode
- Has sidebar navigation, menu bar, search bar, admonition, i18n built-in ([crowdin](https://crowdin.com/) plugin or alternative locale markdown files), `Next` and `Previous` UI links at the end of each doc page
- has url slug in frontmatter to generate a static URL for each md file

Cons:
- when I reorganize the hierarchy structure of md files (ie. move to other folder, rename folder that contains md files, rename md files) in `docs` folder, I need to manually  
    - update doc IDs in my sidebar file, since notes hierarchy structure are hardcoded in sidebar file for sidebar for navigation
    - update the reference links to other markdown files 
- does not support wikilink style, need custom script to convert to markdown link. Or use a [plugin](https://github.com/ozntel/obsidian-link-converter) in Obsidian to convert the link in notes within your vault.

## Helpful resources

- Tutorial in details by [Zatta Production](https://zatta.link/en/web/docusaurus-how-to.html)
- Tutorial in details by [Danny Chávez](https://github.com/dochavez/Documenting-with-Docusaurus-V2.-)
- Tutorial in details by [LogRocket](https://blog.logrocket.com/easy-documentation-with-docusaurus/)
- Tutorial by [Victoria Lo](https://dev.to/lo_victoria2666/build-beautiful-documentation-websites-with-docusaurus-8o2)
- Reason to use Docusaurus by [JavaScript in Plain English](https://javascript.plainenglish.io/10-reasons-to-use-docusaurus-for-your-docs-blog-marketing-site-48dbf2c58b70)

## Getting started
