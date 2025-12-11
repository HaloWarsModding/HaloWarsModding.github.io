---
title: Cadenza
description: "Simple command-line tool to edit Halo Wars: DE Wwise sounds."
layout: default
nav_order: 6
permalink: /tools/cadenza
image: https://raw.githubusercontent.com/HaloWarsModding/HaloWarsModding.github.io/master/resources/images/metadata/header.png
toc: true
---

# Cadenza <span class="label label-green">Stable</span>
{: .no_toc }

Cadenza is a small command-line tool that lets you take sounds out of Halo Wars: Definitive Edition and rebuild them.

If you want to swap voice lines, replace sound effects, or tweak what plays when, Cadenza is what you use.

{: .new }
Cadenza is still being improved.  
Have feedback or ideas? Join the [Halo Wars Hub Discord](https://discord.gg/GuvUCgqz8d)  
Found a bug? Report it on the [Cadenza GitHub issue tracker](https://github.com/HaloWarsModding/Cadenza/issues)

[Download Cadenza](https://github.com/HaloWarsModding/Cadenza/releases/download/0.0.1/Cadenza_win-x64_v0.0.1.zip){: .btn .btn-purple }

---

1. TOC
{:toc}

---

## What You Can Do With Cadenza

With Cadenza, you can:

Extract game audio  
- Pull out voice lines, sound effects, and other sounds from Halo Wars: DE.
Edit or replace sounds  
- Open them in your usual audio editor (e.g Audacity), then save new versions.
Change what plays in-game  
- Adjust which sound plays for a given event (for example: which sound a unit uses for a line).
Rebuild game sound files  
- Pack everything back up so the game uses your new sounds instead of the originals.

Think of it as

Unpack game sounds > edit them > repack them for the game.

Halo Wars: DE stores its audio in a few file types. You’ll see these names, but you don’t need to fully understand them:

`.pck` - big “sound packs” that hold lots of sounds and banks.

`.bnk` - SoundBanks (they tell the game what sounds to play and when).

`.wem` - the actual audio files used by the game.

Cadenza handles converting these into files you can actually edit, and then back into game-ready files.

{: .note }
Cadenza is a command-line tool.
You run it in a terminal / command prompt, not a graphical window.  

---

## Basic Workflow

### Extract From a `.pck`

You point Cadenza at a game `.pck` file.

Cadenza will

- Find all the sounds (`.wem`) and SoundBanks (`.bnk`) inside it.
- Sort files by language (ENG, FRA, etc.).
- Save everything as regular files on disk.

At the same time, it creates a project file:

`something.cadenzaproj`

This project file remembers

- Which sounds were in the pack  
- How they were organized  
- What needs to be rebuilt later  

You don’t need to track any of that yourself, the project file is the recipe for rebuilding.

---

### Edit Sounds and Settings

After extraction, you can work on two main things

The audio itself  
- Convert/edit the audio as WAVs (coming from `.wem`).
- Replace voice lines, sound effects, etc.

The sound setup (events and mappings)  
- Cadenza converts `.bnk` files into easier text-like files called `.bnkinfo`.
- These `.bnkinfo` files are meant to be:
  - Easier to read
  - Easier to tweak

Using `.bnkinfo` you can change, for example

- Which event plays which sound  
- Which media ID points to which audio file  

When you’re done editing `.bnkinfo`, Cadenza can turn them back into proper `.bnk` files the game understands.

---

### Rebuild for the Game

Once you’ve

- Edited or replaced audio (WAVs)
- Adjusted events/mappings (`.bnkinfo`)

You run Cadenza again, this time on the `.cadenzaproj` file.

Cadenza will

- Rebuild any updated SoundBanks (`.bnk`)
- Rebuild the `.pck` package(s)
- Put all your edited audio back into the right places

The result is a new `.pck` that the game can use just like the original, but with your custom sounds.

---

## Credits

Cadenza builds on other projects

HashDepot (Sedat Kapanoglu)  
- Used for hashing internals.

Wwiser.NET  
- Used to read and convert SoundBank data into `.bnkinfo` for easier editing.
