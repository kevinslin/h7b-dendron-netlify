---
id: c1-h7c_wOFHJkpzI1t4Gx
title: Dendron
desc: ''
updated: 1637684294077
created: 1625432744672
---
# Publish notes using Dendron and Github Pages

## Install dendron-cli

Install dendron-cli to check version of dendron and further experiments<br>
Ref: [Dendron wiki](https://wiki.dendron.so/notes/23a1b942-99af-45c8-8116-4f4bb7dccd21.html)

In order dendron-cli script to work, I need to relax the script execution policies of Windows<br>
Ref: [Link](https://www.roelpeters.be/solved-running-scripts-is-disabled-on-this-system-in-powershell/)

## Initial Setup to write note and sync to GitHub
ref: [Dendron Wiki - publish your notes with Github pages](https://wiki.dendron.so/notes/yg3EL1x9fEe4NMqxUC3jP/)

- Configure Git login in VS Code<br>
    ```bash
    git config --global user.name "yourusername"
    git config --global user.email "email@youremail.com"
    ```
    Ref: [Link](https://www.jcchouinard.com/install-git-in-vscode/)
- Create a personal access token and use it to authenticate from VS Code.<br>
    Ref: [GitHub Docs](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token)
- Create a repo in GitHub named `{username}.github.io`. Hence my personal GitHub Pages will be `{username}.github.io/notes`
- Clone remote repo `{username}.github.io` to local (my laptop). I simply install and use [GitHub Desktop](https://desktop.github.com/) to do this
- Open VS Code > Open Command Palette (`Ctrl + Shift + P`) > Type in `Dendron: Initialize Workspace` > Choose the correct location of my cloned repo, setup from previous step. 
- Start to write 1st note in Dendron.<br>
    Ref: [Dendron Wiki](https://wiki.dendron.so/notes/784b8d5e-58eb-4e3e-98b0-8ed1690abc74.html)
- Add property `sync: sync` into  `dendron.yml`  
    ref: [Dendron wiki | per-vault configuration](https://wiki.dendron.so/notes/6682fca0-65ed-402c-8634-94cd51463cc4/#sync)  
    reason: enable Dendron synchronize everything: Dendron will first commit all your changes, then pull changes from the remote, and finally push everything back to the remote
    ```yaml
    vaults:
        -
            fsPath: vault
            name: h7b-blog-dendron
            sync: sync
    ```
- Open Command Palette > Type in `Dendron: Workspace: Sync` to synchronize your 1st note to your GitHub repo. 

## Setup to publish Dendron notes via GitHub Pages

- Turn on GitHub Pages of the created repo `{username}.github.io`
- Add property `SITE_URL` into `dendron.yml`<br>
    `SITE_URL` should be `{username}.github.io`<br>
    Ref: [Dendron Wiki](https://wiki.dendron.so/notes/230d0ccf-5758-4a8f-b39b-3b68e1482e2b.html)


## Dendron - Configuration per Worspace

Ref: [Dendron Wiki](https://wiki.dendron.so/notes/f83c1d87-eac0-48f3-a5cf-8a69989d8ec1.html)

All of the properties mentioned below need to be created/modified in `dendron.yml` which is accessed via `Ctrl + Shift + P` then `Dendron: Configure (yaml)`
- `useFMTitle: false`<br>
    Set to `false`, not use frontmatter as title when publishing and in the preview<br>
    Ref: [Dendron wiki](https://wiki.dendron.so/notes/f83c1d87-eac0-48f3-a5cf-8a69989d8ec1.html#usefmtitle)
- `hierarchyDisplayTitle: "Read more ⬇️"`<br>
    Change the title for children links in published sites from `Children` to `Read more ⬇️`<br>
    Ref: [Dendron wiki](https://wiki.dendron.so/notes/f83c1d87-eac0-48f3-a5cf-8a69989d8ec1.html#hierarchydisplaytitle)
- ~~`workspaceVaultSync: sync`<br>
    Enable sync notes using command `Dendron: Workspace: Sync`<br>
    Ref: [Dendron wiki](https://wiki.dendron.so/notes/c4cf5519-f7c2-4a23-b93b-1c9a02880f6b.html#workspace-sync)~~
- Replace `workspaceVaultSync: sync` (previous item) by using [per-vault configuration](https://wiki.dendron.so/notes/6682fca0-65ed-402c-8634-94cd51463cc4/#sync)  
    reason: `workspaceVaultSync: sync` will be deprecated (ref: [Dendron wiki](https://wiki.dendron.so/notes/f83c1d87-eac0-48f3-a5cf-8a69989d8ec1/#workspacevaultsync))

## Dendron - Configuration per Site
All of the properties mentioned below need to be created/modified in `dendron.yml`, under `site` property

- `siteUrl: {username}.github.io`<br>
    Since I am publishing with GitHub pages, the URL will be `https://{username}.github.io/{notes}/`
- `siteLastModified: true`<br>
    Show a last modified at the bottom of your site
- `gh_edit_link: true`<br>
    Show a `Edit this page on GitHub` link at the bottom of the page
- `gh_edit_view_mode: edit`<br>
    Bring the user directly into editing mode, when they click on `Edit this page on GitHub` link
- `gh_edit_repository: "https://github.com/h7b/h7b.github.io"`<br>
    Add the URL my page's GitHub repository  
    Ref: [Dendron Wiki](https://wiki.dendron.so/notes/f2ed8639-a604-4a9d-b76c-41e205fb8713.html#gh_edit_repository)
- `gh_edit_branch: main`<br>
    Set the branch `main` that my GitHub Pages site is served from
- `title`<br>
    Name of page
- `description`<br>
    Short description of what this page is about
- `author`<br>
    Author of published notes
- `duplicateNoteBehavior`<br>
    I remove this property since I don't intend to use or publish multi-vault scenario
- `mermaid`<br>
    Enable [[mermaid.js | notes.tutorial.mermaid-js]] support to create diagrams<br>
    Ref: [Dendron Wiki](https://wiki.dendron.so/notes/ba97866b-889f-4ac6-86e7-bb2d97f6e376.html#diagrams)
- `useKatex`<br>
    Enable Katex support to render Math equations
- `publishByDefault`<br>
    ```yaml
    config:
        blog:
            publishByDefault: false
    ```
    Setup Dendron to only publish notes within the hierarchy `blog` that have `published: true` property in notes' frontmatter<br>
    Ref: [Dendron Wiki](https://wiki.dendron.so/notes/c93938a4-0938-49d0-aca2-00e624793650.html)
- `logo`<br>
    Add a logo image for all headers<br>
    Ref: [Dendron Wiki](https://wiki.dendron.so/notes/f2ed8639-a604-4a9d-b76c-41e205fb8713.html#logo-optional)
- `siteFaviconPath`<br>
    Set path to favicon<br>
    Ref: [Dendron Wiki](https://wiki.dendron.so/notes/f2ed8639-a604-4a9d-b76c-41e205fb8713.html#sitefaviconpath-optional)

## Dendron - Configuration per note
- `blog` frontmatter
    - `published: true`
        Set to publish the `blog` page
    - `nav_order: 2`<br>
        Denote order that `blog` appears after `root` in the published nav bar. `root` has `nav_order: 1` by default.
    - `has_collection: true`<br>
        Set `blog` as a collection, which doesn't have a table of contents (children links)
    - `sort_by: date`
        Sort items in `blog` collection page, by created date
    - `sort_order: reverse`<br>
        Sort items in `blog` collection page, by descending order
- `notes` frontmatter
    - `nav_order: 3`<br>
        Denote order that `notes` appears after `blog` in the published nav bar
    - `reading` frontmatter
        - `nav_order: 1` <br>
            Denote order that `reading` appears 1st as children of `notes` in the published nav bar
    - `tutorial` frontmatter
        - `nav_order: 2` <br>
            Denote order that `tutorial` appears in 2nd order as a children node of `notes` in the published nav bar
    - `finance` frontmatter
        - `nav_order: 3`
    - `news` frontmatter
        - `nav_order: 4`
- blog articles frontmatter
    - `published: true`<br>
        Set the published status of each article. `true` means the article is published
    - `excerpt: 'expample_content'`<br>
        Set an `example_content` to be displayed as excerpt of each blog articles in the `blog` collection<br>
        Ref: [Dendron Wiki](https://wiki.dendron.so/notes/f2ed8639-a604-4a9d-b76c-41e205fb8713.html#excerpt)