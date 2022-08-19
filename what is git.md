# what is git ?

It is a version control system. 
....

# Git Config:

For setting git configuration, we use:

```git
$ git config
```
The git config command is a convenience function that is used to set Git configuration values on a global or local project level. These configuration levels correspond to . gitconfig text files. Executing git config will modify a configuration text file

## Why configuration with name and email address?

These details are simply used as metadata in each commit so anyone viewing the Git log would know who committed the code and how to get in touch with them

Setting the git configuration:

1. username
2. email
3. default editor for git (default is Vim)

There are 3 different levels for configuring the git:
1. System level - settings applies to all users of the current computer
2. Global level - settings applies to all repository of current user
3. Local level - settings applies to current repository of current user

so we can have different settings for different projects

## Setting the default editor
We can choose our own default editor for our git commands. If not set then git uses the default editor as vim which is not very user friendly. Here we will use vscode as default editor for git:

```git
$ git config --global core.editor "code --wait"
```
**Note:** 
- Before setting the editor, we need to add the vscode to path
- with `--wait` we tell the terminal window that "wait unit we close a new vs code instance".

## We can also view the settings in a txt file, to open it:

We can open our all the global settings in our default editor using:
```git
$ git config --global -e
```

## Setting the end of lines:
- in Windows end of line is `\r\n` and in mac it is `\n`
- if we dont handle end of line, there will be issues down the line

```git
$ git config --global core.autocrlf true
```
We can take help about git commands using `--help` for more detailed help or `-h` for short help

