---
id: zUTHtkQuKQWwnIiQhb9uJ
title: Mito
desc: ''
updated: 1640527093888
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
    pip install mitoinstaller
    ```
3. run the installer
    ```shell
    python -m mitoinstaller install
    ```
    Done here. Jupyter Lab will be called to open in browser.
4. Next time, I can initiate Jupyter lab instance to start, using
    ```shell
    py -m jupyter lab
    ```