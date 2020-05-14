---
layout: page
title: Getting Started
---

# Getting Started
Whether you're a new modder, or just need to brush up on the basics, this is the place to be.
This page will focus on what you need to begin making a mod. 

If you are a beginner, we recommend reading this page top to bottom twice before moving on to anything else, but if you're here for something specific, you can jump to the desired section by clicking on one of the following:

[Whats Needed?](#WhatsNeeded) <br>[Creating Your First Mod](#YourFirstMod)

***

<a name="WhatsNeeded"></a>
## Whats Needed?
### PHXTool - For Extracting Halo Wars: DE Content
<img width="422" height="279" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/phxtool.png?raw=true">

The absolute backbone of Halo Wars modding is the PHXTool by kornman00. This tool lets you unpack and re-pack Halo Wars' resource archives (.era files) so that you can make use of them in new content, or edit them for existing content. It can be downloaded [here](PHX DOWLOAD LINK).

The tool has several options. The 'ERA Expand Path' field allows you to specify where the archive will be dumped to. It is recommended to set this to an "Extract" folder either:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- In your game's install directory (Steam users \| Example: C:\Program Files (x86)\Steam\steamapps\common\HaloWarsDE).<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- In your documents folder (Windows Store Users \| C:\'USER'\Documents).

The "ERA Build Path" field allows you to specify where you want an archive to be spit out when it is re-built. This feature is hardly ever needed, but is still sometimes useful. It is recommended to be set to your game's install directory. **Note: Always make a backup of all your files before modifying anything. Rebuilding an archive into your install directory will overwrite the original file unless "Don't overwrite existing files" is checked.**

For the basics, none of the flags are required. For more information and documentation on this tool, please see [this page](PHX DOC LINK).

To unpack an .era, all you must do is drag the .era file into the tool's gui. The tool will then unpack all of the files contained within the archive to the path specified in the "ERA Expand Path".<br>
 After the files have been extracted, you will find an .eradef file along side the archive's contents. This file is a manifest for all of the files contained within the archive, and can be edited to include new files. All files specified in the .eradef are relative to the file itself. To rebuild an .era, simply drag the .eradef into the tool just as you would do to unpack an .era file. The resulting .era will be put in the specified "ERA Build Output" path.

 You will also come across files with an .xmb extension once you unpack an archive. These files are just compressed XML. To edit these, simply drag them into the tool, just like an .era, and it will spit out an uncompressed .xml file. This file will apear in the same directory as the source .xmb; it is not affected by the "ERA Expand Path". Any .xml file can also be dragged into the tool to produce an .xmb. These are mostly unneeded, however.

### A Decent Text Editor
<img width="1000" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/texteditors.png?raw=true">

Almost all of Halo Wars' data files are in .xml. So with that in mind, it's a good idea to install and use a text editor with syntax highlighting.

Pictured from left to right: [Notepad++](https://notepad-plus-plus.org/downloads/), [Visual Studio Code](https://code.visualstudio.com/download), and [Sublime Text 3](https://www.sublimetext.com/3).

All three of these programs are free, and are excellent programs to edit .xml files. If you have another program that you prefer, you can use that, of course. They are just text files after all.

***

<a name="YourFirstMod"></a>
# Creating Your First Mod
## Setting Up ModManifest

ModManifest is a .txt file that tells the game where to load external content from. This file can automatically found and opened using PHXTool, or alternatively can be found in:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-"C:\Users\'USER'\AppData\Local\Halo Wars" (Steam)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-"C:\Users\'USER'\AppData\Local\Packages\Microsoft.BulldogThreshold_8wekyb3d8bbwe\LocalState" (Windows Store).

Inside of your modmanifest file, you can specify paths for the game to load mods from. Each path must be on it's own line. To disable a path without erasing it, simply put a semi-colon (**;**) in front of it. PHXTool has a gui to automate this process, if you prefer it. It can be accessed by pressing the "Edit ModManifest.txt for ('Version')" button. This button will also create the file if you do not have one already.

**It should be noted that the Windows Store version of the game can _ONLY LOAD MODS FROM FOLDERS IN_ C:\Users\'USER'\AppData\Local\Packages\Microsoft.BulldogThreshold_8wekyb3d8bbwe\LocalState. There is nothing we can do about this.**<br>
For the Steam version however, mod folders can be placed wherever you want. Even on another drive if you have one.