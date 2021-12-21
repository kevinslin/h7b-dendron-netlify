---
id: 3UHqQ5XkT3JvF1JE4jUdR
title: Deploy Netlify
desc: ''
updated: 1640063047662
created: 1640060126202
---
# Deploy my Dendron vault on Netlify

ref: [Dendron blog](https://blog.dendron.so/notes/7h7zZkjF4Yqz8XSrHS1je/)

## Getting started

1. Signup [Netlify](https://www.netlify.com/)

2. Generate a new Dendron Workspace pre-configured for Netlify publishing by cloning this [template](https://github.com/dendronhq/template.publish.netlify) into my GitHub repo
    ![dendron-template](https://org-dendron-public-assets.s3.amazonaws.com/images/github-create-workspace-netlify.gif){max-width: 300px, display: block, margin: 0 auto}
    my repo name: `h7b-dendron-netlify`

3. Import my repo `h7b-dendron-netlify` to Netlify and deploy
    ![netlify-import](https://org-dendron-public-assets.s3.amazonaws.com/images/netlify-import-git-repo.gif){max-width: 300px, display: block, margin: 0 auto}

4. Configure my website name
    ![netlify-change-site-name](https://org-dendron-public-assets.s3.amazonaws.com/images/netlify-change-site-name.gif){max-width: 300px, display: block, margin: 0 auto}

DONE

## Move contents from old vault to new vault

1. Clone `h7b-dendron-netlify` repo (created in `Getting started` - step 2) to my laptop using `GitHub Desktop` app

2. Modify file `dendron.yml`
    ```yaml
    site:
        title: H7B
        description: Mes belles lettres
        logo: vault/assets/logo.png
        siteFaviconPath: vault/assets/favicon.ico
        siteUrl: 'https://h7b.netlify.app/'
    ```
    ```yaml
    workspace:
        vaults:
        -
            fsPath: vault
            name: h7b-dendron-netlify
            sync: sync
    ```

3. Copy `vault` folder from old location to replace `vault` folder in new repo `h7b-dendron-netlify` folder location.

4. Commit and push new contents to repo `h7b-dendron-netlify`

DONE