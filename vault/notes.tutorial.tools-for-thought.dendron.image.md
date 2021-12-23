---
id: p6DAGnvvh2NUL4A2zsAW6
title: Image
desc: ''
updated: 1640217151668
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

## Trick to update embedded image in multiple notes

Instead of just using image links `![img](img.link)` throughout your docs, using note refs with a single image link allows me to embed it everywhere

Trick:
- Create a Dendron note that contains all of the images that need to be referenced, with a dedicated header for each image  
  ```md
  ![Tutorial Welcome Screen](https://org-dendron-public-assets.s3.amazonaws.com/images/tutorial-welcome-screen-2.png)
  ```
  Example notes with all of image links:
[dendron-github-all-images](https://github.com/dendronhq/dendron-site/blob/master/vault/asset.preview.md#tutorial-dendron-layout-dark)
- Then use Dendron note ref throughout docs for specific images
  ```md
  ![[dendron://dendron.dendron-site/asset.preview#tutorial-dendron-layout-dark,1:#*]]
  ```
  Example embedded image in other notes:
[dendron-image-other-note](https://github.com/dendronhq/dendron-site/blob/a9373e4ae16c1dd00eca79d9328336c5f54277d3/vault/dendron.tutorial.user-interface.md?plain=1#L14)