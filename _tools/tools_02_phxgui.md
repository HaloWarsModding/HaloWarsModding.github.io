---
title: PhxGUI
description: "Overview and usage of PhxGUI — the official utilities for editing and rebuilding .era archives in Halo Wars DE."
permalink: /tools/phxgui
layout: default
nav_order: 2
toc: true
---

# PhxGUI <span class="label label-green">Stable</span>
{: .no_toc }

{: .note }
> Use these tools at your own risk. Modifying game files may result in instability, crashes, or bans in online play. Always back up original content.

Official archive management utilities developed by KornnerStudios for modding Halo Wars: Definitive Edition.

1. TOC
{:toc}

---

## Overview

PhxGUI and PhxTool are essential tools used to interact with `.era` files, the game’s compressed archive format for content like units, XML, textures, and more.

- `PhxGUI` is a user-friendly drag-and-drop interface.
- `PhxTool` is the command-line version with advanced flexibility.

Each `.era` contains different types of game data, and every map in Halo Wars has its own `.era` file as well. If you're looking to modify assets specific to a certain map, you can simply extract that map’s `.era` and work with it directly.  
By default, it's safe and common to extract all `.era` files together for a complete data dump.

{: .warning }
If your extracted files are named like `example.xml.xmb`, this means they are still compressed. To properly unpack these, drag and drop the entire containing folder into PhxGUI instead of the individual `.xmb` files.

Both are part of the [KSoft.Phoenix](https://github.com/KornnerStudios/KSoft.Phoenix) project and support `.era`, `.eradef`, `.xmb`, `.xml`, and executable patching for mod loading.


**[Download PhxGUI](https://github.com/HaloMods/HaloWarsDocs/releases/download/v1.0.8/PhxTools_20231125.7z){: .btn .btn-purple }**

![PHXTool](https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/resources/images/phxtool.png?raw=true)

---

## How to Use It

### 1. Launch and Select Game Version

By default, PhxGUI is set to DE. You can choose Xbox 360 instead.

### 2. Set Paths

- **ERA Expand Path** where extracted files will be dumped (ex: `C:/HaloWars/Extracted`)
- **ERA Build Path** where rebuilt archives will go (ex: your install folder)

### 3. Drag-n-Drop Operations

#### `.era` files → Extract
Extracts files from the archive and generates a matching `.eradef`.

#### `.xmb` files → Convert
Converts `.xmb` into readable/editable `.xml` files.
To use `.xml` instead of `.xmb` when rebuilding, use the **"Always build with XML"** toggle.

#### `.eradef` file → Rebuild
Rebuilds a new `.era` archive based on an edited `.eradef`.

#### `.exe` file → Patch
Patches the game executable to allow custom `.era` loading. Creates a backup with `_UNTOUCHED`.

---

## Tips

- `.eradef` = Manifest that controls what gets rebuilt into a new `.era`. All paths are relative to it.
- `.xmb` = Compressed XML. Convert to `.xml` to edit. Convert back or toggle XML-preferred build mode.
- Backup **everything** before patching your `.exe` or rebuilding `.era` files.
- Watch the bottom of the GUI for messages. Log file: `PhxGui.log`.

---

## Known Issues

- Some game builds (Halo Wars Alpha) require "Skip Verification" to rebuild successfully.

---

## Advanced Features

| Feature | Description |
|--------|-------------|
| `Validate Game Data` | Checks core XMLs for load errors and dependency issues. |
| `Always build with XML` | Forces build to use `.xml` if found instead of `.xmb`. Useful for era-modding. |
| `.ecf/.ecfdef` support | Can unpack and rebuild ensemble chunk files (used in many binary assets) (advanced feature). |

---

## PhxTool (CLI)

This command-line variant is left undocumented officially, but can handle most operations PhxGUI can. It is ideal for automation or scripting pipelines.
