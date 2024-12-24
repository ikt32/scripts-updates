# FAQ
{:.no_toc}

* A markdown unordered list which will be replaced with the ToC
{:toc}

## License and subscription

### Q: Where can I get your new mods?

A: They're available [through my Patreon](https://patreon.com/ikt){:target="_blank"}. The "how does this work"
is explained in the Supporter tier membership and in the [readme of License Generator](licgen-readme){:target="_blank"}.

My Patreon-exclusive scripts for now are updated versions of:

* [Manual Transmission](5-gears-readme){:target="_blank"}
* [Custom Gear Ratios](5-cgr-readme){:target="_blank"}
* [Custom Torque Map](5-ctm-readme){:target="_blank"}
* [TurboFix](5-turbofix-readme){:target="_blank"}

These all use the same license system.

### Q: Can I pay once and use your new scripts forever?

A: Yes, the license you generate *while subscribed* is valid for *however long you use your PC in its current form*.

[Please read this for the full details](licgen-readme).

### Q: License Generator is detected as a virus?

A: This should be a false positive. While I'm not disclosing the source for obvious reasons, I can be transparent about
what it does:

The license generator:

1. checks with Patreon if you're eligible,
2. takes notes of the system it's running on for the license data,
3. generates the license and encrypts it

A combination of the unsigned executable, network communication, system profiling and encryption may trigger some
anti-virus software.

### Q: The scripts claim they're not activated?

A: Make sure to have run the [License Generator](licgen-readme), which you obtain through Patreon, and be logged into
Patreon when the browser opens to authorize the license generator to check if you can use it.

The license generator indicates if it was successful or if anything failed.

### Q: Can I try the scripts before getting a Patreon subscription?

A: At the time of writing, no. An upcoming Manual Transmission update will include a demo mode to test things if you've
not had experience with it pre-3095.

## Compatibility

### Q: Do the latest versions of your scripts on Patreon work with the latest game update?

A: As of writing, yes. The latest tested game update is **1.0.3411.0**.

### Q: Why does steering not work in Manual Transmission? / Why does script X behave weirdly?

A: The [old version from GTA5-Mods.com](https://www.gta5-mods.com/scripts/manual-transmission-ikt){:target="_blank"}
(5.6.1) is **not** compatible with game versions 1.0.3095.0 and newer.

Symptoms are:

* Broken steering
* Broken shifting and reversing

You can downgrade the game to 1.0.3028.0 and older to continue playing with Manual Transmission v5.6.1, or you
can use the versions from [Patreon](https://www.patreon.com/ikt){:target="_blank"} after subscribing.

The following other scripts don't work either for game version 1.0.3095.0 and newer, and have been updated on Patreon:

* Custom Gear Ratios
* TurboFix
* Custom Torque Map

For completeness:

The following mod versions **are compatible** for game version **1.0.3095.0**
and at time of writing also support **1.0.3411.0**:

* Manual Transmission **5.6.2 and newer**
* Custom Gear Ratios **1.2.1 and newer**
* TurboFix **2.4.0 and newer**
* Custom Torque Map **1.1.0 and newer**

These new versions are exclusive to [Patreon](https://www.patreon.com/ikt){:target="_blank"}.

### Q: Does Manual Transmission work with my wheel?

A: Steering wheel support works for *any* wheel that supports DirectInput! Any *device* that supports DirectInput
can be mapped as any input. My personal setup:

* Fanatec CSL DD
* Fanatec CSL LC Pedals (separately connected)
* [SHH Shifter](https://www.shiftershh.com/en/){:target="_blank"}
* A random AliExpress handbrake

And it all works together flawlessly!

Ensure your wheel drivers are installed and up-to-date, and that no other application can take force feedback priority
from GTA V with the script running.

### Q: Why doesn't Manual Transmission see my wheel?

A: Please check [the Manual Transmission readme](5-gears-readme#steering-wheel-issues). Possible causes:

* No inputs mapped yet: You need to assign the inputs, the script does **not come with defaults**.
  A more user-friendly initial setup is planned for a future update.
* Drivers: Make sure your wheel drivers are installed and your wheel is picked up by games.
* Driver changes: Sometimes driver updates may re-assign GUIDs and the script doesn't recognize the wheel anymore.
  This will be addressed in a future update.
* Software conflicts: Some software may take priority over the wheel instead of GTA V. Make sure nothing like XInput
  or Steam controller also has the wheel assigned.

### Q: Are the scripts compatible with FiveM?

Sort of:

* The scripts are made with only single-player story in mind
* Only scripts marked as FiveM-compatible through `FX_ASI_BUILD` resources will work in FiveM
  * Manual Transmission
  * Custom Torque Map
  * TurboFix and Custom Gear Ratios will have this added somewhere in the future, but currently won't work with FiveM
* Scripts will only work on FiveM if the server allows client-side plugins
  * Most servers will not allow client-side plugins, as such scripts can give you an unfair advantage

**Usage of these scripts in combination with FiveM is at your own risk and no support is given!**
Before usage on FiveM, ensure the scripts work in vanilla single-player story mode. If scripts work in SP, but not
on FiveM, there is nothing I can do to help you.

If you're a server owner and interested in a server-side solution for drivetrain simulation, I highly recommend
[C.H.A.S.E.R](https://legacydmc.net/chaser/) by LegacyDMC.

I'm not aware of any worthwhile steering wheel support solutions for FiveM.

## Other

### Q: How do I install mods?

A: For general information on getting started with mods for GTA V, please check the
[GTA5-Mods Wiki with guides](https://github.com/5mods/tutorials/wiki){:target="_blank"} or ask around on the
[GTA5-Mods Discord server](https://discord.gg/2PR7aMzD4U).

**No support will be given for general modding** and it is expected of you to be competent with
computers and modding in general before trying my scripts.

### Q: Where are the camera options in Manual Transmission?

A: It's been split off into the (free) standalone
[Dynamic Vehicle First Person Camera](https://www.gta5-mods.com/scripts/dynamic-vehicle-first-person){:target="_blank"}
script.

## Remarks

If you have anything to add to this FAQ, please feel free to reach out via Discord. This FAQ is continously updated
as new questions come in.
