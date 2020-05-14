---
layout: page
title: Getting Started
---

# Getting Started
Whether you're a new modder, or just need to brush up on the basics, this is the place to be.
This page will focus on what you need to begin making a mod. 

If you are a beginner, we recommend reading this page top to bottom twice before moving on to anything else, but if you're here for something specific, you can jump to the desired section by clicking on one of the following:

[Whats Needed?](#WhatsNeeded) **\|** [JUMP2](#)

***

<a name="WhatsNeeded"></a>
## Whats Needed?
### PHXTool - For Extracting Halo Wars: DE Content
<img width="422" height="279" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/phxtool.png?raw=true">

The absolute backbone of Halo Wars modding is the PHXTool by kornman00. This tool lets you unpack and re-pack Halo Wars' resource archives (.era files) so that you can make use of them in new content, or edit them for existing content. It can be downloaded [here](NEED LINK).

The tool has several options. The 'ERA Expand Path' field allows you to specify where the archive will be dumped to. It is recommended to set this to an "Extract" folder either:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- In your game's install directory (Steam users \| Example: C:\Program Files (x86)\Steam\steamapps\common\HaloWarsDE).<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- In your documents folder (Windows Store Users \| C:\'USER'\Documents).

The "ERA Build Path" field allows you to specify where you want an archive to be spit out when it is re-built. This feature is hardly ever needed, but is still sometimes useful. It is recommended to be set to your game's install directory. **Note: Always make a backup of all your files before modifying anything. Rebuilding an archive into your install directory will overwrite the original file unless "Don't overwrite existing files" is checked.**

For the basics, none of the flags are required. For more information and documentation on this tool, please see [this page](PHX DOC LINK).

To unpack an .era, all you must do is drag the .era file into the tool's gui. The tool will then unpack all of the files contained within the archive to the path specified in the "ERA Expand Path".<br>
 After the files have been extracted, you will find an .eradef file along side the archive's contents. This file is a manifest for all of the files contained within the archive, and can be edited to include new files. All files specified in the .eradef are relative to the file itself. To rebuild an .era, simply drag the .eradef into the tool just as you would do to unpack an .era file. The resulting .era will be put in the specified "ERA Build Output" path.

### A Decent Text Editor
<img width="1000" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/texteditors.png?raw=true">

