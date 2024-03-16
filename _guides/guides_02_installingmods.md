---
title: Installing Mods
description: "Learn how to install mods for Halo Wars: Definitive Edition"
permalink: /guides/installing-mods
layout: default
nav_order: 2
image: https://raw.githubusercontent.com/HaloWarsModding/HaloWarsModding.github.io/master/resources/images/metadata/header.png
toc: true
---

# Installing Mods

Work In Progress
{: .label .label-blue }

Welcome to the world of modding for Halo Wars: Definitive Edition! This guide will walk you through the process of installing mods manually or using Medstar's Mod Manager.

[Medstar's Mod Manager](https://www.moddb.com/downloads/start/226029?referer=https%3A%2F%2Fwww.moddb.com%2Fmods%2Fhalo-wars-de-mod-manager%2Fdownloads){: .btn .btn-purple }
[WinRAR](https://www.win-rar.com/download.html){: .btn .btn-blue } [7-Zip](https://www.7-zip.org/download.html){: .btn .btn-green }

1. [Getting Started](#getting-started)
2. [How to Install Mods](#how-to-install-mods)
   - [Manual Approach](#manual-approach)
   - [Using Medstar's Mod Manager](#using-medstar-s-mod-manager)
3. [How to Uninstall Mods](#how-to-uninstall-mods)
   - [Manual Approach](#manual-approach-1)
   - [Using Medstar's Mod Manager](#using-medstar-s-mod-manager-1)

## How to Install Mods

### Manual Approach

If you prefer a hands-on approach, follow these steps to manually install mods:

- Start by downloading the mod you want to install. Mods typically come in compressed archive formats like `.rar` or `.zip`.
- Use software like [WinRAR](https://www.win-rar.com/download.html) or [7-Zip](https://www.7-zip.org/download.html) to extract the contents of the mod archive.

| Distribution  | Path              | 
|:--------------|:------------------|
| Steam         | You can place the mod folder anywhere on your PC |
| Windows Store | C:\Users\YourUsername\AppData\Local\Packages\Microsoft.BulldogThreshold_8wekyb3d8bbwe\LocalState | 

- Open the extracted mod folder and locate the `ModData` folder. Copy the address/path of this folder (or the mod folder itself if `ModData` isn't present).
- Navigate to `C:\Users\Username\AppData\Local\Halo Wars` and create a new text file named `ModManifest.txt`. Paste the copied address/path into this file.
- Save the `ModManifest.txt` file, and you're done! The mod is now installed and ready to use.

### Using Medstar's Mod Manager

Follow these steps to install mods using Medstar's Mod Manager:

- Start by downloading the mod you want to install. Mods compatible with Medstar's Mod Manager will have a `ModData` folder.

- Use software like [WinRAR](https://www.win-rar.com/download.html) or [7-Zip](https://www.7-zip.org/download.html) to extract the mod archive.

- Download and install Medstar's Mod Manager.

- Move the mod folder into the `HWDEMods` folder located in the Mod Manager's directory.

![](https://raw.githubusercontent.com/HaloWarsModding/HaloWarsModding.github.io/master/resources/images/modmanager/1.png)

{: .note }
When closing the mod manager, ALWAYS close it using the X within the mod manager, otherwise it will remain running in the background and won't let you reopen it unless you end the process with task manager.

## How to Uninstall Mods

### Manual Approach

To uninstall mods manually:

- Delete the `ModManifest.txt` file, and the game will no longer load the mod.

### Using Medstar's Mod Manager

Uninstalling mods with Medstar's Mod Manager is straightforward:

- Open Medstar's Mod Manager and navigate to the "My Mods" section.
- Click on "My Mods," and the program will open your file explorer to the mod directory.
- From here, you can easily delete any installed mods. Remember, you can also revert to the original game state by selecting "Vanilla" within the tool.
