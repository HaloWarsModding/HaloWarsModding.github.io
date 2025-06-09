---
title: Firebase
description: "A mod manager for Halo Wars: Definitive Edition, offering fast switching, patching, and mod organization."
layout: default
nav_order: 5
permalink: /tools/firebase
image: https://raw.githubusercontent.com/HaloWarsModding/Firebase/main/docs/firebase_header.png
toc: true
---

# Firebase Mod Manager <span class="label label-green">Stable</span>
{: .no_toc }

{: .new }
Firebase is the renamed version of **Medstar Mod Manager**.  
It retains all core functionality with UI, validation, and performance improvements.  

[Download Firebase](https://github.com/HaloWarsModding/Firebase/releases/download/2024.5.15.2/AutoUpdatePackage.zip){: .btn .btn-purple }

1. TOC
{:toc}

---

## What is Firebase?

Firebase is a dedicated mod manager** for **Halo Wars: Definitive Edition**, providing a simplified workflow for installing and switching between mods.  

Firebase supports:
- `HWDEMods` mod directory
- `ModManifest.txt` usage
- Steam / Windows Store / Steam Deck environments

---

## How to Use

![](https://raw.githubusercontent.com/HaloWarsModding/HaloWarsModding.github.io/master/resources/images/modmanager/1.png)

1. Extract your mod into the `HWDEMods` folder inside the Firebase directory.
2. Run **Firebase.exe**.
3. Select your mod from the **My Mods** list.
4. Click **Enable Mod** or **Set Active** (depending on version).
5. Launch the game manually through Steam or the Windows Store.

{: .note }
Always close Firebase using the `[X]` button in the app UI.  
Closing it with Alt+F4 or from the taskbar may leave it running in the background and block relaunching.

---

## Patch Notes

<details open>
  <summary><strong>[Hotfix 2024.5.15.2] Config Generation Fix</strong></summary>
  <ul>
    <li><strong>Squashed Bugs:</strong>
      <ul>
        <li>Fixed issue with <code>Config.dat</code> not saving correctly on first time setup</li>
      </ul>
    </li>
    <li><strong>General Changes:</strong>
      <ul>
        <li>Reverted change to how <code>LocalAppData</code> folder is fetched</li>
      </ul>
    </li>
  </ul>
</details>

<details>
  <summary><strong>[Hotfix 2024.5.15.1] Microsoft Store and ModManifestMaker Fixes</strong></summary>
  <ul>
    <li><strong>Squashed Bugs:</strong>
      <ul>
        <li>Fixed an issue with Firebase finding Microsoft Store installs</li>
        <li>Fixed an issue with Firebase not applying the correct folder security to mods when launching (affects Microsoft Store installs)</li>
        <li>Fixed an issue with ModManifestMaker not being able to save new manifests and not validating data correctly</li>
      </ul>
    </li>
    <li><strong>General Changes:</strong>
      <ul>
        <li>Tweaked build settings to publish each executable fully self-contained (no need for extra assemblies)</li>
      </ul>
    </li>
  </ul>
</details>

<details>
  <summary><strong>[Version 2024.5.15] Resurrection</strong></summary>
  <ul>
    <li><strong>Squashed Bugs:</strong>
      <ul>
        <li>Fixed issue with mod manager sometimes launching headless (without UI)</li>
        <li>Background videos now pause when manager is minimized</li>
        <li>Compiled binaries are now self-contained (have .NET runtimes embedded)</li>
        <li>Fixed general instabilities</li>
      </ul>
    </li>
    <li><strong>General Changes:</strong>
      <ul>
        <li>Moved source to <code>HaloWarsModding</code> organization on GitHub, rebranded as "Firebase"</li>
        <li>Upgraded backend to .NET 8</li>
        <li>Releases for the mod manager will now be distributed as a <code>.zip</code> file for ease of use</li>
        <li>Auto updates are now distributed as <code>.zip</code> files for portability</li>
        <li>Added new tab in "Options" window for tools so that they're easier to find</li>
      </ul>
    </li>
  </ul>
</details>


---

## Support & Feedback

Although Firebase is not actively maintained, help is available via the community:

- [GitHub Issues](https://github.com/HaloWarsModding/Firebase/issues)  
- [Halo Wars Modding Discord](https://discord.gg/GuvUCgqz8d)
