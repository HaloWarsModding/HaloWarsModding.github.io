---
layout: page
title: The Blender UGX Pipeline
showTitle: 1
---

This guide will go into how to use the StumpyUGXPipeline to create new meshes and animations on new or existing rigs.

***

<a name="Setting Up"></a>
## Setting Up
To get ready, you will first need a few things.<br>
[Blender 2.91 or higher](https://www.blender.org/download/releases/2-91) <br>
Blender is the 3d package that this tool is designed around. This tutorial will not go in-depth into how to use Blender. It is assumed that you already have a basic understanding of the tool.<br>
<br>
[StumpyUGXPipeline](TODO)<br>
StumpyUGXPipeline is a set of tools needed to convert from .dae to .gr2, and then .gr2 to .ugx. It also provides an interface within blender to automate many things.<br>
<br>
Once you have these two tools, you will need to install the Pipeline tool through Blender.<br>
To do this, click the edit tab at the top of Blender, then go down to preferences. In preferences, click add-ons, and at the top of the preferences window, click install.<br>
Then, locate the zip archive and add it. You are now all set.<br>
<br>

<a name="Getting Started"></a>
## Getting Started
### Deciding what to make<br>
When thinking of what you will make with the tools, it is important to know that there are two categories to pick from.<br>
1) A new mesh on an existing rig.<br>
or<br>
2) A new mesh on a new rig.<br>
This is a very important decision because option 1 requires a little more involvement.<br>
<br>
We will start by importing a marine form HWDE.<br>
<img width="400" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/ugxtoolchain/gettingstarted1.PNG?raw=true"><br>
**Note**: A skeleton **is required** for the tool to function, and **all meshes must be skinned**.<br>
This guide will assume at this point that you have a rigged mesh ready to go.<br>

## HWDE Mesh Gotchas
### 
If you wish to use a new mesh on existing animations (and thus the existing rig) you must prepare the model a little bit.<br>
To start, you must apply transforms (Ctrl + A) on the rig. This will remove the unncessary scaling.<br>
<img width="400" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/ugxtoolchain/apply1.PNG?raw=true"><br>
Then you must remove the parent from the mesh.<br>
<img width="400" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/ugxtoolchain/apply2.PNG?raw=true"><br>
Then you must apply the **scale only** to the mesh.<br>
<img width="400" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/ugxtoolchain/apply3.PNG?raw=true">
