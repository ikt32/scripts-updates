# Changelog for TurboFix for GTA V

## 2.4.0

* Update compatibility for game build 3095 and newer (last tested build: 3351)
* Fix particle fx for modkit exhausts after tuning, thanks to [AlexGuirre](https://github.com/alexguirre)!
* Add API functions for detailed boost retrieval
  * `TF_GetAbsoluteBoostConfig`
  * `TF_GetActiveConfigName`

## 2.3.0

* Add boost falloff parameters, which can be used to simulate smaller turbos

## 2.2.0

* Update default anti-lag soundset to a more realistic and subtle version, thanks to **Dieguuds**!
* Remove Enable toggle. The script is always active.
* Only support single model and single plate configs. Existing configs are still compatible, but only the first model and plate are used.
* Move saving out of configuration menu, into its own menu, with multiple options.
  * Overwrite save: Save current settings over old settings
  * Specific save: Save current settings for the specific vehicle+plate combination
  * Generic save: Save current settings for the vehicle model
  * Non-associated save: Save without any autoloading capability
* Add loading functionality: Any configuration can now be loaded into the current configuration.
* Saving only asks for configuration name, as model is saved automatically. Install [Add-on Spawner](https://www.gta5-mods.com/scripts/add-on-vehicle-spawner) so the script can also always figure out the correct model name, to write to in the config file.
* Add turbo stats on main page
* Fix anti-lag soundset index for menu

## 2.1.0

* Allow setting minimal RPM for anti-lag
* Fix anti-lag on reverse
* Fix issues when reloading a save
* Improve anti-lag fall-off

## 2.0.2

* Support any number of sounds in a sound set

It will search the sound set folder for any EX_POP_<number>.wav file until it finds none. E.g. EX_POP_0.wav through EX_POP_15.wav

## 2.0.1

* Fix issue with saving configs

## 2.0.0

* Full rewrite
* Support NPC vehicles
* Add Anti-lag
* Add particle fx for anti-lag
* Add Sound effects for anti-lag

## 1.1.0

* Disable R* boost limitation
* Allow keyboard editing for turbo values
* Add API exposing absolute and mapped boost levels
* Correctly map turbo gauges using DashHook

## 1.0.0

* First release
