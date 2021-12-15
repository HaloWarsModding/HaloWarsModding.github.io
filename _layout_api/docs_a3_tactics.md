---
layout: page
title: Tactics
showTitle: 1
---

This page will go through the basics of creating and editting tactics files. 

Click these links to move to a specific part of the tutorial:

[What are Tactics Files?](#WhatareTactics) <br>[The Components of a Tactics File](#ComponentsofTactics)

***

<a name="WhatareTactics"></a>
## What are Tactics Files?

Tactics files are an absolutely essential part of any unit. They enable units to attack, use abilities, gather resources, and more. 

Each unit has its own .tactics file, each of which is referenced in that unit's `objects.xml` entry. Every tactics is found in the "tactics" folder: 
  `(data/tactics/example_01.tactics)`


***

<a name="ComponentsofTactics"></a>
# The Components of a Tactics File
## Weapons
```xml
<Weapon>
	<Name>AssaultRifle</Name>
	<AttackRate>1</AttackRate>
	<DamagePerSecond>11</DamagePerSecond>
	<WeaponType>SmallArms</WeaponType>
	<Projectile>fx_proj_rifle_01</Projectile>
	<ImpactEffect size="Small">SmallArmsBullet</ImpactEffect>
	<MaxVelocityLead>10</MaxVelocityLead>
	<MaxRange>25</MaxRange>
	<Accuracy>0.1</Accuracy>
	<MaxDeviation>3</MaxDeviation>
	<MovingAccuracy>0.05</MovingAccuracy>
	<MovingMaxDeviation>4.5</MovingMaxDeviation>
	<AccuracyDistanceFactor>0.5</AccuracyDistanceFactor>
	<AccuracyDeviationFactor>0.33</AccuracyDeviationFactor>
	<EnableHeightBonusDamage />
	<VisualAmmo>8</VisualAmmo>
	<ReloadAnimation>AssaultRifleReload</ReloadAnimation>
	<TargetPriority type="Infantry">5</TargetPriority>
	<TargetPriority type="Building">-3</TargetPriority>
	<Hardpoint>Torso</Hardpoint>
	<SmallArmsDeflectable />
</Weapon>
```

<br>
This portion of the file assigns the characteristics of the "weapon" used for each of the unit's attacks, including:

  > Damage, Accuracy, Max and Min Range, Physics, Area of Effect info, Impact and Projectile Effects, Attack Cooldown, Weapon Type, Hardpoint, and Target Priority
  
Most of these are pretty self explanatory, but there is a few things to go over. 
  * Hardpoints are extremely important to take note of. This refers to a hardpoint defined in `objects.xml`, and is the point at which the unit is able to turn when using a particular weapon. This can be a torso for an infantry unit or a turret on a Warthog or Scorpion, for example. If a unit's hardpoints in their tactics is different from the one in their objects entry, then it won't work properly.
  * The "WeaponType" tag  refers to entries in the `weapontypes.xml` file, found in the data folder. Each weapon type specifies how damage is multiplied against certain "Damage Types". Each unit or building is assigned a damage type in `objects.xml.` For more info, click **Insert link to objects guide here**.
  * Target Priority tags refer to how likely the unit is to target the specified unit type, when given the option. 
  
## Actions
```xml
<Action>
	<Name>AssaultRifleAttackAction</Name>
	<ActionType>RangedAttack</ActionType>
	<Anim>AssaultRifleAttack</Anim>
	<ReloadAnim>AssaultRifleReload</ReloadAnim>
	<Weapon>AssaultRifle</Weapon>
	<MainAttack />
</Action>
``` 
<br>
Actions connect a weapon to the unit's animations, as well as enable the unit to use certain abilities or perform more general actions, such as garrisoning cover or gathering supplies. This is also where characteristics relating to an action itself is modified, such as a Warthog's machine gun continuing to fire when switching targets.

There are many different types of attacks, so feel free to look through different tactics files to familiarize yourself with them. Many of them are used in combination with other types, particularly in vehicles. Let's go through a few examples.

``` xml
<Action>
	<Name>CannonAttackAction</Name>
	<ActionType>SlaveTurretAttack</ActionType>
	<Anim>CannonAttack</Anim>
	<Weapon>Cannon</Weapon>
</Action>
<Action>
	<Name>MachinegunAttackAction</Name>
	<ActionType>RangedAttack</ActionType>
	<Anim>MachinegunAttack</Anim>
	<Weapon>Machinegun</Weapon>
	<SlaveAttackAction>CannonAttackAction</SlaveAttackAction>
	<Strafing maxDistance="20" turnRate="90" trackingSpeed="40" jitter="20" />
	<PersistBetweenOpps />
	<MainAttack />
</Action>
```
<br>
  * First off, there is the "SlaveTurretAttack" used by the Scorpion's cannon. The MG uses the standard "RangedAttack", which is exactly as it sounds. In addition, the MG attack action contains `<SlaveAttackAction>`, which links the cannon to the MG. Wherever the MG attacks or turns, the cannon will follow. The MG also has the `<MainAttack>` tag, which means that this attack will be the one that is prioritized when the unit is directed to attack an enemy. Because the cannon is a slave attack, it does not need a target rule (explained below) or a MainAttack tag, as it does not itself target anything, it just uses the same target as the MG.
  
  ``` xml
<Action>
	<Name>FrontMGAttackAction</Name>
	<ActionType>RangedAttack</ActionType>
	<PersistentActionType>SecondaryTurretAttack</PersistentActionType>
	<Anim>MachinegunAttackFront</Anim>
	<Weapon>FrontMG</Weapon>
	<MainAttack />
	<DisableAttackWaitTimer />
	<PersistBetweenOpps />
</Action>
```
  <br>
  * Another important attack type is the "SecondaryTurretAttack". Elephants, for example, use this for each of their machine gun attacks. An important thing to note is that you should avoid using the MainAttack tag with secondary turret attacks. If you have multiple secondary turret attacks on a single unit, like the Elephant does, then they will all be able to attack different units simultaneously, but only if they do not use the MainAttack tag. By default, Elephants do have the tag, which is why there are times when one turret is left unable to attack.

## Persistent Actions and Target Rules
``` xml
<TargetRule>
	<Relation>Enemy</Relation>
	<Action>AssaultRifleAttackAction</Action>
	<SquadMode>Normal</SquadMode>
</TargetRule>
```
<br>
The Tactic section determines the rules for how an action is performed. There are 3 main tags here:
  * `<PersistentAction>`
  * `<PersistentSquadAction>`
  * `<TargetRule>`
  
It is important to use the appropriate type of persistent action for each action type because it make not work properly if the wrong one is used. Actions such as cloaking will use this.

Target Rules are used far more commonly. They are used to determine the following:
  * What type of unit is a viable target for an attack
  * Whether an action should be activated only through the unit's "Y ability"
  * The squad mode (normal, cover, or power) a unit must be in for the action to be used
  * The relationship the target has to the unit (enemy, ally, or nonplayer)
