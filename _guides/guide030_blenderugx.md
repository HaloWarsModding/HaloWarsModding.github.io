---
layout: page
title: The Blender UGX Pipeline
showTitle: 1
---

This guide will go into how to use the StumpyUGXPipeline to create new meshes and animations on existing or new rigs.

***

<a name="Setting Up"</a>
## Setting Up
To get ready, you will first need a few things.
[Blender 2.91 or higher] (https://www.blender.org/download/releases/2-91/)
Blender is the 3d package that this tool is designed around. This tutorial will not go in-depth into how to use Blender. It is assumed that you already have a basic understanding of the tool.

[StumpyUGXPipeline] (TODO)
StumpyUGXPipeline is a set of tools needed to convert from .dae to .gr2, and then .gr2 to .ugx. It also provides an interface within blender to automate many things.

Once you have these two tools, you will need to install the Pipeline tool through Blender.
To do this, click the edit tab at the top of Blender, then go down to preferences. In preferences, click add-ons, and at the top of the preferences window, click install.
Then, locate the zip archive and add it. You are now all set.

<a name="Getting Started"</a>
## Getting Started
### Deciding what to make
When thinking of what you will make with the tools, it is important to know that there are two categories to pick from.
1) A new mesh on an existing rig.
or
2) A new mesh on a new rig.
This is a very important decision because option 1 requires a little more involvement.

We will start by importing a marine form HWDE.
<img width="200" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/gettingstarted1.png?raw=true">
**Note**: A skeleton **is required** for the tool to function, and **all meshes must be skinned**.
This guide will assume at this point that you have a rigged mesh ready to go.
