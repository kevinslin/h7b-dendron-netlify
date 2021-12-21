---
id: p6DAGnvvh2NUL4A2zsAW6
title: Image
desc: ''
updated: 1638738820874
created: 1631926358221
---
# Resize and display image in Dendron

ref: [Images | Dendron Wiki](https://wiki.dendron.so/notes/a91fd8da-6895-49fe-8164-a17acd8d9a17/)

By appending [CSS properties](https://wiki.dendron.so/notes/a91fd8da-6895-49fe-8164-a17acd8d9a17/#allowed-css-properties), Dendron allow me to 
- limit the width of the image
    - `width` sets a fixed size for it
    - `max-width` will set the maximum size but will allow smaller sizes (for example, on mobile)
    - example: 
    ```code
    ![](/assets/images/example.png){max-width: 300px}
    ```
- centering
    - This image will be smaller, and will be centered in the page.
    - The code for it looks like this:
    ```code
    ![](/assets/images/example.png){max-width: 300px, display: block, margin: 0 auto}
    ```
## Better shared link preview of Dendron published page 

If you share a Dendron-published link on social media (Discord server, Twitter...), without insterting image tag, the preview will be like this
![link preview without image tag](https://i.imgur.com/7ZBG3G0.png){max-width: 300px, display: block, margin: 0 auto}

By inserting proper image tag in the frontmatter of the particular article, you will get a better preview
![link preview with image tag](https://i.imgur.com/18skuua.png){max-width: 300px, display: block, margin: 0 auto}

The example of the frontmatter with `image` tag is as follows.
```yaml
---
id: fDCVPEo3guCFWPdxokXHU
title: Best Mobile Note-Taking Apps for Markdown
desc: ''
updated: 1635183157051
created: 1632684719327
date: '2021-10-25'
excerpt: An overview of mobile apps that work well with Markdown
author: Derek Ardolf
image:
  url: https://org-dendron-public-assets.s3.amazonaws.com/images/blog-mobile-editor-header.png
  alt: Mobile phone sitting ontop of a journal
publish: true
---
```
