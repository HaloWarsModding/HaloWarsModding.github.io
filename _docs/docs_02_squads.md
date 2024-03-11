---
title: Squads
description: Squads Description
permalink: /docs/squads
layout: default
image: resources\images\metadata\header.png
toc: true
---

This page will go through the basics of creating, editing and understanding the squads.xml file.



What is the Squads.xml file?


The Squad.xml file stores data and attributes for units that is not present in Objects.xml like how much the unit costs, training time and how many units are in a set squad.

Every infantry, vehicle and air unit in the game has entries in Squads.xml





The Components of a unit in a Squads.xml file.

```xml
</Squad>
	<Squad name="unsc_inf_marine_01" formationType="Flock" dbid="877">
		<PortraitIcon>ui\flash\HUD\hud_menu\hud_menu_icons\final_unsc\inf_marine</PortraitIcon>
		<MinimapIcon size="8">Circle</MinimapIcon>
		<MinimapScale>1</MinimapScale>
		<DisplayNameID>3000</DisplayNameID>
		<RolloverTextID>3001</RolloverTextID>
		<StatsNameID>25679</StatsNameID>
		<RoleTextID>500</RoleTextID>
		<BuildPoints>8</BuildPoints>
		<Cost resourcetype="Supplies">100</Cost>
		<SubSelectSort>3000</SubSelectSort>
		<LeashDistance>55</LeashDistance>
		<LeashDeadzone>25</LeashDeadzone>
		<LeashRecallDelay>2500</LeashRecallDelay>
		<AggroDistance>35</AggroDistance>
		<Birth anim0="Train" anim1="Train" anim2="TrainAirlock" anim3="ElephantTrain" trainerAnim="TrainInfantry" spawnpoint="bone_spawnPoint02" endPoint="bone_endPoint02">Trained</Birth>
		<HPBar offset="0,9,0">UNSC_Health</HPBar>
		<AbilityRecoveryBar Centered="UNSC_Ability_Centered">UNSC_Ability</AbilityRecoveryBar>
		<VeterancyBar Centered="UNSC_Star_Centered">UNSC_Star</VeterancyBar>
		<Units>
			<Unit count="4" role="normal">unsc_inf_marine_01</Unit>
		</Units>
		<Sound Type="StartMove">play_ani_marine_walk_01</Sound>
		<Sound Type="StopMove">stop_ani_marine_walk_01</Sound>
		<Sound Type="StopExist">stop_ani_marine_exist</Sound>
		<Sound Type="MoveChatter">play_unsc_batchat_marines_move</Sound>
		<Sound Type="MoveChatter" World="Harvest">play_unsc_batchat_marines_world_harvest_moving</Sound>
		<Sound Type="MoveChatter" World="Arcadia">play_unsc_batchat_marines_world_arcadia_moving</Sound>
		<Sound Type="MoveChatter" World="SWI">play_unsc_batchat_marines_world_swi_moving</Sound>
		<Sound Type="MoveChatter" World="SWE">play_unsc_batchat_marines_world_sw_moving</Sound>
		<Sound Type="AttackChatter">play_unsc_batchat_marines_action</Sound>
		<Sound Type="AttackChatter" Squad="cov_air_banshee_01">play_unsc_batchat_marines_banshee_taunt</Sound>
		<Sound Type="AttackChatter" Squad="cov_inf_brute_01">play_unsc_batchat_marines_brute_taunt</Sound>
		<Sound Type="AttackChatter" Squad="cov_veh_brutechopper_01">play_unsc_batchat_marines_chopper_taunt</Sound>
		<Sound Type="AttackChatter" Squad="cov_inf_eliteCommando_01">play_unsc_batchat_marines_elite_taunt</Sound>
		<Sound Type="AttackChatter" Squad="cov_veh_ghost_01">play_unsc_batchat_marines_ghost_taunt</Sound>
		<Sound Type="AttackChatter" Squad="cov_inf_grunt_01">play_unsc_batchat_marines_grunt_taunt</Sound>
		<Sound Type="AttackChatter" Squad="cov_inf_hunter_01">play_unsc_batchat_marines_hunter_taunt</Sound>
		<Sound Type="AttackChatter" Squad="cov_inf_jackal_01">play_unsc_batchat_marines_jackal_taunt</Sound>
		<Sound Type="AttackChatter" Squad="cov_veh_locust_01">play_unsc_batchat_marines_locust_taunt</Sound>
		<Sound Type="AttackChatter" Squad="cov_veh_scarab_01">play_unsc_batchat_marines_scarab_taunt</Sound>
		<Sound Type="AttackChatter" Squad="cov_inf_suicidegrunt_01">play_unsc_batchat_marines_grunt_taunt</Sound>
		<Sound Type="AttackChatter" Squad="cov_air_vampire_01">play_unsc_batchat_marines_vampire_taunt</Sound>
		<Sound Type="AttackChatter" Squad="cov_veh_wraith_01">play_unsc_batchat_marines_wraith_taunt</Sound>
		<Sound Type="AttackChatter" Squad="FlyingFlood">play_unsc_batchat_marines_flyingflood_taunt</Sound>
		<Sound Type="AttackChatter" Squad="Flood">play_unsc_batchat_marines_flood_taunt</Sound>
		<Sound Type="AttackChatter" Squad="Forerunner">play_unsc_batchat_marines_forerunner_taunt</Sound>
		<Sound Type="MoveAttackChatter">play_unsc_batchat_marines_moveattack</Sound>
		<Sound Type="IdleChatter">play_unsc_batchat_marines_idle</Sound>
		<Sound Type="IdleChatter" World="Harvest">play_unsc_batchat_marines_world_harvest_idle</Sound>
		<Sound Type="IdleChatter" World="Arcadia">play_unsc_batchat_marines_world_arcadia_idle</Sound>
		<Sound Type="IdleChatter" World="SWI">play_unsc_batchat_marines_world_swi_idle</Sound>
		<Sound Type="IdleChatter" World="SWE">play_unsc_batchat_marines_world_sw_idle</Sound>
		<Sound Type="KilledEnemy">play_unsc_batchat_marines_killenemy</Sound>
		<Sound Type="KilledEnemy" Squad="FlyingFlood">play_unsc_batchat_marines_flyingflood_killed</Sound>
		<Sound Type="KilledEnemy" Squad="Flood">play_unsc_batchat_marines_flood_killed</Sound>
		<Sound Type="KilledEnemy" Squad="Forerunner">play_unsc_batchat_marines_forerunner_killed</Sound>
		<Sound Type="KilledEnemy" Squad="cov_air_banshee_01">play_unsc_batchat_marines_banshee_killed</Sound>
		<Sound Type="KilledEnemy" Squad="cov_inf_brute_01">play_unsc_batchat_marines_brute_killed</Sound>
		<Sound Type="KilledEnemy" Squad="cov_veh_brutechopper_01">play_unsc_batchat_marines_chopper_killed</Sound>
		<Sound Type="KilledEnemy" Squad="cov_inf_eliteCommando_01">play_unsc_batchat_marines_elite_killed</Sound>
		<Sound Type="KilledEnemy" Squad="cov_veh_ghost_01">play_unsc_batchat_marines_ghost_killed</Sound>
		<Sound Type="KilledEnemy" Squad="cov_inf_grunt_01">play_unsc_batchat_marines_grunt_killed</Sound>
		<Sound Type="KilledEnemy" Squad="cov_inf_hunter_01">play_unsc_batchat_marines_hunter_killed</Sound>
		<Sound Type="KilledEnemy" Squad="cov_inf_jackal_01">play_unsc_batchat_marines_jackal_killed</Sound>
		<Sound Type="KilledEnemy" Squad="cov_veh_locust_01">play_unsc_batchat_marines_locust_killed</Sound>
		<Sound Type="KilledEnemy" Squad="cov_veh_scarab_01">play_unsc_batchat_marines_scarab_killed</Sound>
		<Sound Type="KilledEnemy" Squad="cov_inf_suicidegrunt_01">play_unsc_batchat_marines_grunt_killed</Sound>
		<Sound Type="KilledEnemy" Squad="cov_air_vampire_01">play_unsc_batchat_marines_vampire_killed</Sound>
		<Sound Type="KilledEnemy" Squad="cov_veh_wraith_01">play_unsc_batchat_marines_wraith_killed</Sound>
		<Sound Type="KilledEnemy" Squad="Rebel">play_unsc_batchat_marines_rebel_killed</Sound>
		<Sound Type="AllyKilled">play_unsc_batchat_marines_allykilled</Sound>
		<Sound Type="AllyKilled" Squad="cov_air_banshee_01">play_unsc_batchat_marines_banshee_waskilled</Sound>
		<Sound Type="AllyKilled" Squad="cov_inf_brute_01">play_unsc_batchat_marines_brute_waskilled</Sound>
		<Sound Type="AllyKilled" Squad="cov_veh_brutechopper_01">play_unsc_batchat_marines_chopper_waskilled</Sound>
		<Sound Type="AllyKilled" Squad="cov_inf_eliteCommando_01">play_unsc_batchat_marines_elite_waskilled</Sound>
		<Sound Type="AllyKilled" Squad="cov_veh_ghost_01">play_unsc_batchat_marines_ghost_waskilled</Sound>
		<Sound Type="AllyKilled" Squad="cov_inf_grunt_01">play_unsc_batchat_marines_grunt_waskilled</Sound>
		<Sound Type="AllyKilled" Squad="cov_inf_hunter_01">play_unsc_batchat_marines_hunter_waskilled</Sound>
		<Sound Type="AllyKilled" Squad="cov_inf_jackal_01">play_unsc_batchat_marines_jackal_waskilled</Sound>
		<Sound Type="AllyKilled" Squad="cov_veh_locust_01">play_unsc_batchat_marines_locust_waskilled</Sound>
		<Sound Type="AllyKilled" Squad="cov_veh_scarab_01">play_unsc_batchat_marines_scarab_waskilled</Sound>
		<Sound Type="AllyKilled" Squad="cov_inf_suicidegrunt_01">play_unsc_batchat_marines_grunt_waskilled</Sound>
		<Sound Type="AllyKilled" Squad="cov_air_vampire_01">play_unsc_batchat_marines_vampire_waskilled</Sound>
		<Sound Type="AllyKilled" Squad="cov_veh_wraith_01">play_unsc_batchat_marines_wraith_waskilled</Sound>
		<Sound Type="AllyKilled" Squad="FlyingFlood">play_unsc_batchat_marines_flyingflood_waskilled</Sound>
		<Sound Type="AllyKilled" Squad="Flood">play_unsc_batchat_marines_flood_waskilled</Sound>
		<Sound Type="AllyKilled" Squad="Forerunner">play_unsc_batchat_marines_forerunner_waskilled</Sound>
		<Sound Type="AllyKilled" Squad="Rebel">play_unsc_batchat_marines_rebel_waskilled</Sound>
		<Sound Type="Cheer">play_unsc_batchat_marines_cheer</Sound>
		<Sound Type="ReactPowCarpetBomb">play_unsc_batchat_marines_unscleader_carpet</Sound>
		<Sound Type="ReactPowOrbital">play_unsc_batchat_marines_unscleader_mac</Sound>
		<Sound Type="ReactPowCryo">play_unsc_batchat_marines_unscleader_cryo</Sound>
		<Sound Type="ReactPowWave">play_unsc_batchat_marines_covleader_tidalwave</Sound>
		<Sound Type="ReactPowRage" CastingUnitOnly="false">play_unsc_batchat_marines_covleader_rage</Sound>
		<Sound Type="ReactPowCleansing">play_unsc_batchat_marines_covleader_cleansing</Sound>
		<Sound Type="ReactFatalityUNSC">play_unsc_batchat_marines_unscleader_fatality</Sound>
		<Sound Type="ReactFatalityCOV">play_unsc_batchat_marines_covleader_fatality</Sound>
		<Sound Type="ReactJacking">play_unsc_batchat_marines_unscleader_jacking</Sound>
		<Sound Type="ReactCommandeer">play_unsc_batchat_marines_unscleader_commandeering</Sound>
		<Sound Type="ReactHotDrop">play_unsc_batchat_marines_covleader_hotdrop</Sound>
		<Sound Type="ReactDeath" Squad="unsc_inf_spartan_01">play_unsc_batchat_marines_spartan_death</Sound>
		<Sound Type="ReactBirth" Squad="unsc_inf_spartan_01">play_unsc_batchat_marines_spartan_birth</Sound>
		<Sound Type="ReactJoinBattle" Squad="unsc_inf_spartan_01">play_unsc_batchat_marines_spartan_join</Sound>
		<Flag>Repairable</Flag>
		<Flag>Chatter</Flag>
		<Flag>KBAware</Flag>
		<Selection>
			<ConformToTerrain>true</ConformToTerrain>
		</Selection>
	</Squad>
  ```

 This might look confusing at first, but once you break it down it's quite simple.

`<Squad name="unsc_inf_marine_01" formationType="Flock" dbid="877">`
  
 Squad name = Is what the Squad is called in Objects.xml the squad name is needed to be able to train the said squad.
 FormationType = Is how the squad is going to line up. Flock- makes them group up. Line- makes them line up.
  
  
 `<DisplayNameID>3000</DisplayNameID>`
  
  DisplayNameID = Shows the units name. The number in the middle is the number that the text is assigned to in stringtable.xml.
  
  
  `<RolloverTextID>3001</RolloverTextID>`
  
  RolloverTextID = Shows infomation about the unit where it is trainned. Again the number in the middle is the number that the text is assigned to in stringtable.xml.
  
  
  `<StatsNameID>25679</StatsNameID>`
  
  StatsNameID = Shows the unit name on the post game results. The number is used in strnigable.xml.
  
  
  `<RoleTextID>500</RoleTextID>`
  
  RoleTextID = Shows the unit's role. Number in the middle is used in stringtable I'm getting tired of typing that.
  
  `<BuildPoints>8</BuildPoints>`
  
  BuildPoints = How much time it takes to train
  
  
`<Cost resourcetype="Supplies">100</Cost>`
    
 Cost resourcetype= How much supplies or reactors it needs in order to be bought.
 This interfaces with resources declared in `leaders.xml`.
    
`<SubSelectSort>3000</SubSelectSort>`
  
  SubSelectSort= This sorts units togather or apart. If you double click a Marine Squad and a ODST squad near by the Marines have the same SubSelectSort number it will select both squads. The number this time is just used to categorize units with the same or different number.
  
`<AggroDistance>35</AggroDistance>`
  
  AggroDistance= How much range a unit has to automatically target a enemy set this to 0 or removing this line makes a unit ingnore enemies completely unless you tell them yourself to attack.
  
 `<Birth anim0="Train" anim1="Train" anim2="TrainAirlock" anim3="ElephantTrain" trainerAnim="TrainInfantry" spawnpoint="bone_spawnPoint02" endPoint="bone_endPoint02">Trained</Birth>`
 
 Birth= what animation will be used when and where your trainning a unit from.
 anim0= Main Base.
 anim1= Mini Base.
 anim2= Airlock from the campagin missions.
 anim3= Trainned from Elephants
 
 The animations for units trainning is stored in their visual files.
 
 `<HPBar offset="0,9,0">UNSC_Health</HPBar>`
 
 HBBar= what the HPbar above the unit looks like
 
 `<AbilityRecoveryBar Centered="UNSC_Ability_Centered">UNSC_Ability</AbilityRecoveryBar>`
 
 AbilityRecoveryBar= The Clock cirle thing that shows you how much time it takes before you can use a ablility again.
 
`<VeterancyBar Centered="UNSC_Star_Centered">UNSC_Star</VeterancyBar>`

VeterancyBar= The Stars that show up when your unit gets veterancy.

```xml
    <Units>
		<Unit count="4" role="normal">unsc_inf_marine_01</Unit>
    </Units>
```

  Units= What units are in the squad.

```xml
<Sound Type="StartMove">play_ani_marine_walk_01</Sound>
<Sound Type="StopMove">stop_ani_marine_walk_01</Sound>
<Sound Type="StopExist">stop_ani_marine_exist</Sound>
<Sound Type="MoveChatter">play_unsc_batchat_marines_move</Sound>
<Sound Type="AttackChatter" Squad="cov_veh_locust_01">play_unsc_batchat_marines_locust_taunt</Sound>
<Sound Type="KilledEnemy" Squad="FlyingFlood">play_unsc_batchat_marines_flyingflood_killed</Sound>
<Sound Type="AllyKilled" Squad="cov_veh_ghost_01">play_unsc_batchat_marines_ghost_waskilled</Sound>
<Sound Type="Cheer">play_unsc_batchat_marines_cheer</Sound>
<Sound Type="ReactPowCarpetBomb">play_unsc_batchat_marines_unscleader_carpet</Sound>
<Sound Type="ReactPowOrbital">play_unsc_batchat_marines_unscleader_mac</Sound>
<Sound Type="ReactPowCryo">play_unsc_batchat_marines_unscleader_cryo</Sound>
<Sound Type="ReactPowWave">play_unsc_batchat_marines_covleader_tidalwave</Sound>
<Sound Type="ReactPowRage" CastingUnitOnly="false">play_unsc_batchat_marines_covleader_rage</Sound>
<Sound Type="ReactPowCleansing">play_unsc_batchat_marines_covleader_cleansing</Sound>
<Sound Type="ReactFatalityUNSC">play_unsc_batchat_marines_unscleader_fatality</Sound>
<Sound Type="ReactFatalityCOV">play_unsc_batchat_marines_covleader_fatality</Sound>
<Sound Type="ReactJacking">play_unsc_batchat_marines_unscleader_jacking</Sound>
<Sound Type="ReactCommandeer">play_unsc_batchat_marines_unscleader_commandeering</Sound>
<Sound Type="ReactHotDrop">play_unsc_batchat_marines_covleader_hotdrop</Sound>
<Sound Type="ReactDeath" Squad="unsc_inf_spartan_01">play_unsc_batchat_marines_spartan_death</Sound>
<Sound Type="ReactBirth" Squad="unsc_inf_spartan_01">play_unsc_batchat_marines_spartan_birth</Sound>
<Sound Type="ReactJoinBattle" Squad="unsc_inf_spartan_01">play_unsc_batchat_marines_spartan_join</Sound>
```

SoundType= Are Voice files that activate when specific things happen ingame when they kill a unit they cheer when a leader power is    used they stat the obvious.

`<Flag>Repairable</Flag>`

Repairable= Judges whether a unit can be healed or not.


`<Flag>Chatter</Flag>`

Chatter= Unables the Unit to speak when speific things happen. It's closely tied with the whole sound type thing.

 
  
  
  
  
  
  
  
