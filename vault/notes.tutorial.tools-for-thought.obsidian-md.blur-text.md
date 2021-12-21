---
id: 2VmeSowFYYq0e1Ux
title: Blur Text
desc: ''
updated: 1637436342749
created: 1626767712882
---
# How to blur text when taking screencap in Obsidian.md app

Tutorial screencast: [Link from Obsidian Community discord](https://www.loom.com/share/20ebce50f6d04b5cbd89cf89643dfb2e)

While using Obsidian, press `Ctrl + Shift + I` (`Option + Cmd + I` for macOS) to bring up the developer window. Then choose the `Console` tab, and type in

Use to blur
> app.garbleText()

Use to unblur
> app.dom.appContainerEl.removeClass("is-text-garbled");

Or I can search for `Garble Text` plugin in `Community Plugin`
