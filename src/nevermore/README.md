
# Nevermore Roblox (nevermore)

A container for easy Nevermore setup with Luau LSP included

## Options

| Options Id | Description | Type | Default Value |
|-----|-----|-----|-----|


Welcome to the nevermore dev container for VSCode. 

This projects aims to set up a quick start environment with everything needed for Nevermore Roblox game development.

## Why?

Using Nevermore on Roblox has different requirements from other usual workflows in the ecosystem.

Namely the usage of npm which requires a node installation and a global nevermore install and the use of a different version of language server extensions to be compatible with name requires.

## Requirements

To be able to use this container you'll need to have installed [Docker](https://www.docker.com/get-started/) on your system and the [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension in VSCode.

## Usage notes

There is some setup required before going ahead with running your project a little one time setup is required:

### Required tools

This container comes with `Rokit` for toolchain management, it's also compatible with preexisting Aftman and Foreman managed projects. If you don't know which one to use/ don't have a preference, use the bundled Rokit.
For this guide, it is assumed that you use rokit in your project, use the equivalent commands for whichever toolchain manager you're using.


Make sure to add `Quenty/luau-lsp@1.46.0-quenty` to your repository by running 
```bash
rokit add Quenty/luau-lsp@1.46.0-quenty
```
this will make available the correct lsp binary for Nevermore for our extension to use, more on that later. You have to install/upgrade to this version because we bundle the latest official Luau LSP extension version that's compatible with Quenty's.

Use Quenty's rojo `Quenty/rojo`
```bash
rokit add quenty/rojo
```


### Workspace settings

Make sure to add the following to your .vscode/settings.json in your repo so that the correct lsp is used. Ideally you check this in so that everybody's works out of the box
```json 
"luau-lsp.sourcemap.rojoPath": "/root/.rokit/bin/luau-lsp"
```

## Installation

To get started open your project repository in vscode as a workspace. (Equivalent to opening the folder with vscode or Ctrl+Shift+A from Github Desktop)

With the Dev Containers extension intalled 

## Continued use

Simply click 'Reopen in container' from the Dev Containers menu, it should all be set up from the installation step.

---

_Note: This file was auto-generated from the [devcontainer-template.json](https://github.com/EstebenR/devcontainers/blob/main/src/nevermore/devcontainer-template.json).  Add additional notes to a `NOTES.md`._
