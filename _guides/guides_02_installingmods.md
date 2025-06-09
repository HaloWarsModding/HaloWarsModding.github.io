---
title: Installing Mods
description: "Learn how to install mods for Halo Wars: Definitive Edition"
permalink: /guides/installing-mods
layout: default
nav_order: 2
image: https://raw.githubusercontent.com/HaloWarsModding/HaloWarsModding.github.io/master/resources/images/metadata/header.png
toc: true
---

# Installing Mods <span class="label label-green">Stable</span>
{: .no_toc }

{: .new }
**Medstar Mod Manager** has been renamed to **Firebase**.  
All functionality remains the same, just under a new name.

Welcome to the world of modding for Halo Wars: Definitive Edition! This guide will walk you through the process of installing mods manually or using the [Firebase Mod Manager](https://github.com/HaloWarsModding/Firebase).

[Firebase](https://github.com/HaloWarsModding/Firebase/releases/download/2024.5.15.2/AutoUpdatePackage.zip){: .btn .btn-purple } [WinRAR](https://www.win-rar.com/download.html){: .btn .btn-blue } [7-Zip](https://www.7-zip.org/download.html){: .btn .btn-green }

1. TOC
{:toc}

---

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

---

### Using Firebase Mod Manager

Follow these steps to install mods using [Firebase](https://github.com/HaloWarsModding/Firebase)

- Start by downloading the mod you want to install. Mods compatible with Firebase will typically have a `ModData` folder.
- Use software like [WinRAR](https://www.win-rar.com/download.html) or [7-Zip](https://www.7-zip.org/download.html) to extract the mod archive.
- Download and install [Firebase](https://github.com/HaloWarsModding/Firebase/releases/download/2024.5.15.2/AutoUpdatePackage.zip)
- Move the mod folder into the `HWDEMods` folder located in Firebase's directory.

![](https://raw.githubusercontent.com/HaloWarsModding/HaloWarsModding.github.io/master/resources/images/modmanager/1.png)

{: .note }
When closing Firebase, use the `[X]` in its window. Closing it via the taskbar or `Alt+F4` may leave it running in the background, preventing relaunch until it's ended in Task Manager.

---

## How to Uninstall Mods

### Manual Approach

To uninstall mods manually:

- Delete the `ModManifest.txt` file, and the game will no longer load the mod.

---

### Using Firebase Mod Manager

Uninstalling mods with Firebase is straightforward:

- Open Firebase and navigate to the "My Mods" section.
- Click "My Mods" to open your file explorer to the mod directory.
- From there, delete any installed mods you no longer want.
- You can also revert to the unmodified game by selecting the "Vanilla" option inside Firebase.
