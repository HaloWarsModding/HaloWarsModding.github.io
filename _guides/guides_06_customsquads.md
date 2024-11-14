---
title: Custom Squads
description: Custom Sqauds Description
permalink: /guides/custom-squads
layout: default
nav_order: 6
image: https://raw.githubusercontent.com/HaloWarsModding/HaloWarsModding.github.io/master/resources/images/metadata/header.png
toc: true
---

# How to make your first custom squads 
<span class="label label-blue">Work in Progress</span>

In this guide we'll be making various custom squads, and go over some of the intricacies involved with the squad system. To begin, we'll be looking for the `squads.xml` file, which is found in the data folder.

<img src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/resources/images/squadguide1.png?raw=true" height="256" />

From there, find and pick out the marine squad. This can be done quickly by searching for `unsc_inf_marine_01` with the search function in your text editor of choice. Once you are there, scroll down to the `<Units>` section. This is where the contents of squads are handled. You are able to add more then one unit type to a squad, but we'll go through a few different tests to show off some of the interactions.

<img src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/resources/images/squadguide2.png?raw=true" />

Lets start small. Try increasing the number of units in the squad from 4 to 6, then try launching the game. You'll notice your squad is bigger, and even manages to leave the base without issue! Be mindful that you may not be able to pull this off all the time however... If you were to instead change the number of marines to a higher value, then you'd notice some of them getting stuck inside the base. Depending on the situation, the trapped units may be able to free themselves on their own when the squad finishes training, but this might not always be the case.

<p float="left">
  <img src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/resources/images/squadguide3.png?raw=true" width="384" />
  <img src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/resources/images/squadguide4.png?raw=true" width="384" /> 
</p>

Now set the number of marines down to 2. This time, copy the entire entry for the `<Unit>` within the squad, and add it underneath the existing one. It should now look like this:
```
		<Units>
			<Unit count="2" role="normal">unsc_inf_marine_01</Unit>
			<Unit count="2" role="normal">unsc_inf_marine_01</Unit>
		</Units>
```
Now change the marine in the new line you added to something else; we'll use the ODST in this example, so you would change it to `unsc_inf_odst_01`. When you go back into the game, you'll see that now your marine squads consist of both marines and ODSTs. When you use their ability, you'll also see that the marines will throw grenades while the ODSTs will fire their rockets. This can be taken advantage of in more advanced custom squads, but we won't be going over that in this guide. 

<img src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/resources/images/squadguide5.png?raw=true" />

Now, try replacing the ODSTs with a covenant unit; in this case we'll use the grunt, so replace it with `cov_inf_grunt_01`. When you go to train your marines now, you'll notice the grunts stay stuck in the base while the marines run out properly. This is due to the difference in train animations between the units, which make setting things such as this a bit easier said then done. While this can be fixed, we won't be fixing it in this guide as this is meant to be a brief overview to show what's possible.

<img src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/resources/images/squadguide6.png?raw=true" />

Now, go ahead and reset all the changes we made to the marine. We're now going to test a few other Squad interactions. Try searching for `unsc_veh_warthog_01`, scroll down to the unit section for it, and add a second warthog to the squad. When you go ingame, it might look like theres only 1 warthog, but your second warthog is still there. you can see this if you move the warthog around. Vehicles don't seem to work the same way as infantry do when placed into squads, which makes multi-vehicle squads impossible (with our current knowledge). While this mostly also applies to air units, flood swarms have a system that allows them to work as a multi-unit air squad.

<p float="left">
  <img src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/resources/images/squadguide7.png?raw=true" width="384" />
  <img src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/resources/images/squadguide8.png?raw=true" width="384" /> 
</p>

Before we end things off, lets look into other things that can be changed. The various text IDs correspond to text found in the various stringtable files (each for a different language). This lets you add custom names, descriptions, and roles to your squads. To change the build time, you would adjust the buildpoints; 1 buildpoint will equal 1 second of game time. You can also modify the supply and tech cost, though population cost is handled in `objects.xml`. That should conclude this guide for custom squads, now try experimenting with some stuff on your own!

<p float="left">
  <img src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/resources/images/squadguide9.png?raw=true" width="384" />
  <img src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/resources/images/squadguide10.png?raw=true" width="384" />
  <img src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/resources/images/squadguide11.png?raw=true" width="384" />
  <img src="https://github.com/HaloWarsModding/HaloWarsModding.github.io/blob/master/resources/images/squadguide12.png?raw=true" width="384" />
</p>
