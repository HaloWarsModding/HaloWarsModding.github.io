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
   - [Using A Mod Manager](#using-a-mod-manager)
3. [How to Uninstall Mods](#how-to-uninstall-mods)
   - [Manual Approach](#manual-approach-1)
   - [Using A Mod Manager](#using-a-mod-manager-1)

## How to Install Mods

### Manual Approach

If you prefer a hands-on approach, follow these steps to manually install mods:

1. **Download the Mod:** Start by downloading the mod you want to install. Mods typically come in compressed archive formats like `.rar` or `.zip`.
2. **Extract the Mod:** Use software like [WinRAR](https://www.win-rar.com/download.html) or [7-Zip](https://www.7-zip.org/download.html) to extract the contents of the mod archive.

3. **Locate Your Game Directory:**

    Steam
    {: .label }
    
   - You can place the mod folder anywhere on your PC.

   Windows Store
    {: .label }
    
   - Navigate to `C:\Users\YourUsername\AppData\Local\Packages\Microsoft.BulldogThreshold_8wekyb3d8bbwe\LocalState`.
4. **Copy Mod Files:** Open the extracted mod folder and locate the `ModData` folder. Copy the address/path of this folder (or the mod folder itself if `ModData` isn't present).
5. **Paste Mod Path:** Navigate to `C:\Users\*YourUsername*\AppData\Local\Halo Wars` and create a new text file named `ModManifest.txt`. Paste the copied address/path into this file.
6. **Save and Finish:** Save the `ModManifest.txt` file, and you're done! The mod is now installed and ready to use.

### Using A Mod Manager

Follow these steps to install mods using Medstar's Mod Manager:

1. **Download the Mod:** Start by downloading the mod you want to install. Mods compatible with Medstar's Mod Manager will have a `ModData` folder.

2. **Extract the Mod:** Use software like [WinRAR](https://www.win-rar.com/download.html) or [7-Zip](https://www.7-zip.org/download.html) to extract the mod archive.

3. **Install Mod Manager:** Download and install Medstar's Mod Manager.

4. **Place Mod in Mod Manager Directory:** Move the mod folder into the `HWDEMods` folder located in the Mod Manager's directory.

5. **Activate Mod:** Follow the instructions provided with Medstar's Mod Manager to activate the mod.

## How to Uninstall Mods

### Manual Approach

Uninstalling mods is straightforward:

- **Manual Uninstallation:** Delete the `ModManifest.txt` file or the entire mod folder from your game directory.

### Using A Mod Manager

Uninstalling mods with Medstar's Mod Manager is simple:

- **Deactivate Mod:** Use Medstar's Mod Manager to deactivate the mod. You can choose to play the vanilla version of the game at any time without uninstalling mods.
