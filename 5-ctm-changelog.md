# Changelog for Custom Torque Map

## 1.1.0

* Require a license to use
* Add a tachometer, inspired by [the Nissan 300ZX](https://www.youtube.com/watch?v=xGmNuuoyiYQ), using real power curve
* Add power curve to engine map visualizer
* Add new torque and power calculations for current vehicle, and option to change visualization:
  * Relative (0.5x of max torque/power)
  * Metric (kW and N⋅m)
  * Imperial (hp and lb⋅ft)
* Add peak power/torque numbers for current vehicle
* Accurately represent default torque behavior for 2nd gear and up

Additional notes: Actual torque and power calculations still require a player vehicle,
as `fInitialDriveForce` and `fMass` are used to calculate torque. In addition, the idle and rev limit RPMs also need to
be specified to calculate everything. Once you have a good configuration, all numbers should pop out accurately.

## 1.0.2

* Add support for `{actual_rpm}|{actual_torque}` in the torque map.
  Conversion to relative numbers is not required any more.
  Check `CustomTorqueMap/Configs/VAG 4.2 V8 FSI 32v.ini` for an example.
* Fix crash on invalid/missing config
* Fix crash on missing vehicle
* Update dependencies

## 1.0.1

* Add exported function to retrieve idle, rev limit and actual RPM if those are defined
* Fix mapped "actual" RPM reporting below 0.2 RPM

## 1.0.0

* Initial release
