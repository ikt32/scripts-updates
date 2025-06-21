# TurboFix
{:.no_toc}

Overhauls how the turbo works, for more useful performance and new effects.

![TurboFix](resources/5TurboFix.png)

<a href="https://github.com/ikt32/scripts-updates/releases?q=%22TurboFix%22"
   target="_blank"
   class="download-button"
   title="View and download all releases on GitHub">📥Releases</a>

* ToC Placeholder
{:toc}

## Features

* Unlock turbo boost limits  
  The original turbo only adds 10% torque when fully spooled up.  
  This script unlocks that for much more boost and resulting power!  
* Better turbo spooling  
  The original turbo takes a very long time to spool up to full boost.  
  This script makes it to spool up as quickly as your configuration allows, for realistic turbo lag.  
* Anti-lag and effects  
  Optionally simulate anti-lag by keeping boost high off-throttle.  
  Optionally play visual and audio effects while anti-lag is active!  
  Works best combined with Manual Transmission  
* Supports NPC vehicles  
  Combines great with ARS by Eddlm for competitive AI performance  
* Turbo dial adjustments with DashHook  
  Vehicles' turbo dials are remappable to accurately show boost  

## Requirements

* Grand Theft Auto V
* [ScriptHookV](http://www.dev-c.com/gtav/scripthookv/)
* A valid license [(Patreon)](https://www.patreon.com/ikt)

Optional:

* [DashHook](https://www.gta5-mods.com/tools/dashhook)
* [Manual Transmission](https://github.com/ikt32/scripts-updates/blob/master/5-gears-readme.md)

### Activation

A license is required to use TurboFix v2.4.0 and newer.
You can get one by pledging on [Patreon](https://www.patreon.com/ikt).
The script will inform you when you need to generate or renew the license.

## Installation

1. Drag and drop the following files into your GTA V folder.
   1. `TurboFix.asi`
   2. `TurboFix` folder
   3. `irrKlang.dll`
2. In-game: Immediately works for all cars with the turbo tuning upgrade installed
3. In-game: Use `turbofix` cheat to open the menu (see "Menu opening")
   1. Menu can be used to view, customize and save configurations

## Menu opening

1. Open the cheat box with tilde key (~)
2. Enter the "turbofix" cheat without quotes

The menu opening cheat and other shortcuts may be changed in `settings_menu.ini`.
Usable buttons are in `Keys_Controls.txt`.

## Creating configs from scratch

Configs can be manually made when not using the in-game menu, check `TurboFix/Configs/INSTRUCTIONS.txt` for info.

## Adding sounds

Sound sets can be added by creating a new folder in the Sounds folder. Files need to be of type `.wav`.

Files inside the new folder should be named:

* `EX_POP_0.wav`
* `EX_POP_(number).wav`
* `EX_POP_SUB.wav`

For example, to get 16 sounds playing, name your files `EX_POP_0.wav` through `EX_POP_15.wav`.

The script randomly picks a numbered exhaust sound. `EX_POP_SUB.wav` always plays.

## Developers

In the release archive, in `TurboFix/Developers`, the current header with exposed TurboFix functions is available.

This can be used to retrieve the mod status and applicable boost information.

## Credits

* Audio for anti-lag by Dieguuuds
