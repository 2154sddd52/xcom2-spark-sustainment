# SPARK Sustainment — v1.0.0

**War of the Chosen · INI only · no Highlander required**

Makes the SPARK a sustainable long-term investment instead of a 100-supply novelty.

---

## The problem

A SPARK costs 100 supplies, 2 Elerium Cores, 20 Alloys, 5 Crystals and 14 days. It cannot use the Infirmary. It cannot be stabilised. At 0 HP it simply dies — no bleed-out, no rescue. And when it limps home, it sits in the Proving Ground for an age while the Colonel who took the same beating is back in six days.

So nobody builds them after month two, and an entire chassis plus a DLC campaign's worth of content goes unused.

This mod doesn't make SPARKs a carry. It removes the parts that make them a bad *purchase*.

## Features

**Field repair, roughly halved**
`BaseSparkHealRate` 80 → 40. Repair charges 2 → 3, HP per charge 6 → 8. Downtime now roughly matches an Infirmary stay.

**A chassis that survives being shot at**
HP 10 → 12, Defense 15 → 20, Mobility 12 → 13, Hacking 5 → 15. All four difficulty variants patched, not just the base block — the SPARK now performs identically on Rookie through Legend.

**Plating that keeps up with the weapon tiers**
Plated: +3 HP / 1 armour → +4 HP / 2 armour. Powered: +5 HP / 2 armour → +6 HP / 3 armour.

**Weapons**
Magazine 3 → 4 across all tiers, so a three-shot Overdrive turn doesn't end on an empty click. SPARK BIT hack bonus 0/10/20 → 10/20/30. Base damage deliberately untouched — a beam SPARK RIFLE already beats a plasma rifle.

**Death detonation that actually hurts**
3–4 damage / 2 shred → 4–6 damage / 3 shred. Losing the chassis at least buys the squad a turn.

**Abilities**
Overdrive cooldown 5 → 4, follow-up aim penalty −15 → −10, Bulwark armour 1 → 2, Hunter Protocol 33% → 50%.

**And one nerf**
Sacrifice cooldown 4 → 5. It is one of the strongest buttons in the game, and a SPARK that survives using it shouldn't get to spam it. Set it back to 4 in the INI if you want pure upside.

## Installation

1. Extract the `SparkSustainment` folder into:

```
...\steamapps\common\XCOM 2\XCom2-WarOfTheChosen\XComGame\Mods\
```

(Create `Mods` yourself if it doesn't exist. The folder name must match `SparkSustainment.XComMod`.)

2. Enable **SPARK Sustainment** in the New Mod Launcher or AML. Manual users can add `ActiveMods="SparkSustainment"` under `[Engine.XComModOptions]` in `XCom2-WarOfTheChosen\XComGame\Config\DefaultModOptions.ini`.

3. Verify in-game: a SPARK should show 12 base HP, 20 Defense, 15 Hacking.

## Requirements

- XCOM 2: War of the Chosen
- Shen's Last Gift (included with WOTC; works with Integrated DLC on or off)
- No Community Highlander, no SDK, no script

## Compatibility

- Works on every WOTC build from the Tactical Legacy Pack (Oct 2018) through the current 2025 launcher-free releases. No balance patch has touched these keys since.
- Safe to add mid-campaign.
- Conflicts with other SPARK overhauls (LWOTC, Mechatronic Warfare, SPARK buffs) on a per-key basis — run one at a time.

## Files

```
SparkSustainment\
├─ SparkSustainment.XComMod
├─ ReadMe.txt
└─ Config\
   ├─ XComGameData.ini
   ├─ XComGameData_CharacterStats.ini
   ├─ XComGameData_WeaponData.ini
   ├─ XComGameData_SoldierSkills.ini
   └─ XComGameCore.ini
```

## Changelog

**v1.0.0**
- Initial release.
