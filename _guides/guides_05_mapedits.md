---
title: Making Map Edits
description: Map Edits Description
permalink: /guides/map-edits
layout: default
nav_order: 5
image: https://raw.githubusercontent.com/CinderellaKuru/Dev.HaloWarsModding/master/resources/images/metadata/header.png
toc: true
---

# Making Map Edits

Deprecated
{: .label .label-red }

# Creating a basic new map

This guide assumes you know how to extract game files and have a general understanding of where files are located. I use notepad++ but you may use another text editing tool. To create a new map, you need the map you want extracted. I will be using bloodgulch.era.
You will also need to convert the scenario file from xmb to just scn. To do this, you have to drag and drop the scenario file into the PhxGui tool. It will auto convert the file. The last files you will need are scenariodescriptions.xml.xmb and stringtable-en.xml.xmb. You may use another stringtable file that contains your language you use for the game. For those files, you will also need to drag and drop it in the tool to change it to a XML file. 
***
To begin the process, head to the design folder that is in your scenario folder. Create a new folder with whatever name you choose. Copy all the files in the blood gulch folder and paste them into your new folder. You may use another map if you choose but for this guide we will use blood gulch. Open PhxGui tool, then drag and drop the bloodgulch.scn.xmb into it. It will convert it to a .scn file. Delete the bloodgulch.scn.xmb in the new map folder since you do not need the xmb version. The next step is to head to your data folder with the scenariodescriptions.xml.xmb, drag and drop it in the tool for it to convert to the xml version. When that is done, you need to open it and you will see a lot of lines full of data for the maps. All you need to do, is enter in a new line.

<img width="1000" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/md7.PNG?raw=true">

You can either enter in the ScenarioInfo manually or copy an existing line and edit parts of it. Let's take and edit the file location of the new line and change it with our new location for the new map. It should look like this:

<img width="1000" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/md3.PNG?raw=true">

The last thing we need to do with this file, is to change the name and description of the map. That would be what NameStringID and InfoStringID hold. For this file, it uses numbers to represent the name and description of maps. You can find what those numbers mean in the stringtable-en.xml.xmb file or the file you chose for your language. Drag and drop the stringtable file of your choice into the PhxGui tool to convert it to XML. You need to give the new map text names as well as descriptions. It is best to enter in new lines at the bottom of the stringtable-en.xml file. Take some existing lines from the other maps in scenariodescriptions. Copy and paste them at the bottom of the file but make sure to change it to what you like.

<img width="1000" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/md4.PNG?raw=true">

Once that is done, you need to go back to scenariodescriptions.xml and change the NameStringID to your new map's name. Also change the InfoStringID to the new description. The last step is to update the eradef file since now instead of using the xmb version of the files, we are using the converted versions. Open up root.eradef, search up scenariodescriptions.xml, and remove the xmb part of it.

<img width="auto" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/md5.PNG?raw=true">

You will also need to do this for the stringtable file of your language. Just search it up and remove the xmb part if it still has it in root.eradef. When that is done, this is what your folder should look like.

<img width="auto" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/md6.PNG?raw=true">
***

If you have done this correctly, you can start the game and see your new map you created in game. This guide is for a basic map. If you want to edit and add new things to your new maps, keep a look for more guides coming soon.

<img width="1000" height="auto" src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/assets/images/md8.jpg?raw=true">