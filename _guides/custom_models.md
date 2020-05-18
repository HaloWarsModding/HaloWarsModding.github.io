---
layout: page
title: Creating New Meshes
showTitle: 1
---

This guide will go into how to use the StumpyUGXSDK program to create new meshes and animations for use in Halo Wars: DE.
Creating models is not exactly straight forward, and requires a few hurdles to jump through. Trust us though, it is well worth it.

Click these links to move to a specific part of the tutorial:

[Getting Started](#GettingStarted)<br>
[Installing StumpyUGXSDK](#UGXSDKInstallation)<br>

***

<a name="GettingStarted"></a>
# Setup & Usage

## Tools
Creating models for this game requires 3DSMax 2018 and StumpyUGXSDK, as well as Visual Studio 2017+, and the Granny3D SDK & exporters.

### StumpyUGXSDK
StumpyUGXSDK is a command line tool created to convert Granny Runtime files (.gr2) into Halo Wars' proprietary file format.<br>
Installation of this program can be found [below](#UGXSDKInstallation).<br>

### 3DSMax 2018
3DSMax is a CAD tool created by Autodesk. The 2018 version is required to export the .gr2 files. How you obtain it is up to you.<br>
You will also need the .gr2 exporter plugin. It can be downloaded [here](https://www.mediafire.com/file/rgn93ruk7p00low/3dsmax2018gr2exporter.rar/file) (MediaFire link).

<a name="UGXSDKInstallation"></a>
## Installing StumpyUGXSDK
The download for StumpyUGXSDK can be found [here](https://github.com/HaloWarsModding/StumpyUGXSDK/releases/download/1.0.0/StumpyUGXSDK.exe) (with source available on [GitHub](https://github.com/HaloWarsModding/StumpyUGXSDK)).<br>
It requires the Granny3D SDK by RAD Game Tools to function. It can be downloaded [here](https://www.mediafire.com/file/5pwpeiozx7tvja3/granny2_x64.dll/file) (MediaFire link).<br>
Once you have downloaded the tool and the Granny3D SDK dll, go ahead an place them side-by-side in your desired directory.<br>