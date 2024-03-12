---
title: Importing Skinned Meshes 
description: Skinned Meshes Description
permalink: /guides/importing-skinned-meshes
layout: default
nav_order: 4
image: https://raw.githubusercontent.com/HaloWarsModding/HaloWarsModding.github.io/master/resources/images/metadata/header.png
toc: true
---

# Importing Skinned Meshes 

Deprecated
{: .label .label-red }

This guide will explain how to import skinned meshes for use in Halo Wars, specifically ones to use with base-game animations. If you want to use your own animations, refer to the "Creating New Meshes" guide.

Click these links to move to a specific part of the tutorial:

[Requirements](#Requirements)<br>
[Importing the Models](#ModelImport)<br>
[Editting the Models](#EdittingtheModels)<br>

***

<a name="Requirements"></a>
# Requirements
Follow the "Creating New Meshes" guide first.

You'll need 3ds Max 2018 and Blender for this tutorial. Most of the work will be done in Blender, but you'll need 3ds Max for reasons explained in the "Creating New Meshes" guide.

***
<a name="ModelImport"></a>
## Importing the Models

You'll need two models for this tutorial, one from the base game, and one you want to import. Be sure to use a model from Halo Wars that most closely matches the one you are importing.

In order to get models from Halo Wars, you'll need to open 3ds Max and run the script called "ugx_import.ms". The script comes with the StumpyUGXSDK archive you downloaded from the "Creating New Meshes" guide.
To run the script, simply find "Scripting" in the ribbon at the top of 3ds Max, then click "Run Script", and find the script where you extracted the previously mentioned archive.

After running the script, you'll be greeted with a window. Navigate to the .ugx file (the model) that you wish to use, and open it. It will take a few seconds to load the model, but once it has been loaded in 3ds Max, you will see a list of bones and objects on the left.
You will see "Main Root". Select it, right click, and delete it. Once done, go to "File -> Export -> Export..." export the model as an .FBX.

Open Blender and import both the Halo Wars model, and the one you want to import.

***
<a name="EdittingtheModels"></a>
# Editting the Models
Now that you have both models in Blender, you will need to scale, rotate, and then pose your imported model to match the Halo Wars model. 

Select your imported model, then click "object mode" at the top left of the screen, then click "edit mode". Just to the right of that, click "Select", then "Select All". 
Now you may rotate and scale your model. 
Press R on your keyboard to rotate, then X,Y, or Z to select the axis by which you want to rotate by, then type the degrees by which you want to rotate, then press enter.
Press S to scale, then type the percentage that you want to scale by, then press enter.
You can use your mouse to rotate or scale as well.

If your model already has bones/armature, then you also need to scale and rotate that by the same amount as the mesh. Note that you must go back to object mode in order to select a different object, but you need to be in edit mode to properly scale and rotate the objects.

Now you must pose you model to match the Halo Wars model. For now, it is a good idea to hide the Halo Wars model and it's armature so it isnt in your way. If your mesh already has armature, you may go ahead and pose it. Get it as close to the other model as possible, as this will make it look better in game.
If your model does not have armature, navigate to object mode and click "add", then "armature". Create some basic bones along the spine, head, legs, and arms. Dont worry about making them perfect, these will be deleted right after you pose the model.
Take note of the names of the bones from the Halo Wars model, as it will be easier to go ahead and name your temporary bones after them. For Example, most right upperarm bones are named "Bip01 R Upperarm". 

* It is important that you name the right side bones as left, and vice versa, as the model is flipped in game.

Once the bones have been created and named, navigate to object mode. Select the mesh, then the armature, and press "Ctrl P" on your keyboard. On the menu that pops up, click "with Empty Groups" under "Armature Deform".
Now, select just the mesh and navigate to the "Object Data Properties", shown in the image below. 

<img width="403" height="563" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/resources/images/skinmeshes1.png?raw=true">

You will see a list of Vertex Groups. Vertex groups are the what determines the influence that a particular bone has on deforming the mesh. 
You will now want to click on object mode again, but select "Weight Paint" in the drop-down menu. Use weight paint to paint around the areas that each bones should have influence over. Be sure not to leave gaps on the mesh, as those gaps wont be affected by animations or posing.
After you've finished weight painting for each bone, you may navigate to object mode and select the armature, then change to Pose Mode. Pose the model.

Now you need to save the new pose as the "rest pose". In object mode, select the mesh and go to the modifier properties, as shown in the image below.

<img width="403" height="563" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/resources/images/skinmeshes2.png?raw=true">

There should already be a modifier there. Click "Copy", then click "Apply" on the top modifier. The mesh will now be incorrectly deformed. Navigate again to pose mode. Just to the right of the mode switching menu is a "Pose" button. Click it, then click "Apply", then "Apply Pose as Rest Pose".
Once finished, delete the armature you created earlier. If your mesh snaps to a different rotation or scale, simply scale and rotate it back in edit mode, like we did earlier. 

Navigate to Object mode and click your mesh, then the armature of the Halo Wars model. Once again, press "Ctrl P" and select "Armature Deform with Empty Groups".
Now you'll need to adjust the weight paint and vertex groups of the mesh to match those of the original Halo Wars model. You may need to navigate back and forth between both models to ensure you get the weight paint correct.
After this is done, you may delete the Halo Wars model and export yours as an FBX.

Back in 3ds Max, delete the model and bones of the Halo Wars model if you haven't already, you'll want a clear scene. Then import the FBX you just created in Blender. Once imported, it is absolutely necessary that you delete the "Main Root", as you did before. 
Now you need to run the "gr2export.ms" script in the same you did earlier with the ugx import script. Now, export the model as a .gr2 and follow the "Creating New Meshes" guide to get the model into the game.

