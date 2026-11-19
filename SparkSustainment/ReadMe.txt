SPARK Sustainment v1.0.0
=======================

XCOM 2: War of the Chosen - INI only, no Highlander, no script.

WHAT IT DOES
------------
Repair:    BaseSparkHealRate 80 -> 40, repair charges 2 -> 3, HP per charge 6 -> 8
Chassis:   HP 10 -> 12, Defense 15 -> 20, Mobility 12 -> 13, Hacking 5 -> 15
           (all four difficulty variants patched, not just the base block)
Plating:   Plated +3HP/1arm -> +4HP/2arm, Powered +5HP/2arm -> +6HP/3arm
Weapons:   Magazine 3 -> 4, BIT hack bonus 0/10/20 -> 10/20/30,
           death detonation 3-4/2shred -> 4-6/3shred (base damage unchanged)
Abilities: Overdrive cooldown 5 -> 4, Overdrive aim penalty -15 -> -10,
           Bulwark armour 1 -> 2, Hunter Protocol 33% -> 50%,
           Sacrifice cooldown 4 -> 5 (nerf)

INSTALL
-------
Copy this folder into:
  ...\steamapps\common\XCOM 2\XCom2-WarOfTheChosen\XComGame\Mods\

Then enable "SPARK Sustainment" in the New Mod Launcher or AML.
No launcher? Add this under [Engine.XComModOptions] in
XCom2-WarOfTheChosen\XComGame\Config\DefaultModOptions.ini:

  ActiveMods="SparkSustainment"

REQUIRES
--------
War of the Chosen + Shen's Last Gift (works with Integrated DLC on or off).

TUNING
------
Every value is in Config\*.ini with the vanilla number in a comment above it.
Change a number, restart the game. Delete a file to revert that whole category.

NOTES
-----
Do not run alongside another SPARK overhaul - these are scalar overrides,
so the last mod loaded wins per key and there is no merge.
