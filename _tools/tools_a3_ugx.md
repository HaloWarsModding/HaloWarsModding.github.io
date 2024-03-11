---
layout: page
title: The Blender UGX Pipeline
showTitle: 1
categories: tools
---

This guide will go into how to use the StumpyUGXPipeline to create new meshes and animations on new or existing rigs.

***

## Setting Up
To get ready, you will first need a few things.<br>
<br>
[Blender 2.91 or higher](https://www.blender.org/download/releases/2-91) <br>
Blender is the 3d package that this tool is designed around. This tutorial will not go in-depth into how to use Blender. It is assumed that you already have a basic understanding of the tool.<br>
<br>
[StumpyUGXPipeline](https://github.com/HaloWarsModding/StumpyUGXPipeline/releases)<br>
StumpyUGXPipeline is a set of tools needed to convert from .dae to .gr2, and then .gr2 to .ugx. It also provides an interface within blender to automate many things.<br>
<br>
Once you have these two tools, you will need to install the Pipeline tool through Blender.<br>
To do this, click the edit tab at the top of Blender, then go down to preferences. In preferences, click add-ons, and at the top of the preferences window, click install.<br>
Then, locate the zip archive and add it. You are now all set.<br>
<br>

***

## Getting Started
### Deciding what to make
When thinking of what you will make with the tools, it is important to know that there are two categories to pick from.<br>
**1)** A new mesh on an existing rig.<br>
or<br>
**2)** A new mesh on a new rig.<br>
This is a very important decision because option 1 requires a little more involvement.<br>
<br>
We will start by importing a marine from HWDE. This was obtained through 3ds Max.<br>If you are using a fully custom mesh and rig you can [skip to the overview](#Overview).<br>
<img width="400" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/ugxpipeline/gettingstarted1.PNG?raw=true"><br>

## HWDE Mesh Gotchas
### Preparing a mesh obtained through the 3ds Max script
If you wish to use a new mesh on existing animations (and thus the existing rig) you must prepare the model.<br>
If it is a custom mesh, it must be in the exact same pose as the target anims rig. If you are targeting the marine, your custom mesh should be in the exact same pose as the HWDE marine mesh obtained through 3ds Max.
To start, you must apply transforms (Ctrl + A) on the rig. This will remove the unncessary scaling.<br>
<img width="300" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/ugxpipeline/apply1.PNG?raw=true"><br>
Then you must remove the parent from the mesh.<br>
<img width="300" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/ugxpipeline/apply2.PNG?raw=true"><br>
Then you must apply (Ctrl + A) **only scale** to the mesh.<br>
<img width="300" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/ugxpipeline/apply3.PNG?raw=true"><br>
Your mesh is now ready to go like any other.<br>

### Quirks
A major quirk is that the maxscript exports meshes flipped on the X axis. Watch out for this, and make sure your normals are correct after correcting this.<br>
Another quick quirk is that sometimes meshes obtained through the 3ds Max script have incorrect bone weighting. Always double check your weighting.

***

<a name="Overview"></a>
## Tool Overview
This guide will assume at this point that you have a rigged mesh ready to go.<br>

### Mesh Settings
In order for your mesh to show up in the correct orientation in game, you must have your mesh's front facing the **negative Y** axis, and right facing the **negative X** axis. Up is obviously positive Z.<br>
Also, a skeleton **is required** for the tool to function, and **all meshes must be skinned**.<br>

### Materials
This tool has a built-in system for materials. It allows you to define all of the settings that the game needs, including texture paths.<br>
You can find the global list of materials in the "World Properties" tab in the properties menu. Here, you can define as many materials as you need for your export.<br>
<img width="300" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/ugxpipeline/material1.PNG?raw=true">
<img width="300" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/ugxpipeline/material2.PNG?raw=true"><br>
If you click on a material, it will show you all of its settings.<br>
First, there are the environment settings. These pertain to how the model shows up in the lit world of Halo Wars.<br><br>
Next, there are several texture paths, each with a UVW velocity (texture scrolling, think shields) and a channel (usage not implemented yet).<br><br>
Here, you can specify the paths to your textures. They must be relative to your mods art folder, and without a file extension. So if your texture is in<br> ```[Mod Folder]/art/unsc/custom/texture.ddx``` you would enter ```unsc/custom/texture```.<br><br>
Lastly, there are flags. These do a number of different things:<br>
**ColorGloss**: Determines if glossyness is colored.<br>
**TwoSided**: If checked the mesh's backfaces will not be culled. Only check if you have a reason to, this increases rendering resources needed for the mesh by times two.<br>
**GlobelEnv:** TBD<br>
**LocalReflection**: Determines if the mesh reflects on itself or not.<br>
**OpacityValid**: TBD <br>
**DisableShadows**: Disables shadows from this model.<br>
**TerainConform**: Makes the mesh into a decal.<br>
**DisableShadowReception**: Disables shadows from showing up on this model.<br>
<br>
Now, you will need every mesh to have a material applied to it in order to export. To do this, just go to the "Object Properties" tab in the properties menu.<br>
<img width="250" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/ugxpipeline/object4.PNG?raw=true"><br>
Here, there is a dropdown that lets you select one of your global materials for this object. You will need a material applied to each object before exporting. Multiple objects can use the same material, 
and only materials that are used in the export will be baked into the .ugx.<br>
<img width="250" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/ugxpipeline/object2.PNG?raw=true"><br>
<br>

### Exporting
All thats left is to export!<br>
Simply find the export menu next to the rest.<br>
<img width="600" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/ugxpipeline/export1.PNG?raw=true"><br>
<br>
Now you will see the export window pop up. You will notice some options.<br>
**Back/Right/Up**: These determine the orientation of the exported model. Note that these are in in-game axis rather than Blender's. The default is good, unless you need something specific.<br>
**Export Meshes**: Toggles generation of a .ugx mesh file. Useful for just exporting animations.<br>
**Selected Only**: Determines if only the selected objects will be exported. Note that you must also select an armature.<br>
**Selected Armature**: Allows you to select the rig you want to include in the .ugx/.uax.<br>
**Exports Animations**: Toggles generation of .uax files.<br>
**All Actions**: If toggled, a .uax will be made for each action in the .blend. Otherwise just uses current action on selected armature.





