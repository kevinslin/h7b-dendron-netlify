---
id: zUTHtkQuKQWwnIiQhb9uJ
title: Mito
desc: ''
updated: 1639885986837
created: 1639628094199
---
# Getting started with [Mito](https://trymito.io/)

## Installing Mito
ref: [Mito | Install Mito inside a virtual environment](https://docs.trymito.io/getting-started/installing-mito/installing-mito-inside-a-virtual-environment),

Preparation: [[Install virtualenvwrapper|notes.tutorial.python.virtual-environment#install]]

Step-by-step:

1. Create a new virtual environment named `mitoenv`
    ```shell
    mkvirtualenv mitoenv
    ```
2. install the Mito installer
    ```shell
    pip3 install mitoinstaller
    ```
3. run the installer
    ```shell
    python3 -m mitoinstaller install
    ```
    Done here. Jupyter Lab will be called to open in browser.
4. Next time, I can initiate Jupyter lab instance to start, using
    ```shell
    py -m jupyter lab
    ```