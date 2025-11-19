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

## Installation

To get started open your project repository in vscode as a workspace(Equivalent to opening the folder with vscode or Ctrl+Shift+A from Github Desktop) and start the Docker client.

With the Dev Containers extension intalled  click on the extension's button (on the bottom left) and click `Add Dev Container Configuration Files...`. 

Choose if you want to add it locally (user data folder) or to the repo (workspace), adding it to the repo will let all of your collaborators to skip the installation step.

Next you'll be asked to select a template or enter a cutom id, enter the following id:
```
ghcr.io/EstebenR/devcontainers/nevermore
```

No additional features are needed, just click Ok.

You may be prompted to Reopen in Container by VSCode or just click on the extension menu again and click 'Reopen in Container'

So that all tools are installed make sure to run
```bash
rokit install
```
and 
```bash
npm install
```


## Continued use

Before opening the container, the docker app needs to have been launched. If it's not, VSCode will let you know so no problem.

Simply click 'Reopen in container' from the Dev Containers menu, it should all be set up from the installation step.

If it's your first time running this container then make sure to run 
```bash
rokit install
```
and 
```bash
npm install
```