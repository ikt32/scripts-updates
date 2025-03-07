# Handling guide
{:.no_toc}

* A markdown unordered list which will be replaced with the ToC
{:toc}

The scripts build upon the base handling parameters the game provides, and
use its existing physics. This means some work is needed to create an optimal
experience. In the following sections I go over the work that's needed to
achieve this.

## Powertrain

[Custom Torque Map](5-ctm-readme), [Custom Gear Ratios](5-cgr-readme) and
[TurboFix](5-turbofix-readme) are needed to change how the game simulates
the drivetrain, from how the engine (with or without turbos) behaves, to the
gearing used to apply that power to the ground.

Gear ratios are easy and can be applied from common databases easily. While
"final drive" is not directly applicable to the game, this can be approximated
with the top speed (per gear) values from these databases. I use
[Automobile-Catalog](https://www.automobile-catalog.com) to gather this info.

For NA and supercharged engines, taking a dyno run output and stuffing it into
CTM (Custom Torque Map) gets you close enough regarding engine behavior.
Taking the peak torque output in N⋅m and using that in the `handling.meta`
(`fInitialDriveForce = torqueNm/curbWeightKg`) gets you nearly on the spot.

For turbo engines, it's a bit trickier. My approach is to find a similar NA
variant of the engine, taking those torque numbers, and using TurboFix to create
the corresponding boost power and spool-up to match up with the actual behavior.

To tune the top speed **for stock gear ratios**, use the following formula:
`fInitialDriveMaxFlatVel = topGearMaxSpeedKph*0.75`

This is because there is a 1.2 factor between `fInitialDriveMaxFlatVel` and
an internal top speed variable. On top of that, the top gear ratio is usually
0.9. Just take the top speed achievable with the top gear and use this number
here - this should be your baseline handling.meta top speed,
before applying custom gear ratios.

## Grip and handling feel

The default handling in GTA V has two main issues:

* Slip angles are too high. This results a very vague steering feel and with
  the levels in GTA V, even causes significant delay between the front wheels
  turning and the car changing direction. When the car is turning, the back
  wheels can slide around an unrealistic amount causing even more vagueness.
  This may feel like using soft balloons as tires.
* Grip levels are too high. This results in the car turning too quickly and
  very strong force feedback once you do crank the wheel enough.

While this is fine for arcade driving with GTA V's quick and responsive
steering model made for keyboards and controllers, this is completely unsuitable
for steering wheel inputs.

Check [Manual Transmission's readme](5-gears-readme#handling-for-force-feedback)
for tips to set up handling with grip levels and slip angles. The general gist:
lower is better.

Ever since Manual Transmission 5.5.0, wheel slip angle data is used as main
component for force feedback calculations, where you feel the results of these
high slip angles and grip values.

Especially when driving on the
[many ported tracks](https://www.gta5-mods.com/maps/tags/map-model+racetrack),
you'll feel the car behaving as it should once the handling has more realistic
slip angle and grip level values.

## Other stuff

Generally this has mostly been covered by the community, so I won't repeat
too much. [Eddlm has a great guide.](https://eddlm.github.io/Handling-Tools/guide)

My [Real Time Handling Editor script](https://www.gta5-mods.com/tools/real-time-handling-editor)
also contains a bunch of tips, embedded inside the script menu, from
[this repository](https://github.com/ikt32/GTAVHandlingInfo).

Finally, I've contributed to [GTACars.net](https://gtacars.net/gta5/glossary),
which also is a good source to get familiar with the workings.

Other `handling.meta` settings I always change:

* Reduce `fInitialDragCoeff`
* Adjust `fInitialDriveMaxFlatVel` to match Custom Gear Ratio values
* Set `fLowSpeedTractionLossMult` to 0.0
* Enable the `FREEWHEEL_NO_GAS` handling flag so cars don't slow off-throttle excessively
* Enable the `TYRES_CAN_CLIP` flag to simulate tire compression
* Check if the ABS flags are accurate for the car

If you'd like to ask about specific things in handlings, feel free to reach out
on the Discord server in the page header!
