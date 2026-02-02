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

Use Quenty's rojo `Quenty/rojo` for all your rojo needs
```bash
rokit add quenty/rojo
```

## Installation

To get started open your project repository in vscode as a workspace(Equivalent to opening the folder with vscode or Ctrl+Shift+A from Github Desktop) and start the Docker client.

With the Dev Containers extension intalled  click on the extension's button (on the bottom left) and click `Add Dev Container Configuration Files...`. 

Choose if you want to add it locally (user data folder) or to the repo (workspace), adding it to the repo will let all of your collaborators to skip the installation step.

Next you'll be asked to select a template, search for `Nevermore Roblox`. If it doesn't show up make sure to click on `Show All Templates`

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

Afterwards make sure to reload your luau lsp in vscode if it gave you any errors about the sourcemap, you can do it by pressing Ctrl+Shift+P and running `Luau: Reload Language Server`. If running in a large codebase it might take a bit to index all files the first time.

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

Afterwards make sure to reload your luau lsp in vscode if it gave you any errors about the sourcemap, you can do it by pressing Ctrl+Shift+P and running `Luau: Reload Language Server`. If running in a large codebase it might take a bit to index all files the first time.