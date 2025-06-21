# Changelog for Manual Transmission for GTA V

## 5.8.1

* Update patches for Enhanced 1.0.889.15
* Fix keyboard and wheel button "tap" action
* Fix recognizing extended keys (function cluster)
* Fix hotwiring animations not playing with synced steering animations
* Remove usage of ScriptHookV's `getScriptHandleBaseAddress` for FiveM compatibility

Notes:

* Button tap action fix may or may not fix flickering indicators and assists.
  I'd happy happy to hear if this did anything or if I need to look further.
  Details are appreciated, I haven't managed to reproduce it.

## 5.8.0

* Add handbrake hold-to-toggle functionality<br>
  To use: Enable in Gameplay Assists. Hold handbrake for 0.5 seconds to keep it on.
  Disengage by driving away or briefly tapping the handbrake.
* Update game version detection
* Update patches and vehicle offset for Enhanced
* Fix force feedback per-vehicle curve multiplier not applied
* Fix analog handbrake doing nothing when Manual Transmission is off

## 5.7.3

* Add support for externally cancelled indicators (e.g. Moza Multifunction Stalks)<br>
  To use: Unassign old indicator buttons and assign new
  `Indicator left/right/cancel (stalk)` buttons
* Fix broken collision force feedback since 5.7.0
* Improve collission effect using jerk and directionality
* Fix telemetry RPM x10 issue for SimHub etc. (Still same DiRT 4 format)
* License: Fix an issue that causes added hardware possibly causing premature license expiration

## 5.7.2

* Hotfix for 5.7.1: Fix camera spinning when using wheel

## 5.7.1

* Add analog camera support for steering wheels
* Improve re-identification support for composite devices, e.g. newer Fanatec wheelbases
* Allow manual input for HUD element locations
* UDP Telemetry: Read fuel volume from handling instead of fixed 65L
* Fix last analog axis (Slider1) not being picked up during assignment
* Fix nonfunctional buttons for analog actions

## 5.7.0

* Add a demo mode for 15 minutes x 4 trial usage
* Add force feedback effects for surface textures
* Automatically resolve devices with changed Instance GUIDs
* Clarify "Enhanced Steering"-related descriptions in the menus
* Rename confusing force feedback settings
* Improve steering wheel devices initialization
* Improve force feedback initialization

## 5.6.3

* Improve license check for switchable GPU systems

## 5.6.2

* Require a license to use
* Fix traction control acting with too little wheelspin
* Fix adaptive cruise control
* Update for b3095+ compatibility

## 5.6.1 and older

Changelogs for older versions can be found [in the original repository](https://github.com/ikt32/GTAVManualTransmission/blob/master/doc/changelog.md).
