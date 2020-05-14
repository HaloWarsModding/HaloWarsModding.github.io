---
layout: page
title: Tactics Files
showTitle: 1
---

This page will go through the basics of creating and editting tactics files. 

Click these links to move to a specific part of the tutorial:

[What are Tactics Files?](#WhatareTactics) <br>[The Components of a Tactics File](#ComponentsofTactics)

***

<a name="WhatareTactics"></a>
## What are Tactics Files?

Tactics files are an absolutely essential part of any unit. They enable units to attack, use abilities, gather resources, and more. 

Each unit has its own .tactics file, each of which is referenced in that unit's objects.xml entry. Every tactics is found in the "tactics" folder: 
  (data/tactics/example_01.tactics)


***

<a name="ComponentsofTactics"></a>
# The Components of a Tactics File
## "Weapon"
This portion of the file assigns the characteristics of the "weapon" used for each of the unit's attacks, including:

  > Damage, Accuracy, Max and Min Range, Physics, Area of Effect info, Impact and Projectile Effects, Attack Cooldown, Weapon Type, and Target Priority
  
Most of these are pretty self explanatory, but there is a few things to go over. 
  * The "WeaponType" tag  refers to entries in the weapontypes.xml file, found in the data folder. Each weapon type specifies how damage is multiplied against certain "Damage Types". Each unit or building is assigned a damage type in objects.xml. For more info, click **Insert link to objects guide here**.
  * Target Priority tags refer to how likely the unit is to target the specified unit type, when given the option. 

## "Action"


## "Tactic/TargetRule"

