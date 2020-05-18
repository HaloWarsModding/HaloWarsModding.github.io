---
layout: page
title: Creating New Meshes
showTitle: 1
---

This guide will go into how to use the StumpyUGXSDK program to create new meshes and animations for use in Halo Wars: DE.
Creating models is not exactly straight forward, and requires a few hurdles to jump through. Trust us though, it is well worth it.

Click these links to move to a specific part of the tutorial:

[Getting Started](#GettingStarted)<br>
[Using StumpyUGXSDK](#UGXSDKInstallation)<br>
[Exporting .gr2 Files](#GR2Export)<br>

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


***
<a name="UGXSDKInstallation"></a>
## Installing StumpyUGXSDK
The download for StumpyUGXSDK can be found [here](https://github.com/HaloWarsModding/StumpyUGXSDK/releases/download/1.0.0/StumpyUGXSDK.exe) (with source available on [GitHub](https://github.com/HaloWarsModding/StumpyUGXSDK)).<br>
It requires the Granny3D SDK by RAD Game Tools to function. It can be downloaded [here](https://www.mediafire.com/file/5pwpeiozx7tvja3/granny2_x64.dll/file) (MediaFire link).<br>

<img width="200" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/stumpyugxsdk.png?raw=true">

Once you have downloaded the tool and the Granny3D SDK dll, go ahead an place them side-by-side in your desired directory.<br>

To use this program, simply open it. You will be greeted with a prompt to type or paste in a path to a .gr2 file.
```
Please enter a path to a .gr2 file.
>>
```
You will then be prompted to specify what you want to export this as.
```
Please select what you want to export this file as: (a = animation | m = mesh)
>>
```
The tool will then convert the .gr2 into either a .uax or .ugx in the exact same path as the input, and will give it the appropriate file extension.

These files can be used in game like any other model or animation file.


***
<a name="GR2Export"></a>
## Exporting .gr2 Files

To export .gr2 Files, you will need 3DS Max 2018, along with the .gr2 exporter found [here](https://www.mediafire.com/file/rgn93ruk7p00low/3dsmax2018gr2exporter.rar/file) The folder in the archive "stdplugin" can be dropped directly into your 3DS Max installation folder. Once you have a satisfactory piece of art, **be sure to run the gr2_export.ms MaxScript file that was included in the StumpyUGXSDK tool download.
(Click "Scripting on the top context menu bar in 3DS Max, then "Run Script").**<br>
Now you are ready to export. Go to "File" => "Export" => "Export..." and set the "Save as type:" option to "Granny Run-time (\*.GR2). Click save and a new menu should pop up.

Under the "File" settings, set yours to match the this:<br>
**NOTE:** the "Tool Coordinate System" option may have to be tweaked in order to show up correctly in game depending on the orientation of your model in 3DS Max

<img width="300" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/gr2expfile.png?raw=true">

Now under "Animations" set it to match this:

<img width="300" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/gr2expanim.png?raw=true">

**NOTE:** Each animation must be exported as it's own .gr2 and processed separately. As long as your model's rig does not change, you are free to edit the base mesh without needing to re-process the animations, and vice-versa.<br>
**NOTE:** Be sure not to exceed 65535 vertices in your model.<br>
**NOTE:** It is necessary to have an idle animation, otherwise the model will show up on it's side in-game. For models that you do not want to animate at all (i.e. props), just change the "Tool Coordinate System" option as mentioned before to achieve the desired orientation.

Now you have a .gr2 file to use in the tool.<br>
Happy modding!