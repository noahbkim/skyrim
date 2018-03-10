# The Ultimate Skyrim Mod Guide

This document is essentially as a simpler version of a guide by SinitarGaming available [here](http://www.nexusmods.com/skyrim/mods/76373/?), but includes a full set of gameplay overhaul mods on top.
It is intended for the final version of the original (not the Special Edition) Steam distribution of Skyrim with all DLC, and is based on the Nexus Mod Manager. 
This guide was last updated on March 7th, 2018.

## Prerequisite Software

- [Skyrim Script Extender](http://skse.silverlock.org/) - an external script loader used for almost all mods, plugins, and tweaks. Can be conveniently installed via Steam. 
- [LOOT](https://loot.github.io/) - a tool that manages dependencies and plugin load order. Crucial to maintaining stability with large numbers of mods.
- [TES5edit](http://www.nexusmods.com/skyrim/mods/25859/?) - a plugin manipulation tool that provides mod comparison and conflict detection/resolution.
- [Save Game Script Cleaner](http://www.nexusmods.com/skyrim/mods/52363/?) - tool for managing plugin assets and scripts in save game data. Useful if you want to remove mods during a game, but not necessary.
- [Windows Texture Viewer](http://www.nvidia.com/object/windows_texture_viewer.html) - a small viewer for `.dds` texture files that allows you to compare conflicting assets between mods.
- [Notepad++](https://notepad-plus-plus.org/) - my personally recommended editor for all text-based files, such as `.ini` and `.txt`. This will be highly convenient because of how useless Windows is when it comes to file extensions. 

## File locations

There are two main file system locations used by Skyrim. 
The first is in your Steam install directory, and its path will be referred to as the **[skyrim root]**. 
It is generally located here:

```
C:\Program Files (x86)\Steam\steamapps\common\Skyrim\
```

The Skyrim root directory can also be under a custom Steam directory if you've modified the installation path in your Steam preferences (useful if you want to use separate storage media for your game files, for example). 
My installation is located here:

```
E:\Steam\steamapps\common\Skyrim\
```

The other important directory is where your local Skyrim files are stored. 
This will be referred to as the **[skyrim data]**, and is typically located here (replacing `Me` with your Windows username):

```
C:\Users\Me\Documents\My Games\Skyrim
```

## SKSE Setup

Make sure you have an `SKSE.ini` file located in the `[skyrim root]/Data/skse` directory. 
If you do not, make an empty one (I recommend that you use Notepad++). 
Open the `SKSE.ini` file and paste the following lines:

```ini
[General]
ClearInvalidRegistrations=1
EnableDiagnostics=1

[Display]
iTintTextureResolution=2048
```

## Crash Fixes

Install the [Crash Fixes](http://www.nexusmods.com/skyrim/mods/72725/?) mod. 
Edit `[skyrim root]/Data/skse/plugins/CrashFixPlugin.ini` and modify the following options:

```ini
UseOSAllocators=1
CustomMemoryBlock=1
MemoryInfoConsole=1
```

To make sure memory block load isn't too high, run Skyrim and open the developer console. 
Check if any of the listed loads are above 85-90%, and if so, increase the `CustomMemoryBlockTotalSizeMb` value in the `CrashFixPlugin.ini` in increments of 10 until they aren't. 
Then, download this [SKSE plugin pre-loader](http://www.nexusmods.com/skyrim/mods/75795/?) and copy the `d3dx9_42.dll` file into your Skyrim root directory. 
This will allow SKSE to execute plugins, such as CrashFixes, prior to loading the game. 

Finally, install the [Safety Load](http://www.nexusmods.com/skyrim/mods/46465/?) mod, which prevents infinite loading screens and other issues related to memory allocation.

## Base Game Cleaning

To clean the base game, open TESVEdit and load the `Skyrim.esm`, `Update.esm`, `Dawnguard.esm`, `HearthFires.esm`, and `Dragonborn.esm` files.
Right click on each and select  `Apply Filter for Cleaning`.
Then, right click again and select `Remove "Identical to Master" records`.

## Initial Mods

* [ ] [Unofficial Skyrim Legendary Edition Patch](http://www.nexusmods.com/skyrim/mods/71214/?) - an enormous Skyrim patch that attempts to fix most of the common bugs currently persistent in the game.
* [ ] [Falskaar](http://www.nexusmods.com/skyrim/mods/37994/?) - over 20 hours of extended story, including new items and lore.
* [ ] [Alternate Start](http://www.nexusmods.com/skyrim/mods/9557/?) - adds different starting scenarios and skips the cutscene in the beginning.
* [ ] [SkyUI](http://www.nexusmods.com/skyrim/mods/3863/?) - an actually usable inventory control interface.
* [ ] [iHUD](http://www.nexusmods.com/skyrim/mods/3222/?) - an configurable immersive in-game overlay.

## Modding Methodology

As a note, don't try to install all of the listed mods without intermediate testing, as there's a much lower chance of it working that way. 
Instead, install a group of mods, sort them with LOOT, and test Skyrim to make sure everything works. 
Also make sure to keep track of your progress as you go. 

Another thing to think about is how long it will take for some mods to download. 
I would recommend queueing a bunch of the listed mods in advance so they download while you're configuring earlier ones (especially texture mods).

## Graphics and Meshes

* [ ] [Optimized Vanilla Textures](http://www.nexusmods.com/skyrim/mods/57353/?) - better and faster vanilla textures.
      After installing for Nexus Mod Manager, run the `Texture Install.vbs` file in your `[skyrim root]/Data` folder.
* [ ] [Ruins Clutter Improved](http://www.nexusmods.com/skyrim/mods/14227/?) - better meshes for environmental ruins.
* [ ] [Ultimate HD Fire Effects](http://www.nexusmods.com/skyrim/mods/28642/?) - better looking fire.
* [ ] [HD Enhanced Terrain](http://www.nexusmods.com/skyrim/mods/29782/?) - higher resolution textures and meshes for terrain.
* [ ] [Static Mesh Improvement Mod](http://www.nexusmods.com/skyrim/mods/8655/?) - better meshes for tons of static objects in the world.
* [ ] [Skyrim HD - 2K Textures](http://www.nexusmods.com/skyrim/mods/607/?) - a complete set of 2K textures.
* [ ] [Vivid Landscapes - All in One](http://www.nexusmods.com/skyrim/mods/49344) - unified mod for more attractive landscapes.
* [ ] [aMidianBorn Caves and Mines](http://www.nexusmods.com/skyrim/mods/39190) - better cave and mine textures and meshes.
* [ ] [4k Parallax Mines by Pfuscher](http://www.nexusmods.com/skyrim/mods/58242) - parallax texturing for mines.
* [ ] [Parallax Bridges by Pfuscher](http://www.nexusmods.com/skyrim/mods/57805) - parallax texturing for bridges.
* [ ] [Real Roads for Skyrim](https://www.nexusmods.com/skyrim/mods/55518) - better looking roads.
* [ ] [Skyrim Flora Overhaul](http://www.nexusmods.com/skyrim/mods/141) - better plant meshes and textures.
* [ ] [Forest Bark](http://www.nexusmods.com/skyrim/mods/64192) - a companion mod to the flora overhaul with more attractive tree bark.
* [ ] [Skyrim Bigger Trees](http://www.nexusmods.com/skyrim/mods/17168/?) - a mod that introduces taller trees.
* [ ] [4K Parallax Treebark](http://www.nexusmods.com/skyrim/mods/61875) - better tree bark with parallax.
* [ ] [Realistic Aspen Trees 4k](http://www.nexusmods.com/skyrim/mods/51069/?) - more realistic Aspen trees.
* [ ] [4K Parallax Treebark Aspen Patch](http://www.nexusmods.com/skyrim/ajax/downloadfile?id=1000144755) - a patch that accommodates Aspen trees.
* [ ] [Verdant - A Skyrim Grass Plugin](http://www.nexusmods.com/skyrim/mods/60220) - better and more dense grass. 
      Requires you to modify your `[skyrim data]/Skyrim.ini` to add `iMaxGrassTypesPerTexture=15` and `iMinGrassSize=70`
* [ ] [Verdant No Road Water Grass and Landscape Edits](http://www.nexusmods.com/skyrim/mods/80656/?) - a set of Verdant tweaks.
* [ ] [High Definition Ivy](http://www.nexusmods.com/skyrim/mods/30971) - better ivy textures.
* [ ] [Replacement Ivy](http://www.nexusmods.com/skyrim/mods/1878) - better ivy textures on existing models.
* [ ] [RUGNAROK](http://www.nexusmods.com/skyrim/mods/64830) - nicer rug textures.
* [ ] [Realistic Water Two](http://www.nexusmods.com/skyrim/mods/41076) - better water textures.
* [ ] [Watercolor for ENB and Realistic Water Two](http://www.nexusmods.com/skyrim/mods/48938) - adds water color and sun scattering.
* [ ] [Realistic Water Two ENB Textures](http://www.nexusmods.com/skyrim/ajax/downloadfile?id=1000081559) - water textures for the ENB.
* [ ] [Transparent wave spray Retexture by Pfuscher](http://www.nexusmods.com/skyrim/mods/59547) - improved shoreline water spray.
* [ ] [aMidianBorn Landscape](http://www.nexusmods.com/skyrim/mods/37865) - better landscape meshes.
* [ ] [Solstheim landscape and furniture](http://www.nexusmods.com/skyrim/mods/31591) - better meshes and textures for furniture in Solstheim.
* [ ] [aMidianBorn Solstheim Landscape](http://www.nexusmods.com/skyrim/mods/50013) - better textures for Solstheim landscape.

## Parallax Textures 

* [ ] [Skyrim 2016 Terrain Parallax by Pfuscher](http://www.nexusmods.com/skyrim/mods/61929) - various parallax retextures for terrain. 
      I chose to not overwrite any files with this mod, since others are provided by aMidianBorn Landscape.
* [ ] [Skyrim 2016 WIP by Pfuscher](http://www.nexusmods.com/skyrim/mods/60150/?) - parallax textures for other meshes.
* [ ] [Whiterun Streets](http://www.nexusmods.com/skyrim/mods/82433) - improved parallax for Whiterun streets.
* [ ] [Vivid Landscapes - Rocking Stones and Mountains Two](http://www.nexusmods.com/skyrim/mods/54540) - better stones and mountains.
* [ ] [Project Parallax Remastered](http://www.nexusmods.com/skyrim/mods/40512) - better parallax textures for roads and stuff.
* [ ] [Dust Effects](http://www.nexusmods.com/skyrim/mods/44201) - better dust particle effects.

## Custom Particles

* [ ] [Particle Patch All-In-One & Subsurface Scattering Patch](http://enbseries.enbdev.com/forum/viewtopic.php?t=1499) - complete particle and subsurface scattering mod. 
      Quit Nexus Mod Manager, download the archives, and move them to your Nexus Mods folder, which is usually located here: `C:\Games\Nexus Mod Manager\Skyrim\Mods`. 
      Then restart the mods and install them, but say no to mod when it asks to overwrite Static Mesh Improvement Mod.

## Weather Mods

* [ ] [Climates of Tamriel](http://www.nexusmods.com/skyrim/mods/17802) - major climates mod that improves weather and storms.
* [ ] [Falskaar - Climates of Tamriel patch](http://www.nexusmods.com/skyrim/mods/38361) - patch for climates in Falskaar.
* [ ] [Supreme Storms](http://www.nexusmods.com/skyrim/mods/27022) - larger, more realistic storms.
* [ ] [True Storms - Thunder and Rain Redone](http://www.nexusmods.com/skyrim/mods/63478) - really attractive thunder storms.
* [ ] [Lightning during Thunder Storms](http://www.nexusmods.com/skyrim/mods/15506) - adds lightning to storms.
* [ ] [Lightning during Thunder Storms - Climates of Tamriel - Patch](http://www.nexusmods.com/skyrim/mods/25675) - compatibility patch for lightning.
* [ ] [Wonders of Weather](http://www.nexusmods.com/skyrim/mods/64941) - adds rain splashes and rainbows.

## Lighting Mods

* [ ] [Enhanced Lights and FX](http://www.nexusmods.com/skyrim/mods/27043) - a really nice lighting and light effects mod.
* [ ] [Vivid Landscapes ELFX Patch](http://www.nexusmods.com/skyrim/ajax/downloadfile?id=1000140985) - compatibility patch for Vivid Landscapes and ELFX.

## Towns and Villages

* [ ] [Lanterns of Skyrim - All In One](https://www.nexusmods.com/skyrim/mods/18916) - lanterns around Skyrim.
* [ ] [Hunters Cabin of Riverwood](https://www.nexusmods.com/skyrim/mods/15878) - a small player home outside of Riverwood.
* [ ] [Hunters Cabin of Riverwood - Extended](https://www.nexusmods.com/skyrim/mods/64841) - tweaks to the hunter cabin.
* [ ] [Expanded Towns and Cities (ETAC)](http://www.nexusmods.com/skyrim/mods/13608) - provides bigger, more detailed towns and cities.
* [ ] [Unique Shops and Stores](http://www.nexusmods.com/skyrim/mods/80393) - more interesting stores within cities and outposts.

## More Environment

* [ ] [Ethereal Clouds](http://www.nexusmods.com/skyrim/mods/56279) - nice looking clouds.
* [ ] [Real Skyrim Snowflakes - Vivid Snow](http://www.nexusmods.com/skyrim/mods/68496) - nice looking snow.
* [ ] [Lorkhans Vision - Night Sky V2](http://www.nexusmods.com/skyrim/mods/48643) - use the ENB compatible version.
* [ ] [Dawnguard Parallax](http://www.nexusmods.com/skyrim/mods/45477) - Dawnguard textures.
* [ ] [Bellyaches Animal and Creature Pack](http://www.nexusmods.com/skyrim/mods/3621) - textured animals and creatures.
* [ ] [Bellyaches HD Dragon Replacer Pack](http://www.nexusmods.com/skyrim/mods/29631) - retextured dragons.
* [ ]  [Enhanced HD Dragon Bones](http://www.nexusmods.com/skyrim/mods/28741) - better dragon bones.
* [ ]  [Realistic Boat Bobbing](http://www.nexusmods.com/skyrim/mods/52694) - makes boats look less ridiculous.
* [ ]  [RUSTIC CLOTHING](http://www.nexusmods.com/skyrim/mods/69784) - more interesting and thematic clothing.
* [ ]  [Mage Outfit Texture Overhaul (HD 2K) - MOTO - With Schools of Magic](http://www.nexusmods.com/skyrim/mods/69289) - mage clothing.
* [ ] [aMidianBorn Book of Silence](http://www.nexusmods.com/skyrim/mods/24909) - retexture armor, weapons, creatures, and unique items. 
  Install in order of armor, creatures, Dragonborn DLC, unique items, weapons, as well as hot fixes. 
  Make sure to also read posted instructions, as there is a directory that has to be [renamed](https://www.nexusmods.com/skyrim/mods/24909?tab=posts)
* [ ] [aMidianborn Wolf Armor and Skyforge Weapons](https://www.nexusmods.com/skyrim/mods/34147) - retextured wolf armor and Skyforge weapons.
* [ ] [Joy of Ships](http://www.nexusmods.com/skyrim/mods/61808) - high quality replacements for ships and boats. 
  Also install the Joy of Parallax Ships patch from its files for using ENB.
* [ ] [RUSTIC WINDOWS](http://www.nexusmods.com/skyrim/mods/54302) - better-looking windows.
* [ ] [RUSTIC ALCHEMY and ENCHANTING TABLES](http://www.nexusmods.com/skyrim/mods/62328) - better alchemy and enchanting tables.
* [ ] [LeanWolf's Improved Enchanter Candle Meshes](http://www.nexusmods.com/skyrim/mods/53638) - better meshes for enchanting table props.
* [ ] [LeanWolf's Better-Shaped Weapons](http://www.nexusmods.com/skyrim/mods/39870) - makes weapons looks much more glorious and elegant, compatible with other retextures.
* [ ] [RUSTIC CLUTTER COLLECTION](http://www.nexusmods.com/skyrim/mods/62506) - improved clutter meshes.
* [ ] [RUSTIC COOKING STATION](http://www.nexusmods.com/skyrim/mods/62800) - more interesting foods and cooking meshes.
* [ ] [RUSTIC EAST EMPIRE COMPANY SIGNAGE](http://www.nexusmods.com/skyrim/mods/68196) - more detailed signs for East Empire.
* [ ] [RUSTIC ELDERSCROLL](http://www.nexusmods.com/skyrim/mods/73287) - thematically improved Elder Scroll textures.
* [ ] [RUSTIC FORSWORN](http://www.nexusmods.com/skyrim/mods/73515) - improved textures for the forsworn armor.
* [ ] [RUSTIC MONUMENTS and TOMBSTONES](http://www.nexusmods.com/skyrim/mods/68884) - better monuments and tombs.
* [ ] [RUSTIC NORDIC MURALS](http://www.nexusmods.com/skyrim/mods/65602) - cool mural textures.
* [ ] [RUSTIC OVEN - Hearthfires](http://www.nexusmods.com/skyrim/mods/68387) - better oven meshes and textures.
* [ ] [RUSTIC SOULGEMS](http://www.nexusmods.com/skyrim/mods/63766) - more interesting soulgems.
* [ ] [Soulgem Stand Redone](http://www.nexusmods.com/skyrim/mods/83320) - better mesh and texturing for soulgem stand.
* [ ] [RUSTIC STANDING STONES](http://www.nexusmods.com/skyrim/mods/68493) - better standing stones. 
* [ ] [RUSTIC WORD WALLS](http://www.nexusmods.com/skyrim/mods/68561) - more detailed textures and meshes for word walls.
* [ ] [HD Ruined Book Retexture - 1k 4k -](http://www.nexusmods.com/skyrim/mods/74510) - more detailed ruined books.
* [ ] [HD Stone Quarry and Clay Deposit for Hearthfire](http://www.nexusmods.com/skyrim/mods/38479) - cleaner quarries.
* [ ] [Business Ledger HD Retexture](http://www.nexusmods.com/skyrim/mods/38389) - way better business ledger.
* [ ] [Serious Mammoth Bone Retex HD](http://www.nexusmods.com/skyrim/mods/25179) - better mammoth skeletons.
* [ ] [Forgotten Retex Project](http://www.nexusmods.com/skyrim/mods/81792) - revisits overlooked objects in Skyrim.
* [ ] [RUSTIC ANIMATED POTIONS and POISONS](http://www.nexusmods.com/skyrim/mods/77541) - combination of poisons and potions mods.
## Maps

* [ ] [A Quality World Map and Solstheim Map - With Roads](http://www.nexusmods.com/skyrim/mods/4929) - standard world map improvements.
* [ ] [Better Falskaar and Wyrmstooth Map With Roads](http://www.nexusmods.com/skyrim/mods/51339) - mod maps.

## Even More Environment

* [ ] [Ultimate HD Torch](http://www.nexusmods.com/skyrim/mods/28060) - better torches.

- [ ] [Smoking Torches and Candles](http://www.nexusmods.com/skyrim/mods/35819) - smoke for torches and candles.
- [ ] [Birds of Skyrim](http://www.nexusmods.com/skyrim/mods/17723) - better birds.
- [ ] [Birds of Skyrim - Ruhadre Patch v1.1](http://www.nexusmods.com/skyrim/mods/72833) - patch for birds, make sure to get the one that is USLEEP compatible.
- [ ] [Enhanced Blood Textures](http://www.nexusmods.com/skyrim/mods/60) - better blood.
- [ ] [Deadly Spell Impacts](http://www.nexusmods.com/skyrim/mods/2947) - textures for ground impacts from spells.
- [ ] [Dawn of the Dawnguard Armor](http://www.nexusmods.com/skyrim/mods/64559) - better Dawnguard armor.
- [ ] [Dragonbone Armor and Weapons HD by Natterforme](http://www.nexusmods.com/skyrim/mods/68952) - better dragonbone armor and weapons.
- [ ] [Nightingale Prime HD](http://www.nexusmods.com/skyrim/mods/28899) - retexture weapons to match nightingale prime.
- [ ] [Spellbreaker Oblivionized retexture in HD](http://www.nexusmods.com/skyrim/mods/58015) - spellbreaker with oblivion colors.
- [ ] [Refracting Stalhrim](http://www.nexusmods.com/skyrim/mods/53067) - add refraction to Stalhrim.
- [ ] [Outlandish Stalhrim](http://www.nexusmods.com/skyrim/mods/70817) - better textures for Stalhrim.
- [ ] [Transparent and refracting Glass Eqmnt CBBE UNP UNPB](http://www.nexusmods.com/skyrim/mods/29123) - transparent glass and armor weapons. 
  Note: maybe go back and configure for enhanced blood?
- [ ] [Thieves Guild Armor HD revival](http://www.nexusmods.com/skyrim/mods/46873) - better thieves guild armor. Also install the secondary armor replacements after the revival. 
- [ ] [Deathbell HD - All-New Textures](http://www.nexusmods.com/skyrim/mods/70133) - better Deathbell flower textures.
- [ ] [Mountain flower by Mari](http://www.nexusmods.com/skyrim/mods/78145) - mountain flowers.
- [ ] [Deathbell by Mari](http://www.nexusmods.com/skyrim/mods/78197) - Deathbell meshes and textures.
- [ ] [Green Hanging Spanish Moss HD](http://www.nexusmods.com/skyrim/mods/28985) - Spanish moss.
- [ ] [Hybrids HD Plants and Herbs Retexture](http://www.nexusmods.com/skyrim/mods/1546) - some good flora textures. 
  Choose and install texture manually as many of them can be already retextured by other flora mods.
- [ ] [Better Nirnroot - Hi-Res 2K Textures](http://www.nexusmods.com/skyrim/mods/36457) - improved Nirnroot.
- [ ] [Tamriel Reloaded Grasses - Plants - Shrubs](http://www.nexusmods.com/skyrim/mods/59774) - better grasses and shrubs. 
  Install plants only. 
  Install texture files manually as many of this mod plants can look oversaturated and not very lore-friendly.
- [ ] [Realistic Jazbay Grapes](http://www.nexusmods.com/skyrim/mods/70360) - better Jazbay grapes.
- [ ] [Unique Flowers And Plants](http://www.nexusmods.com/skyrim/mods/58091) - interesting region-specific plants.
- [ ] [Langleys Textures Workshop](http://www.nexusmods.com/skyrim/mods/26269) - various environmental texture improvements.
- [ ] [Daedric Armor and weapon Improvement](http://www.nexusmods.com/skyrim/mods/3104) - better Daedric armor. Get the all-in-one.
- [ ] [Realistic HD Food](http://www.nexusmods.com/skyrim/mods/62665) - better food, chickens, and other odds and ends.
- [ ] [Realistic HD Baskets](http://www.nexusmods.com/skyrim/mods/66008) - better baskets!
- [ ] [Enhanced Ore Veins](http://www.nexusmods.com/skyrim/mods/74836) - better ore veins, ingots, etc.
- [ ] [Arri's Snow Elf Ruins Retexture](http://www.nexusmods.com/skyrim/mods/68660) - Snow Elf ruins retexture.
- [ ] [Barenziah's Glory](http://www.nexusmods.com/skyrim/mods/63902) - better Barenziah's stone and armor textures.
- [ ] [Barset HQ](http://www.nexusmods.com/skyrim/mods/64938) - high quality barset for inns, taverns, and shops.
- [ ] [Better mammoth cheese](http://www.nexusmods.com/skyrim/mods/62991) - improved mammoth cheese textures.
- [ ] [Better ropes for skyrim](http://www.nexusmods.com/skyrim/mods/69313) - better ropes.
- [ ] [BLOODSTONE CHALICE REBORN](http://www.nexusmods.com/skyrim/mods/63551) - great bloodstone chalice retexture.
- [ ] [Book Covers Skyrim](http://www.nexusmods.com/skyrim/mods/35399) - unique book covers for almost all books in Skyrim.
- [ ] [Clothing Iron's retexture](http://www.nexusmods.com/skyrim/mods/74384) - clothing iron replacement.
- [ ] [RUSTIC DEATH HOUND](http://www.nexusmods.com/skyrim/mods/77415) - better death hounds.
- [ ] [RUSTIC GARGOYLE](http://www.nexusmods.com/skyrim/mods/77778) - better gargoyles.
- [ ] [Detailing the Eldrich - Higher-Res Apocrypha - Temple of Miraak - Black Books](http://www.nexusmods.com/skyrim/mods/45782) - improved black books.
- [ ] [Detailing the Eldrich - Higher-Res Riekling Architecture](http://www.nexusmods.com/skyrim/mods/46741) - improved architecture.
- [ ] [DOOR](http://www.nexusmods.com/skyrim/mods/65786) - better doors.
- [ ] [HD Whiterun Shack door](http://www.nexusmods.com/skyrim/mods/83229) - "THAT. AWFUL. DOORS. YOU SEE. EACH TIME. WHEN LEAVING. OR ENTERTING. THE HOUSE."
- [ ] [Dragonborn Clothing HD Retextures](http://www.nexusmods.com/skyrim/mods/54681) - better dragonborn clothing.
- [ ] [ELECTRIFY](http://www.nexusmods.com/skyrim/mods/58695) - better electric magic textures.
- [ ] [Falmer Ear and Hagraven Claw](http://www.nexusmods.com/skyrim/mods/74792) - odds and ends of Falmer and Hagravens.
- [ ] [Spider Egg Retexture](http://www.nexusmods.com/skyrim/mods/74336) - modified spider eggs.
- [ ] [Taproot 1K](http://www.nexusmods.com/skyrim/mods/74303) - better taproot.
- [ ] [Skeever Tail 1K](http://www.nexusmods.com/skyrim/mods/74291) - better skeever tail.
- [ ] [TROLL](http://www.nexusmods.com/skyrim/mods/68131) - improved troll textures.
- [ ] [WISPMOTHER](http://www.nexusmods.com/skyrim/mods/67525) - wispmother textures and meshes.
- [ ] [HAGRAVEN](http://www.nexusmods.com/skyrim/mods/67075) - improved hagraven textures.
- [ ] [Hagravens](http://www.nexusmods.com/skyrim/mods/74121) - previous mod retextures hagravens, this one retextures their building and other objects, so use them both.
- [ ] [FALMER](http://www.nexusmods.com/skyrim/mods/66770) - falmer textures.
- [ ] [GIANT](http://www.nexusmods.com/skyrim/mods/66428) - giant textures.
- [ ] [HORNCANDLES](http://www.nexusmods.com/skyrim/mods/66185) - horn candles for chandeliers.
- [ ] [Farmhouse Chimneys](http://www.nexusmods.com/skyrim/mods/51330) - adds chimneys, beautiful and immersive.
- [ ] [Fine Lute Texture](http://www.nexusmods.com/skyrim/mods/71994) - better lutes.
- [ ] [Frankly HD Miraak](http://www.nexusmods.com/skyrim/mods/75063) - better Miraak gear.
- [ ] [Gildergreen 4K Parallax](http://www.nexusmods.com/skyrim/mods/74498) - better textures for the Gildergreen tree in Whiterun.
- [ ] [HD Dark brotherhood door](http://www.nexusmods.com/skyrim/mods/53059) - another door fix.
- [ ] [HD Model Ship](http://www.nexusmods.com/skyrim/mods/74931) - thieves guild model ship.
- [ ] [Hectrol SPIDER WEBS Deluxe HighRes Retex](http://www.nexusmods.com/skyrim/mods/1731) - better spider webs.
- [ ] [IMMERSIVE LORE-FRIENDLY CHEESE AND CABBAGE](http://www.nexusmods.com/skyrim/mods/62603) - cheese and cabbage.
- [ ] [Insanitys City Banner Replacer](http://www.nexusmods.com/skyrim/mods/16791) - city banners.
- [ ] [Designs of the Nords](http://www.nexusmods.com/skyrim/mods/13429) - Nordic city banners.
- [ ] [Jewels of the Nord - HD rings and necklaces](http://www.nexusmods.com/skyrim/mods/27038) - improved jewelry.
- [ ] [JS Dragon Claws](http://www.nexusmods.com/skyrim/mods/75377) - better dragon claw textures.
- [ ] [Leather LeatherStrips and Leatherrack](http://www.nexusmods.com/skyrim/mods/74380) - leath retextures.
- [ ] [LEAVES](http://www.nexusmods.com/skyrim/mods/52733) - fallen leaves retexture (not the tree leaves).
- [ ] [Magic Runes HD](http://www.nexusmods.com/skyrim/mods/41052) - redone magic runes.
- [ ] [MANHOLE OF SOLITUDE](http://www.nexusmods.com/skyrim/mods/58959) - improved manhole covers.
- [ ] [MAPS](http://www.nexusmods.com/skyrim/mods/66819) - nice paper maps.
- [ ] [More Dramatic Alduin Retexture](http://www.nexusmods.com/skyrim/mods/54070) - casual Alduin retexture.
- [ ] [Better Shaped Female Creatures](http://www.nexusmods.com/skyrim/mods/51560) - adds more feminine look to many female creatures.
- [ ] [nightingale circle](http://www.nexusmods.com/skyrim/mods/74278) - better nightingale circle texture.
- [ ] [Nord Cattle - HD cows](http://www.nexusmods.com/skyrim/mods/29673) - cows!
- [ ] [Northfire's Skidmarks 1K-2K](http://www.nexusmods.com/skyrim/mods/72245) - landing skid marks for dragons.
- [ ] [OIL](http://www.nexusmods.com/skyrim/mods/59714) - oil retexture.
- [ ] [PELTAPALOOZA - Pelts of Skyrim Expansion](http://www.nexusmods.com/skyrim/mods/60412) - improved textures and look for pelts.
- [ ] [Project Skyrim HD - College of Winterhold](http://www.nexusmods.com/skyrim/mods/43063) - overhaul retexture for College of Winterhold
- [ ] [Brawl Bug Plugin](https://www.nexusmods.com/skyrim/mods/24020) - fix for effect and player state bug.
- [ ] [Campfire - Complete Camping System](https://www.nexusmods.com/skyrim/mods/64798) - immersive camping experience.
- [ ] [HQ Snow Texture](https://www.nexusmods.com/skyrim/mods/743) - better snow. NOTE: might be redundant.
- [ ] [Get Snowy](https://www.nexusmods.com/skyrim/mods/19660) - adds snow to NPC's and objects under snowfall.
- [ ] [Dynamic Ash](https://www.nexusmods.com/skyrim/mods/84806) - better environmental ash.
- [ ] [Rens HD Shrines](http://www.nexusmods.com/skyrim/mods/50327) - better shrines.
- [ ] [Rens HD Flame Atronach](http://www.nexusmods.com/skyrim/mods/51456) - flame Atronach improvements.
- [ ] [Seeker and Lurker - Creature Retex](http://www.nexusmods.com/skyrim/mods/73321) - seeker and lurker retextures.
- [ ] [Storm Atronach - Creature Retex](http://www.nexusmods.com/skyrim/mods/73385) - storm atronach retexture.
- [ ] [Ice Wraith Retexture](http://www.nexusmods.com/skyrim/mods/32741) - ice wraith and dragon priest retexture.
- [ ] [Stunning Statues of Skyrim](http://www.nexusmods.com/skyrim/mods/56588) - improved, customizable statues.
- [ ] [tamu75 Terrain Parallax Textures](http://www.nexusmods.com/skyrim/mods/61416) - apply if preferred.
- [ ] [Troll Skull 4kHD](http://www.nexusmods.com/skyrim/mods/58681) - manual retexture for troll skull.
- [ ] [Ultra HD Rags Retexture](http://www.nexusmods.com/skyrim/mods/72847) - more interesting rag textures.
- [ ] [Upgrade for Large imperial tent](http://www.nexusmods.com/skyrim/mods/68631) - a better mesh and texture for large imperial tents.
- [ ] [Vandr Presents - HD Falmer Pod](http://www.nexusmods.com/skyrim/mods/6936) - improved falmer pods.
- [ ] [WATERplants - retexture by Pfuscher](http://www.nexusmods.com/skyrim/mods/57868) - retextured water flora.
- [ ] [Weathered Road Signs](http://www.nexusmods.com/skyrim/mods/2810) - retextured road signs.
- [ ] [White Phial Replacer](http://www.nexusmods.com/skyrim/mods/54078) - retextured white phials.
- [ ] [Windhelm Enhanced - HD 4k Grey Quarter Flags](http://www.nexusmods.com/skyrim/mods/74720) -
- [ ] [Windhelm Enhanced - HD 4k Metalwork](http://www.nexusmods.com/skyrim/mods/74830) -
- [ ] [Windhelm Enhanced - 500 Companions Wall 8k HD Retexture](http://www.nexusmods.com/skyrim/mods/74942) -
- [ ] [Skyrim Landscape Overhaul - Stone Walls](http://www.nexusmods.com/skyrim/mods/76359) - mesh and texture replacer for the freestanding stone walls. 
- [ ] [Nightingale Pride - Bow and Blade Reincarnation](http://www.nexusmods.com/skyrim/mods/33704) - improved textures for nightingale bow and blade.
- [ ] [Nightingale Prime](https://www.nexusmods.com/skyrim/mods/28899) - makes nightingale armor look better.
- [ ] [Daedric Armor and Weapons](https://www.nexusmods.com/skyrim/mods/3104) - improves daedric textures.
- [ ] [Frankly HD Silver Sword](http://www.nexusmods.com/skyrim/mods/29563) - well created silver sword.
- [ ] [Lockpicking Interface Redone](http://www.nexusmods.com/skyrim/mods/63279) - better lock picking.
- [ ] [Frankly HD Stormcloak and City Guards](http://www.nexusmods.com/skyrim/mods/42404) - retexture for guards.
- [ ] [Embers HD](http://www.nexusmods.com/skyrim/mods/62425) - meshes, textures, and effects for embers from fire. 
- [ ] [High Poly Project](http://www.nexusmods.com/skyrim/mods/76439) - model improvements similar to SMIM.
- [ ] [Footprints](https://www.nexusmods.com/skyrim/mods/22745) - adds player footprints on snow.
- [ ] [Splash of Rain](https://www.nexusmods.com/skyrim/mods/37873) - adds rain splash effects.
- [ ] [DYNAVISION](https://www.nexusmods.com/skyrim/mods/12525) - dynamic depth of field.
- [ ] [Point The Way](https://www.nexusmods.com/skyrim/mods/33393) - adds signposts around Skyrim.

## DynDOLOD

- [ ] [Dynamic Distant Objects LOD - DynDOLOD](http://www.nexusmods.com/skyrim/mods/59721) - a tool for generating and rendering distant objects. 
  Essentially, this mod makes everything far away look like it should. 
  However, I had some difficulties installing it due to Windows' awful file system capitalization ambiguity. 
  The main issue with the mod is that the resources core files are packaged inconsistently: while some files are meant for Data/Textures, others are meant for Data/textures. 
  However, there can only be one such folder, and any files intended to be moved to the other are ignored with no warning. 
  To fix this without simply copying the files and directories over, I downloaded the manual installation package, renamed the offending file paths according to what was already in my Data folder, and repackaged it as a zip file. 
  I then installed that mod from my local file system. Make sure to follow the actual instruction manual. 

## Player

- [ ] [RaceMenu](http://www.nexusmods.com/skyrim/mods/29624) - disables character creator cache and provides support for complex character creation.
- [ ] [Caliente's Beautiful Bodies Edition -CBBE-](http://www.nexusmods.com/skyrim/mods/2666) - better female body models.
- [ ] [Fitness Body](http://www.nexusmods.com/skyrim/mods/16731) - fitness blender for female models.
- [ ] [Mature skin texture and body for UNP(B) 7BASE CBBE Vanilla](http://www.nexusmods.com/skyrim/mods/32986) - skin tone and coloration for aging.
- [ ] [Better males - Beautiful nudes and faces - New hairstyles](http://www.nexusmods.com/skyrim/mods/2488) - better male body models.
- [ ] [Natural Eyes](http://www.nexusmods.com/skyrim/mods/3589) - basic eye textures for full range.
- [ ] [Lind's Human Eyes](http://www.nexusmods.com/skyrim/mods/75674) - beautiful human eye textures.
- [ ] [Lind's Elven Eyes](http://www.nexusmods.com/skyrim/mods/74948) - beautiful elven eye textures.
- [ ] [Superior Lore-Friendly Hair - HD textures](http://www.nexusmods.com/skyrim/mods/36510) - well-rounded textures and meshes for hairstyles.
- [ ] [ApachiiSkyHair](http://www.nexusmods.com/skyrim/mods/10168) - more hairstyles.
- [ ] [XCE - Warpaint and Dirt](http://www.nexusmods.com/skyrim/mods/29977) - facial war paint options.
- [ ] [High Resolution Scars](http://www.nexusmods.com/skyrim/mods/4784) - facial scars.
- [ ] [Northborn Scars](http://www.nexusmods.com/skyrim/mods/49279) - scares of the Northborn.
- [ ] [Beards](http://www.nexusmods.com/skyrim/mods/28363) - better beards.
- [ ] [The Art of Beard - New Facial Hairs](http://www.nexusmods.com/skyrim/mods/72961) - more facial hair options.
- [ ] [Brows](http://www.nexusmods.com/skyrim/mods/30411) - eyebrow options.
- [ ] [Smile in HD](http://www.nexusmods.com/skyrim/mods/34346) - better mouth textures.
- [ ] [Enhanced Camera](https://www.nexusmods.com/skyrim/mods/57859) - more immersive first-person camera.
- [ ] [RaceMenu](https://www.nexusmods.com/skyrim/mods/29624) - overhauls character creation menu.
- [ ] [Improved closefaced helmets](https://www.nexusmods.com/skyrim/mods/15927) - see player's face under helmets.

## Lanterns

- [ ] [Campfire](https://www.nexusmods.com/skyrim/mods/64798/) - adds camping and camping equipment.
- [ ] [Wearable Lanterns](https://www.nexusmods.com/skyrim/mods/17416/) - added as an afterthought because I saw the HDT mod. Adds lanterns that illuminate the area around you.
- [ ] [Wearable Lanterns SMIM Patch](https://www.nexusmods.com/skyrim/mods/34535/) - SMIM compatibility.

## Physics

- [ ] [HDT Physics Extensions](http://www.nexusmods.com/skyrim/mods/53996) - required to run further physics extensions.
- [ ] [HDT HighHeels System](http://www.nexusmods.com/skyrim/mods/36213) - modifies the height of different footwear.
- [ ] [HDT Breast And Butt Physics - TBBP BBP Supported](http://www.nexusmods.com/skyrim/mods/54044) - add some sexy physics.
- [ ] [HDT Equipment](http://www.nexusmods.com/skyrim/mods/57408) - moving slings and sheathes. Add the lanterns as well.
- [ ] [Dead Body Collision Fix](https://www.nexusmods.com/skyrim/mods/30947) - adds collision to dead bodies.

## Odds and Ends
- [ ] [NetImmerse Override](https://www.nexusmods.com/skyrim/mods/37481) - runtime shader overrides.
- [ ] [Double Cursor Fix](https://www.nexusmods.com/skyrim/mods/36125) - fixes double cursor when alt-tabbing.
- [ ] [Skyrim Project Optimiation](https://www.nexusmods.com/skyrim/mods/32505) - FPS boost, **get No Homes Full**.
- [ ] [Skyrim Performance PLUS](https://www.nexusmods.com/skyrim/mods/6387) - more FPS boost.
- [ ] [HIALGOBOOST GPU Upgrade](https://www.nexusmods.com/skyrim/mods/15123) - even more FPS boost.
- [ ] [Multiple Floors Sandboxing](https://www.nexusmods.com/skyrim/mods/57376) - changes sandboxes so NPCs move floors.
- [ ] [Better Dialogue Controls](https://www.nexusmods.com/skyrim/mods/27371) - improves selecting dialogue options.
- [ ] [Better MessageBox Controls](https://www.nexusmods.com/skyrim/mods/28170) - allows keyboard controls in message boxes.

## Animation
- [ ] [Fores New Idles in Skyrim](https://www.nexusmods.com/skyrim/mods/11811) - idle animations.
- [ ] [Realistic Ragdolls and Force](https://www.nexusmods.com/skyrim/mods/601) - ragdoll movement.
- [ ] [XP32 Maximum Skeleton Extended](https://www.nexusmods.com/skyrim/mods/68000) - skeleton improvements.
- [ ] [Dual Sheath Redux](https://www.nexusmods.com/skyrim/mods/34155) - sheaths left-hand weapon.
- [ ] [Sexy Move](https://www.nexusmods.com/skyrim/mods/54521) - changes female movement.

## NPCs

- [ ] [Bijin Warmaidens](http://www.nexusmods.com/skyrim/mods/40038) - adds an array of female Bijin characters.
- [ ] [Bijin Wives](http://www.nexusmods.com/skyrim/mods/63473) - permits marriage to Bijin women.
- [ ] [Bijin NPCs](http://www.nexusmods.com/skyrim/mods/71054) - adds other Bijin NPC's.
- [ ] [The Ordinary Women](http://www.nexusmods.com/skyrim/mods/70547) - improved NPC women models.
- [ ] [NPCs of Dibella](http://www.nexusmods.com/skyrim/mods/27427) - various thematic NPC's.
- [ ] [Seranaholic](http://www.nexusmods.com/skyrim/mods/38326) - Serana overhaul.
- [ ] [Skyrim Ladies - Aela and Astrid](http://www.nexusmods.com/skyrim/mods/69467) - overhaul Aela and Astrid.
- [ ] [Avelyn or Elisif](http://www.nexusmods.com/skyrim/mods/63903) - a new standalone follower Elisif.
- [ ] [Males of Skyrim](http://www.nexusmods.com/skyrim/mods/61937) - awesome and lore-friendly males.
- [ ] [The Men of Winter](http://www.nexusmods.com/skyrim/mods/74376) - more well-done men models.
- [ ] [Vilkas and Farkas by Netherwalk](http://www.nexusmods.com/skyrim/mods/21540) - two male followers.
- [ ] [TDN Improved Lucien - Spectral Assassin Replacer](http://www.nexusmods.com/skyrim/mods/62835) - replacement for Lucien.
- [ ] [Improved Bards](http://www.nexusmods.com/skyrim/mods/56599) - changes appearance of bards.
- [ ] [The College of Winterhold - NPC Improvement](http://www.nexusmods.com/skyrim/mods/67359) - college of Winterhold NPC improvements.
- [ ] [Clothing and Clutter Fixes](https://www.nexusmods.com/skyrim/mods/43053) - fixes clothes bugs.
- [ ] [Ultimate Follower Overhaul](https://www.nexusmods.com/skyrim/mods/14037) - improves follower system.
- [ ] [Marriable Serana](https://www.nexusmods.com/skyrim/mods/28685) - allows marrying Serana.
- [ ] [Immersive Patrols](https://www.nexusmods.com/skyrim/mods/12977) - adds patrols around Skyrim.
- [ ] [Interesting NPCs](https://www.nexusmods.com/skyrim/mods/8429) - adds dialogue to various NPCs.
- [ ] [Guard Dialogue Overhaul](https://www.nexusmods.com/skyrim/mods/23390) - gives guards new dialogue.
- [ ] [Inconsequential NPCs](https://www.nexusmods.com/skyrim/mods/36334) - adds a bunch of new NPCs.
- [ ] [Run For Your Lives](https://www.nexusmods.com/skyrim/mods/23906) - ordinary citizens hide during dragon attacks.
- [ ] [Fuz Ro D-oh](https://www.nexusmods.com/skyrim/mods/14884) - adds voice animation for silent dialogue.

## Audio

## Gameplay
- [ ] [Open Cities](https://www.nexusmods.com/skyrim/mods/8058) - makes major cities part of Skyrim.
- [ ] [Sneak Tools](https://www.nexusmods.com/skyrim/mods/19447) - stealth overhaul.
- [ ] [Lock Overhaul](https://www.nexusmods.com/skyrim/mods/29979) - better lockpicking.
- [ ] [Auto Unequip Ammo](https://www.nexusmods.com/skyrim/mods/10753) - unequips quiver when out of combat.
- [ ] [Deadly Dragons](https://www.nexusmods.com/skyrim/mods/3829) - customize difficulty of dragon fights.
- [ ] [Dibella's Compulsion](https://www.nexusmods.com/skyrim/mods/30072) - adds spell to remove clothing.
- [ ] [Breezehome FullyUpgradeable](https://www.nexusmods.com/skyrim/mods/11158) - greatly expands Breezehome.
- [ ] [Improved Dragon Shout](https://www.nexusmods.com/skyrim/mods/14353) - tweaks all dragon shouts.
- [ ] [Rich Merchants](https://www.nexusmods.com/skyrim/mods/769) - gives more gold to merchants.
- [ ] [Trade and Barter](https://www.nexusmods.com/skyrim/mods/34612) - overhauls trading system.
- [ ] [Convenient Horses](https://www.nexusmods.com/skyrim/mods/14950) - overhauls horses.
- [ ] [Dual Wield Parrying](https://www.nexusmods.com/skyrim/mods/9247) - allows parrying while dual wielding.
- [ ] [Better Arrows](https://www.nexusmods.com/skyrim/mods/13185) - arrows fly faster.
- [ ] [TK Dodge](https://www.nexusmods.com/skyrim/mods/20923) - allows dodging in combat.
- [ ] [Locational Damage](https://www.nexusmods.com/skyrim/mods/12615) - more damage when hitting certain body parts.
- [ ] [The Dance of Death](https://www.nexusmods.com/skyrim/mods/10906) - adds new killmoves.
- [ ] [Apocalypse - Magic of Skyrim](https://www.nexusmods.com/skyrim/mods/16225) - adds new spells.
- [ ] [Immersive Weapons](https://www.nexusmods.com/skyrim/mods/27644) - adds lots of new weapons.
- [ ] [Immersive Armors](https://www.nexusmods.com/skyrim/mods/19733) - adds lots of new armors.
- [ ] [Weapons and Armor Fixes Remade](https://www.nexusmods.com/skyrim/mods/34093) - tweaks armor and weapon stats.
- [ ] [Enchanted Arsenal](https://www.nexusmods.com/skyrim/mods/56614) - makes enchanted items cooler.
- [ ] [Acquisitive Soul Gems](https://www.nexusmods.com/skyrim/mods/5312) - fixes soul gem mechanics.
- [ ] [Lore-Based Loading Screens](https://www.nexusmods.com/skyrim/mods/21265) - adds new loading screens.
- [ ] [No Menu and Loading Smoke](https://www.nexusmods.com/skyrim/mods/7901) - removes smoke for ENB compatibility.
- [ ] [Even Better Quest Objectives](https://www.nexusmods.com/skyrim/mods/32695) - adds more descriptive quest objectives.

## Quests
- [ ] [The Paarthurnax Dilemma](https://www.nexusmods.com/skyrim/mods/18465) - allows saving Paarthurnax.
- [ ] [The Forgotten City](https://www.nexusmods.com/skyrim/mods/70219) - new award-winning quest.

## Wildlife
- [ ] [Immersive Creatures](https://www.nexusmods.com/skyrim/mods/24913) - adds many new creatures.
- [ ] [Hunting in Skyrim](https://www.nexusmods.com/skyrim/mods/18866) - completely new hunting system.
- [ ] [Birds of Skyrim](https://www.nexusmods.com/skyrim/mods/17723) - adds many new birds.

## Patches
- [ ] [Birds of Skyrim Patches](https://www.nexusmods.com/skyrim/mods/72833) - 
- [ ] [Open Cities Patches](https://www.nexusmods.com/skyrim/mods/59937) - 
