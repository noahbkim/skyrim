# Skyrim Modding Guides

This repository contains a couple guides I've accumulated or created for overhauling Skyrim's graphics and gameplay.
Feel free to message me if you'd like to contribute or offer suggestions.

Here is my current project:
* [Ultimate Skyrim](ultimate.md)

## Prerequisite Software

- [Skyrim Script Extender](http://skse.silverlock.org/) - an external script loader used for almost all mods, plugins, and tweaks. 
  Can be conveniently installed via Steam. 
- [LOOT](https://loot.github.io/) - a tool that manages dependencies and plugin load order. 
  Crucial to maintaining stability with large numbers of mods.
  Also useful for checking if there are unmet dependencies.
- [TES5edit](http://www.nexusmods.com/skyrim/mods/25859/?) - a plugin manipulation tool that provides mod comparison and conflict detection/resolution.
- [Save Game Script Cleaner](http://www.nexusmods.com/skyrim/mods/52363/?) - tool for managing plugin assets and scripts in save game data. 
  Useful if you want to remove mods during a game, but not necessary.
- [Windows Texture Viewer](http://www.nvidia.com/object/windows_texture_viewer.html) - a small viewer for `.dds` texture files that allows you to compare conflicting assets between mods.
This is also useful if you want to be able to compare the aesthetic of conflicting mod packs.
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

## Modding Methodology

As a note, don't try to install all of the listed mods without intermediate testing, as there's a much lower chance of it working that way. 
Instead, install a group of mods, sort them with LOOT, and test Skyrim to make sure everything works. 
Also make sure to keep track of your progress as you go. 

Another thing to think about is how long it will take for some mods to download. 
I would recommend queueing a bunch of the listed mods in advance so they download while you're configuring earlier ones (especially texture mods).