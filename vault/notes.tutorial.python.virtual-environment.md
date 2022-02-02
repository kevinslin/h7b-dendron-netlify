---
id: 5AA8KKYfUpbCkcdm7CaMX
title: Virtual Environment
desc: ''
updated: 1643760371158
created: 1639626240928
---
# Python Virtual Environments
ref: 
- [Real Python](https://realpython.com/python-virtual-environments-a-primer/)
- [opensource | guide with virtualenvwrapper](https://opensource.com/article/21/2/python-virtualenvwrapper)

by default, every project on your system will use the same directories to store and retrieve site packages (third party libraries)

The main purpose of Python virtual environments is to create an isolated environment for Python projects. This means that each project can have its own dependencies, regardless of what dependencies every other project has.

## Manage Virtual Environments with [virtualenvwrapper](https://virtualenvwrapper.readthedocs.org/en/latest/)

### Why virtualenvwrapper over other tools?
Some useful features of [virtualenvwrapper](https://virtualenvwrapper.readthedocs.org/en/latest/) are that it:
- Organizes all of your virtual environments in one location
- Provides methods to help you easily create, delete, and copy environments
- Provides a single command to switch between environments. It's just
  ```python
  workon projectname
  ```
  rather than
  ```python
  source ~/Projects/flashylights-env/bin/activate
  ```
- Instead of having a `venv` directory inside or alongside your project directory, `virtualenvwrapper` keeps all your environments in one place: `~/.virtualenvs` by default.

### Install `virtualenvwrapper`

#### On Windows 10, WSL2 Ubuntu

Prerequisite: [[Enable the Windows Subsystem for Linux (WSL)|notes.tutorial.windows-subsystem-for-linux]]

1. Check if Python was installed in this WSL  
    ```bash
    python3 -V
    ```
2. Download [virtualenvwrapper](https://virtualenvwrapper.readthedocs.org/en/latest/)
    ```bash
    sudo pip3 install virtualenvwrapper
    ```
3. Edit my shell's RC file (e.g. .bashrc, .bash_profile, or .zshrc) and adding the following lines
    ```bash
    # setup script for virtualenvwrapper
    export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
    export VIRTUALENVWRAPPER_VIRTUALENV=/usr/local/bin/virtualenv
    source /usr/local/bin/virtualenvwrapper.sh
    WORKON_HOME=$HOME/.virtualenvs
    PROJECT_HOME=$HOME/projects
    ```

#### On Windows 10
1. I use this [answer](https://stackoverflow.com/questions/20979474/how-can-i-set-environment-variable-workon-home-for-virtualenvwrapper-win/56120236#56120236) to define the `WORKON_HOME` and `PROJECT_HOME` environment variables in Win 10.
    ```shell
    [Environment]::SetEnvironmentVariable("WORKON_HOME", "D:\Workspace\.virtualenvs", "User")
    [Environment]::SetEnvironmentVariable("PROJECT_HOME", "D:\Workspace\project", "User")
    ```

### Use `virtualenvwrapper`

Display the location of `$WORKON_HOME` that contains all of the virtualenvwrapper data/files
```shell
$ echo $WORKON_HOME
```

[mkvirtualenv](http://virtualenvwrapper.readthedocs.org/en/latest/command_ref.html#mkvirtualenv)  
create and activate a new environment in the directory located at `$WORKON_HOME`
```shell
$ mkvirtualenv my-new-project
```

[deactivate](http://virtualenvwrapper.readthedocs.org/en/latest/command_ref.html#deactivate)  
stop using that environment
```shell
(my-new-project) $ deactivate
```

[workon](http://virtualenvwrapper.readthedocs.org/en/latest/command_ref.html#workon)  
List all working virtual environments
```shell
$ workon
```
Activate the desired environment
```shell
$ workon project-name
```

## Related resources

- [Liquid Web | setup Python Virtual Environment on Windows 10](https://www.liquidweb.com/kb/how-to-setup-a-python-virtual-environment-on-windows-10/)
- [Ruslanmv | setup Python Virtual Environment in WSL](https://ruslanmv.com/blog/Python3-in-Windows-with-Ubuntu)
- [Analyzing Alpha | Python Virtual Environments: Setup & Usage](https://analyzingalpha.com/python-virtual-environment)