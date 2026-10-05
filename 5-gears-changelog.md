# Changelog for Manual Transmission for GTA V

## 5.9.1

* Fix FFBv3 not working on Legacy
* Revert FFB playback to more compatible method (Fixes Moza wheels having no FFB)
* Fix FFB shutdown keeping game process open

## 5.9.0

While developing my upcoming handling overhaul, the steering feel in Manual Transmission still did not feel entirely right. Specifically the initial force feedback build up as you start cranking the wheel, which still didn't feel communicative enough unless I cranked up the responsivity curve, but that muddied away finer details when the steering force was strong.

I dove back into finding a better way and I think this is the best I can extract from GTA V. This update introduces an improved force feedback model, and when paired with the handling overhaul, should push the game to feel pretty realistically. Of course the physics model isn't actual simulation-tier, but this is pretty convincing from my personal experience, when comparing it against titles like BeamNG or AC Evo, on a Fanatec CSL DD 8Nm wheel base.

Changelog:

* Introduce new force feedback model
  * Main steering forces are based on per-wheel tyre forces.
  * Add tunable vertical load component to communicate surface shape and transiant weight transfer (effectively replaces suspension force feedback).
  * Replace old wheel friction effect with tyre scrub, steering rack resistance and viscous damping.
  * Feed force feedback with surface grip information to communicate decreased grip.
  * Improve surface material force feedback effect generation/calculation.
  * The previous force feedback model is still available and can be selected, if that's preferred.
  * Removed `AntiDeadForce`, use a force feedback LUT if your wheel has force feedback deadzone. Applies to both force feedback models.
  * Improve wheel (re)initialization and force feedback recovery stability.
* Manual Transmission now supports automatic gearbox hints from `BaseAutomaticHints.json` and vehicle configs.
* Automatic gearboxes now simulate sequential-style, double-clutch and torque converter-type modes, which changes how the clutch/throttle interact during shifting events.
* Automatic gearboxes now can slip the clutch when accelerating from a stop, as to not bog down the engine.
* Enhanced Steering mode now has an optional slip-angle aware steering angle limiter now.
* NPC gearboxes may now skip multiple gears on downshifts, for more competitive NPCs.
* Cruise control now supports throttle input to allow accelerator override.
* Cruise control now ignore clutch input, to allow manual shifting while cruise control is active.
* Cruise control commanded throttle/brake values are now displayed in the pedal info HUD element.
* Export wheel input state and processed horizontal/vertical camera input through the script API, for camera-script integration.

Fixes:

* Fix clutch bit point not used properly for engine lockup, engine braking, RPM behavior with clutch bite point and hill gravity.
* Fix swapped y/z axes in reported UDP telemetry position/velocity/direction vectors.

Minor changes:

* All decimal values in the menu now accept keyboard input for quicker editing.

Notes:

* The new and previous force feedback models have separate tuning settings.
* Remember to set the wheelbase maximum torque to your wheelbase's rated torque so force feedback scales properly.

## 5.8.5

* HUD: Add handbrake bar to pedal input box
* Wheel: Make toggling handbrake optional for analog handbrakes
* Wheel: Fix force feedback spring effect not being disabled on launch
* Fix Native controller input method triggers
* Fix features coupled to first person camera mode not working with independent camera modes
* Fix quadbikes having lean forces disabled
* Fix telemetry direction vectors missing forward vector and wrong right vector

## 5.8.4

* Resolve `getScriptHandleBaseAddress` dynamically for FiveM compatibility

## 5.8.3

* Update memory code for Legacy 1.0.3788.0, fixing crashes
* Update memory code for Enhanced 1.0.1013.33
* Update menu for Enhanced record global
* Update menu for hotkey falsely triggering on camera switch
* Fix wheel button-axis override input detection
* Fix Native gamepad inputs wrongly triggering
* Increase UpshiftLoad top range from 0.2 to 1.0

## 5.8.2

* Fix flickering inputs caused by unmapped keyboard values reading invalid data
* Fix and restore older "hold to X" behavior on gamepad to pre-5.8.0 behavior

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
