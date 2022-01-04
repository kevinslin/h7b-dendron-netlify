---
id: 3UHqQ5XkT3JvF1JE4jUdR
title: Publish Netlify
desc: ''
updated: 1641258631208
created: 1640060126202
---
# Publish my Dendron vault using Netlify

Publish my Dendron vault by deploying on Netlify, with notes stored on private GitHub repo

ref: [Dendron blog](https://blog.dendron.so/notes/7h7zZkjF4Yqz8XSrHS1je/), [Dendron wiki](https://wiki.dendron.so/notes/yetuum6o9wZi6eVJQBbQb/)

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
        description: Kool Casa is my personal blog and notes. The site is published using Dendron, deployed on Netlify. Articles are plain Markdown files located in the vault directory. Each Mardown file also has a yaml frontmatter for storing metadata. The URL for each article is determined by the id in the frontmatter.
        author: Huy
        logo: vault/assets/logo.png
        siteFaviconPath: vault/assets/favicon.ico
        siteUrl: 'https://kool.casa/'
    ```
    ```yaml
    workspace:
        vaults:
        -
            fsPath: vault
            name: h7b-dendron-netlify
            sync: sync
    ```
    ```yaml
    preview:
        enableFMTitle: false
    ```
    ```yaml
    useFMTitle: false
    ```

3. Copy `vault` folder from old location to replace `vault` folder in new repo `h7b-dendron-netlify` folder location.

4. Commit and push new contents to repo `h7b-dendron-netlify`

DONE

## Thoughts:

With this Netlify workflow, I just need to use `Dendron: Workspace: Sync` to push updated contents. Then it's done on my part. The built process will be executed by Netlify. I don't have to use `Dendron CLI` to build manually and push output `docs` folder to GitHub Pages. 

By deploying on Netlify, my website will be built after each commits to my GitHub repo.

The free tier limit of Netlify is 
- 300 minutes / month for [Build minutes](https://www.netlify.com/pricing/faq/) (The time it takes Netlify to build my site)
- 100 GB / month Bandwidth

Wrt my usage during 15 days (from 2021-12-20 to 2022-01-04), by pushing daily updates to my repo, I spent 111/300 build minutes

## Assign my custom domain to Netlify site

ref: [Netlify docs](https://docs.netlify.com/domains-https/custom-domains/)

To assign a custom domain or domain alias to a site, go to `Site settings` › `Domain management`.

To add a custom domain, select `Add custom domain` at the bottom of the `Custom domains` panel, and enter your domain name. Select `Verify`.

If the domain is registered (already has an owner), you will be asked to confirm that you are the owner of the domain. If you are the owner, select Yes, add domain to assign the custom domain to the site.

if the domain was registered elsewhere (my case is [porkbun](https://porkbun.com/)), and you want to continue using your current DNS provider, you will need to add DNS records on your provider to point your domain or subdomain to your site on Netlify

## Configure external DNS for a custom domain

ref: [Netlify docs](https://docs.netlify.com/domains-https/custom-domains/configure-external-dns/)

DNS records in `porkbun` before change
![dns-before](https://i.imgur.com/VfwRxR9.jpg){max-width: 300px, display: block, margin: 0 auto}

In `porkbun` DNS control panel, 

1. Add a `CNAME` record for `www` subdomain, pointing to my site on Netlify `https://h7b.netlify.app/`
2. Add a `ALIAS` record for apex domain `kool.casa`, pointing to Netlify’s load balancer at: `apex-loadbalancer.netlify.com`

DNS records in `porkbun` after change
![dns-after](https://i.imgur.com/7Lo5EFF.jpg){max-width: 300px, display: block, margin: 0 auto}
