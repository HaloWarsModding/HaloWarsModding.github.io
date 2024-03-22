---
title: GLS (Lighting) File
description: "GLS (Lighting) File Description"
permalink: /docs/gls
layout: default
nav_order: 4
image: https://raw.githubusercontent.com/HaloWarsModding/HaloWarsModding.github.io/master/resources/images/metadata/header.png
toc: true
---

# GLS <span class="label label-blue">Work In Progress</span>
{: .no_toc }

The GLS file(s) handles map lighting on a per-map basis, and they can be found in each dedicated map folder contained within the `(ModName)\scenario` directory. It DOES NOT however, control the Fog of War, as that is handled globally in a different file.

1. TOC
{:toc}


Every map has its own `.GLS` located in its dedicated folder. For instance, the .GLS for Chasms would be located at `(ModName)\scenario\skirmish\design\chasms`


Here is a sample `.GLS` file that will be referenced throughout this guide.

```xml
    <lightSet xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <EnvironmentMap>environment\sky\harvest_sky_en</EnvironmentMap>
    <backgroundColor>0,0,0</backgroundColor>
    <SHFillIntensity>0.3</SHFillIntensity>
    <LGTIntensityScale>10</LGTIntensityScale>
    <LGTParticleIntensityScale>1</LGTParticleIntensityScale>
    <brightnessIntensity>1</brightnessIntensity>
    <sunInclination>46.116</sunInclination>
    <sunRotation>45.828</sunRotation>
    <sunUnitColor>0,0,0</sunUnitColor>
    <setTerrainColor>0,0,0</setTerrainColor>
    <SunParticleColor>0,0,0</SunParticleColor>
    <terrainSpecularPower>50.391</terrainSpecularPower>
    <terrainBumpStrength>1.458</terrainBumpStrength>
    <TerrainAODiffuseIntensity>1</TerrainAODiffuseIntensity>
    <TerrainSpecOnlyColor>97,149,237</TerrainSpecOnlyColor>
    <TerrainSpecOnlyPower>51.5</TerrainSpecOnlyPower>
    <TerrainSpecOnlyShadowDarkness>1</TerrainSpecOnlyShadowDarkness>
    <TerrainSpecOnlySunInclination>0</TerrainSpecOnlySunInclination>
    <TerrainSpecOnlySunRotation>141.588</TerrainSpecOnlySunRotation>
    <sunUnitShadowDarkness>0</sunUnitShadowDarkness>
    <sunTerrainShadowDarkness>0</sunTerrainShadowDarkness>
    <sunUnitIntensity>4.926</sunUnitIntensity>
    <sunTerrainIntensity>4.95</sunTerrainIntensity>
    <SunParticleIntensity>1</SunParticleIntensity>
    <sunShadows>true</sunShadows>
    <hemiInclination>53.136</hemiInclination>
    <hemiRotation>258.084</hemiRotation>
    <hemiUnitTopColor>50,50,50</hemiUnitTopColor>
    <hemiUnitBottomColor>50,50,50</hemiUnitBottomColor>
    <hemiTerrainTopColor>50,50,50</hemiTerrainTopColor>
    <hemiTerrainBottomColor>50,50,50</hemiTerrainBottomColor>
    <hemiUnitIntensity>0.054</hemiUnitIntensity>
    <hemiTerrainIntensity>0.018</hemiTerrainIntensity>
    <middleGrey>0.803</middleGrey>
    <brightMaskThresh>0.854</brightMaskThresh>
    <bloomIntensity>2.96</bloomIntensity>
    <bloomSigma>4</bloomSigma>
    <adaptationRate>0.044</adaptationRate>
    <logAveMin>0.608</logAveMin>
    <logAveMax>0.646</logAveMax>
    <whitePointMin>4.737</whitePointMin>
    <whitePointMax>4.875</whitePointMax>
    <zFogColor>50,50,50</zFogColor>
    <zFogIntensity>1.25</zFogIntensity>
    <zFogStart>50</zFogStart>
    <zFogDensity>5</zFogDensity>
    <planarFogColor>50,50,50</planarFogColor>
    <planarFogIntensity>1.25</planarFogIntensity>
    <planarFogStart>20</planarFogStart>
    <planarFogDensity>6</planarFogDensity>
    <dofEnabled>false</dofEnabled>
    <dofNearRange>350</dofNearRange>
    <dofFocalPlaneDist>100</dofFocalPlaneDist>
    <dofFarRange>450</dofFarRange>
    <dofMaxBlurriness>1</dofMaxBlurriness>
    <Light>
        <Name>LocalFloodAreaLight</Name>
        <Type>omni</Type>
        <Priority>127</Priority>
        <Position>696.7579,-11.1961,290.3232</Position>
        <Radius>14.492</Radius>
        <Specular>true</Specular>
        <Intensity>2.8</Intensity>
        <Color>0,114,54</Color>
        <Shadows>false</Shadows>
        <ShadowDarkness>0.28</ShadowDarkness>
        <Fogged>true</Fogged>
        <FoggedShadows>true</FoggedShadows>
        <LightBuffered>true</LightBuffered>
        <TerrainOnly>false</TerrainOnly>
        <FarAttnStart>0.5</FarAttnStart>
        <DecayDist>70</DecayDist>
        <Direction>0,-1,0</Direction>
        <OuterAngle>70</OuterAngle>
        <InnerAngle>40</InnerAngle>
    </Light>
    <ObjectPropertyForFLSGen>_Position67_,_67_</ObjectPropertyForFLSGen>
</lightSet>
```
`<EnvironmentMap>`
Handles skybox texture used for enviromentmap (.rm) textures.
- Uses a link to a texture of your choosing, starting from the art folder.

`<backgroundColor>`
Determines the color of the area normally blacked out outside of map boundaries.
- Uses RGB values (0-255) to dictate the color used.
- Setting the values to 0,0,0 makes it opaque, making it impossible to see any terrain past it

`<SHFillIntensity>`
Influences global lighting, and has a more significant effect on shadows casted by most objects.
- Makes use of numerical values with seemingly no limit (decimals are allowed); lower values allow shadows, but higher values can disable them or even make the map brighter.
- Ideally, values should be kept in the 0-1 range for the best results.

`<LGTIntensityScale>`
Affects the Intensity of lights produced from some objects, like UNSC buildings while they are building.
- Makes use of numerical values with seemingly no limit (decimals are allowed).
- Ideally, values should be kept in the 0-1 range for the best results.

`<LGTParticleIntensityScale>`
Likely affects the Intensity of lights produced by particles, but seemingly does nothing in testing.

`<brightnessIntensity>`
Seemingly does nothing according to testing; name unclear.

`<sunInclination>`
Controls the pitch of the sun, which affects what direction shadows are casted. (think how the Minecraft sun rotates relative to the world).
- Uses a range of -180-180; 0 being directly above of the map. Values higher then 90 (or lower then -90) can tilt the sun underneath the map which can lead to unrealistic shadows.

`<sunRotation>`
Controls the angle of the sun relative to the map, which affects which direction shadows are casted from.
- Uses a range of 0-360
- Using a value of 0 places the sun in the North East.

`<sunUnitColor>`
Modifies what color is overlaid onto objects if the sun is shining onto them. Does not affect how the sun lights up terrain.
- Uses RGB values (0-255) to dictate the color used. Darker combinations can be used to simulate moonlight instead.
- Inputting 0,0,0 as the values effectively covers all objects in shadow, but they will still create shadows of their own.

`<setTerrainColor>`
Modifies what color is overlaid onto the terrain if the sun is shining onto it. Does not affect how the sun lights up objects.
- Uses RGB values (0-255) to dictate the color used. Darker combinations can be used to simulate moonlight instead.
- Setting this value as 0,0,0 effectively covers the terrain in shadow.

`<SunParticleColor>`
Modifies what color is overlaid onto particles that are set to be modified by map lighting.
- Uses RGB values (0-255) to dictate the color used. Best kept similar and/or identical to the <sunUnitColor> value

`<terrainSpecularPower>`
Global value that affects the intensity of reflections off of terrain specular (.sp) textures
- Makes use of numerical values with seemingly no limit (decimals are allowed); higher values can simulate wetness on terrain with a specular texture.

`<terrainBumpStrength>`
Hard to describe, but basically determines how strict the reflections are in regards to angles.
- Makes use of numerical values with seemingly no limit (decimals are allowed); Low values recommended.
- Inputting 0 will make it so any terrain specular texture exposed to the sun will reflect, which may not always be realistic in some circumstances.

`<TerrainAODiffuseIntensity>`
Seemingly does nothing according to testing; name unclear.

`<TerrainSpecOnlyColor>`
Controls the color of the specular reflection off of the terrain.
- Uses RGB values (0-255) to dictate the color used.

`<TerrainSpecOnlyPower>`
Seemingly does nothing according to testing; name unclear.

`<TerrainSpecOnlyShadowDarkness>`
Seemingly does nothing according to testing; name unclear.

`<TerrainSpecOnlySunInclination>`
Influences `<TerrainSpecOnlySunRotation>`, but exact effect is hard to pin down. Hard to determine exactly how this is set up, since it doesn’t seem to work like you’d expect it to.

`<TerrainSpecOnlySunRotation>`
Changes the yaw angle that the specular textures with emit reflections based off of the rotation of the camera. Hard to determine exactly how this is set up, since it doesn’t seem to work like you’d expect it to.

`<sunUnitShadowDarkness>`
Affects how bright or dark units covered in shadows are. Higher values make units brighter.
- Makes use of numerical values with seemingly no limit (decimals are allowed); Low values recommended.
- Using a value of `1` effectively prevents shadows from being casted onto units.

`<sunTerrainShadowDarkness>`
Affects how bright or dark terrain covered in shadow is. Higher values makes the terrain brighter.
- Makes use of numerical values with seemingly no limit (decimals are allowed); Low values recommended.
- Using a value of `1` effectively prevents shadows from being casted onto terrain.

`<sunUnitIntensity>`
Modifies how much units are lit up in the sunlight
- Makes use of numerical values with seemingly no limit (decimals are allowed); Low values recommended.
- Using a value of `0` effectively prevents the sunlight from making units brighter.

`<sunTerrainIntensity>`
Modifies how much the terrain is lit up in the sunlight
- Makes use of numerical values with seemingly no limit (decimals are allowed); Low values recommended.
- Using a value of `0` effectively prevents the sunlight from brightening the terrain.

`<SunParticleIntensity>`
Modifies how much particles are lit up in the sunlight
- Makes use of numerical values with seemingly no limit (decimals are allowed); Low values recommended.
- Using a value of `0` effectively prevents the sunlight from brightening up particles.

`<sunShadows>`
Enables/Disables shadows.
- Uses `True`/`False` inputs. Pretty straightforward.

`<hemiInclination>`
Seemingly does nothing according to testing; name unclear.

`<hemiRotation>`
Seemingly does nothing according to testing; name unclear.

`<hemiUnitTopColor>`
Seemingly a primary global color modifier that can be overlaid onto units.
- Uses RGB values (`0-255`) to dictate the color used.
- Setting the values to `0,0,0` basically disables it.

`<hemiUnitBottomColor>`
Seemingly a secondary global color modifier that can be overlaid onto units.
- Uses RGB values (`0-255`) to dictate the color used.
- Setting the values to `0,0,0` basically disables it.

`<hemiTerrainTopColor>`
Seemingly a primary global color modifier that can be overlaid onto the terrain.
- Uses RGB values (`0-255`) to dictate the color used.
 - Setting the values to `0,0,0` basically disables it.

`<hemiTerrainBottomColor>`
Seemingly a secondary global color modifier that can be overlaid onto terrain.
- Uses RGB values (`0-255`) to dictate the color used.
- Setting the values to `0,0,0` basically disables it.

`<hemiUnitIntensity>`
Determines how intense the global color overlay is for units.
- Ideally, values should be kept in the `0-1` range for the best results. The game typically uses decimals pushed out by the 3rd digit for this.

`<hemiTerrainIntensity>`
Determines how intense the global color overlay is for terrain.
- Ideally, values should be kept in the `0-1` range for the best results. The game typically uses decimals pushed out by the 3rd digit for this.

`<middleGrey>`
Controls the global map brightness, **OR** controls how far the game transitions from the black fade in to gameplay.
 - Ideally, values should be kept in the `0-1` range for the best results. Preferably 1.
 - Setting this value to `0` makes the game unplayable, as your entire screen will be black.

`<brightMaskThresh>`
Changes an unknown threshold that dictates what things are blurred onscreen.
- Ideally, values should be kept in the `0-1` range for the best results. 
- Setting this to `0` makes everything blurry.

`<bloomIntensity>`
Changes how intense the blurs are overall.
- Ideally, values should be kept in the `0-10` range for the best results. 

`<bloomSigma>`
Changes how wide reaching the blurs are.
- Ideally, values should be kept in the `0-10` range for the best results. 

`<adaptationRate>`
Placeholder Text

`<logAveMin>`
Placeholder Text

`<logAveMax>`
Placeholder Text

`<whitePointMin>`
Placeholder Text

`<whitePointMax>`
Placeholder Text

`<zFogColor>`
Placeholder Text

`<zFogIntensity>`
Placeholder Text

`<zFogStart>`
Placeholder Text

`<zFogDensity>`
Placeholder Text

`<planarFogColor>`
Placeholder Text

`<planarFogIntensity>`
Placeholder Text

`<planarFogStart>`
Placeholder Text

`<planarFogDensity>`
Placeholder Text

`<dofEnabled>false</dofEnabled>`
Placeholder Text
 
`<dofNearRange>350</dofNearRange>`
Placeholder Text
 
`<dofFocalPlaneDist>100</dofFocalPlaneDist>`
Placeholder Text
  
`<dofFarRange>450</dofFarRange>`
Placeholder Text
  
`<dofMaxBlurriness>1</dofMaxBlurriness>`
Placeholder Text
