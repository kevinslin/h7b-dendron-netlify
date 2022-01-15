---
id: n5Fr9vDFUxyDSxF6l4oEr
title: Git Directory and Work-Tree Explained
desc: ''
updated: 1642208178101
created: 1642180076564
---
# Can I store the .git folder outside the files I want tracked?
ref: [Stack Overflow](https://stackoverflow.com/questions/505467/can-i-store-the-git-folder-outside-the-files-i-want-tracked), [jdhao's blog](https://jdhao.github.io/2020/12/25/git_directory_work-tree_explained/), [Apple Communities](https://discussions.apple.com/thread/251290283)

Situation: 
- On laptop, I have a personal blog written with Dendron, which is a GitHub repo, located at local directory `./blog-dendron-repo/` and deploy on Netlify 
- I put the `./blog-dendron-repo/` inside the `Obsidian` folder in `iCloud Drive` to sync and use Obsidian on iOS to read and edit the Dendron vault on mobile.
- To keep things clean I don't want to have a `./blog-dendron-repo/.git` folder (Git directory)

So I came up with 2 possible solutions:
1. I separate the location of `.git` subfolder outside the folder `./blog-dendron-repo/` I want to track and sync via iCloud Drive.
2. Or I keep the location of `.git` subfolder inside the folder `./blog-dendron-repo/` but exclude the `.git` subfolder from `iCloud Drive` sync.

I incline to the 1st option, since the 2nd choice might break the Git workflow.

## Getting started
