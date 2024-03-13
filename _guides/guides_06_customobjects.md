---
title: Creating Custom Objects
description: Creating Custom Objects Description
permalink: /guides/custom-objects
layout: default
nav_order: 6
image: https://raw.githubusercontent.com/HaloWarsModding/HaloWarsModding.github.io/master/resources/images/metadata/header.png
toc: true
---

# Creating Custom Objects Guide

Work In Progress
{: .label .label-blue }

Objects.xml is a massive file containing every single object in the game, such as units, structures, and projectiles. By following this guide, you’ll learn the basics as how to create the foundations for all sorts of custom objects, as well as how to fix some of the common issues that may arise when creating these custom objects.
If you'd like to jump to a particular section, then you can use the table of contents found below.

- [Shared Attributes](#shared-attributes)
- [Custom Units](#custom-units)
- [Custom Structures](#custom-structures)
- [Custom Garrisons](#custom-garrisons)
- [Custom Scenery Objects](#custom-scenery-objects)
- [Custom Projectiles](#custom-projectiles)
  - [Custom Particles](#custom-particles)
- [Troubleshooting Common Issues](troubleshooting-common-issues)

# Shared Atributes
Most objects in the game share the same two core attributes: An `<Obstruction Radius>` and a `<Visual>`.
The `<Obstrution Radius>` handles the collision box for any given object, and has a major factor in unit maneuverability. The `<Visual>` on the other hand is a bit more straightforward, as it contains the file path that the object will use to retrieve its model and animations.
However, these two attributes aren't the only ones shared between objects. In fact, units and structures in particular share all sorts of tags. For a more in depth explanation for what the many various tags within objects.xml do, check the [Objects.xml documentation](_docs/objects) for more info, as this guide will only go over the basics for the most important things among these tags.

A brief overview of the various common shared tags:

`<Hardpoint>`

Hardpoints are used by all sorts of turret-like objects attached to structures and units. They are also used by certain air units like the Pelican to control wings and other similar parts. These are used to help distinguish turrets from a model, and allow said turrets to turn independently from the main model. They also assist infantry in that they allow them to attack while moving.

`<Hitpoints>`

Hitpoints dictate the **BASE** health of an object. Various external factors such as `techs.xml` and `aidifficultysettings.xml` can then modify this base value and cause it to be different ingame.

`<ObjectClass>`

The Object Class dictates what kind of object that particular asset is, and it enables and disables various tags depending on the input. Making something use an object class that its not meant to can have unexpected results!

`<MovementType>`

An Object's Movement Type determines how it moves around the map, whether it flies, stays on the ground, or if it crawls over terrain. This often works alongside an objects `<PhysicsInfo>`.

`<Tactics>`

An object can't attack without tactics. It handles all of an object's weapons and the damage they deal, as well as what enenmies they should use which weapons on. It also handles supportive abilites, such as self healing, cyclops repairing, and passive projectile deflections.

# Custom Units
Custom Units are composed of many components that spread across a few files, these additional files are: `squads.xml` and `techs.xml`, though every combat unit will additionally require a `.tactics` file. While it may seem overwhelming to create custom units based on that description, its actually
much easier then it sounds, since you should always make a copy of an existing unit that you can use as a baseline to then turn into your custom unit.

- `<PhysicsInfo>`/`<PhysicsReplacementInfo>`
  - Physics are one of the most defining attributes of any particular unit, as the physics applied can drastically affect how the unit visually moves on the battlefield. also controls how wheels and treads function on the craft. Its not a rare sight to see a particlar set of physics used by only a single unit. The Warthog is a good example of such, where its physics allow it to drive around erratically and generally handle much like a Warthog does in the mainline games.

# Custom Structures
Custom Structures are spread across similar files much like Custom Units, though they do not require entries in `squads.xml`.

# Custom Garrisons
Custom Garrisons are a bit easier then Custom Structures, as you don't need to worry about making them available to train through `techs.xml`.

# Custom Scenery Objects
Scenery Objects are by far the easiest to set up, as the only external file usually needed for them would be a `<visual>` (which most objects have anyway).

# Custom Projectiles
Custom Projectiles are fairly straightforward to create, and have a fair few settings to experiment with to adjust the projectile as you wish. Don't forget that some settings for the projectile are also controlled in the `.tactics` file as well!

## Custom Particles
Custom Particle effects can be very complex, and so we instead insist that you check out the [Particle File documentation](_docs/pfx) for an in-depth explanation on how these files can be customized.

# Troubleshooting Common Issues
Often when setting up custom objects, you may run into all sorts of various issues ranging from game crashes to being unable to train your custom object. This section aims to fix to help you find a fix these issues and will be expanded on as more issues arise and are solved.
These troubleshooting options are set up with custom units in mind, though many of them can be applied to other object types. 

**Game Crashes before main menu loads**

- There's an error in your `Objects.xml` and/or `Techs.xml` that causes the file to not format correctly. Ensure all brackets are enclosed and that no objects share completely identical names.

**Game Crashes at match start (when unit is started spawned in)**/**Game Crashes when unit is trained**

- There is most likely an issue within the object's `.vis`. Ensure that there isn't an infinite loop of modelrefs, as this is the most probable cause. Sometimes this crash can rarely come from very specific animations under very specific circumstances. Its not well known as to what this affects, though one known example would be the `RotaryMachinegunAttack` animation from the Warthog being used on a Warthog Turret placed on an Elephant.

**Game Crashes when unit attacks and/or is attacked**

- This is likely connected to an invalid or incomplete `Damagetype` and/or `Weapontype` being used by one or more units involved in combat when the crash occurrs.

**Unit has no model, but is selectable**

- There is an error in the object's `.vis` that causes it to become invalid, causing no model to appear. Make sure all brackets close properly.

**Unit isn't attacking and/or can't be ordered to attack**

- The unit's `.tactics` file is invalid, or your attacks within were not set up properly. Ensure all brackets close properly and that your actions are properly linked to your targetrules.

**Unit is aiming at enemies but not firing.**

- The animation isn't set up properly in the `.vis`. Ensure that the main model also has attack animation entries on it.

**The unit jitters when trying to attack**

- One or more of the unit's Hardpoints within are not set up properly. Ensure the hardpoints in `objects.xml` properly link to model names in the `.vis`, and that they are correctly referenced by weapons in the `.tactics`

**The unit isn't appearing in the circle menu**

- You didn't use `commandenable` in `techs.xml` to allow the unit to appear in the circle menu. Depending on the use case, this can usally be inserted into `unsc_basic`/`cov_basic`, or into a specific leader's leader tech.

**The unit is in the circle menu, but isn't trainable**

- You may have not set up the `enable` properly in `techs.xml`. Ensure its directing to both your unit and the place where it is built.

(To be expanded)
