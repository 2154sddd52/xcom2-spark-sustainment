# SPARK Sustainment

An INI-only balance and quality-of-life mod for **XCOM 2: War of the Chosen** that rebuilds the SPARK from the maintenance bay outward.

No script. No Community Highlander. No `.upk` files. Five config files, 38 overridden values, all of them documented below so you can disagree with any of them.

---

## Why

The SPARK is the most expensive single unit in WOTC and the least forgiving to lose:

| | |
|---|---|
| Build cost | 100 supplies, 2 Elerium Cores, 20 Alloys, 5 Crystals |
| Build time | 14 days (20 on Legend) |
| Recovery | Proving Ground repair only — **no Infirmary, no Specialist heals** |
| At 0 HP | Dies outright. No bleed-out, no stabilise, no capture. |
| Progression | No PCS, no bonds, no covert ops, no AP abilities |

So it is a 100-supply, 14-day investment that cannot be healed, cannot be stabilised, and sits in the shop for a long stretch after every bad mission — while a Colonel Ranger walks off the same mission into the Infirmary and is back in six days. Players stop building SPARKs around the second month, and the whole Shen's Last Gift chassis goes unused for the rest of the campaign.

This mod does not turn the SPARK into a carry. It removes the parts of the unit that make it a bad *purchase*, and pays for some of that with a nerf.

---

## What changes

### 1. Field repair — the headline

| Value | Vanilla | Mod |
|---|---|---|
| `BaseSparkHealRate` | 80 | **40** |
| `REPAIR_CHARGES` | 2 | **3** |
| `REPAIR_HP` | 6 | **8** |

Repair time scales inversely with the heal rate, so downtime is roughly halved. Combined with a third Repair charge and more HP per charge, a SPARK can be patched in the field and put back in the roster in about the time a wounded soldier spends in the Infirmary.

### 2. Chassis

| Stat | Vanilla | Mod |
|---|---|---|
| HP | 10 (11 on Rookie) | **12 (13)** |
| Defense | 15 | **20** |
| Mobility | 12 | **13** |
| Hacking | 5 | **15** |

A SPARK has no cover and no bonds. It eats every flank shot in the open, so raw HP and Defense are the only survivability it has. Hacking 5 was cosmetic — the SPARK BIT bonus now stacks on top of a stat that does something.

> **Technical note:** WOTC ships four difficulty variants (`SparkSoldier_Diff_0..3`) that re-declare HP, Will, FlankingCritChance and Hacking *after* the base `SparkSoldier` block. Editing only the base block changes nothing on HP or Hacking. All five sections are mirrored here so the SPARK is identical on all four difficulties. `LostTowersSpark` (the story SPARK in the Shen's Last Gift mission) is untouched.

### 3. Plating that keeps up

| | Vanilla | Mod |
|---|---|---|
| Plated SPARK Armor | +3 HP / 1 armour | **+4 HP / 2 armour** |
| Powered SPARK Armor | +5 HP / 2 armour | **+6 HP / 3 armour** |

Mobility bonuses unchanged.

### 4. Weapons

| Value | Vanilla | Mod |
|---|---|---|
| SPARK RIFLE magazine (CV / MG / BM) | 3 / 3 / 3 | **4 / 4 / 4** |
| SPARK BIT hack bonus (CV / MG / BM) | 0 / 10 / 20 | **10 / 20 / 30** |
| Death detonation | 3–4 dmg, 2 shred | **4–6 dmg, 3 shred** |

**Base damage is deliberately untouched.** A beam SPARK RIFLE is already 9–10 against a plasma rifle's 8–10; damage was never the problem. The problem was that Overdrive chains die to an empty magazine, and that losing the chassis was nearly free for the aliens.

### 5. Abilities

| Value | Vanilla | Mod |
|---|---|---|
| `OVERDRIVE_COOLDOWN` | 5 | **4** |
| Overdrive follow-up aim penalty | −15 | **−10** |
| `BULWARK_ARMOR` | 1 | **2** |
| `HUNTERPROTOCOL_CHANCE` | 33 | **50** |
| `SACRIFICE_COOLDOWN` | 4 | **5** ← nerf |

Overdrive is the reason to bring a SPARK at all, and it was on a five-turn leash in a game where most fights last three. At −15 aim a three-shot Overdrive turn is usually one hit and two misses, which reads as "SPARKs can't shoot" rather than "Overdrive is a burst you have to set up."

---

## Trade-offs

`SACRIFICE_COOLDOWN` goes **4 → 5**. Sacrifice is one of the strongest buttons in the game — a free body that eats everything aimed at the squad — and the chassis buffs above make the SPARK far more likely to survive using it. Without the extra turn of cooldown it stops being a decision and becomes a rotation.

If you want the mod to be pure upside, open `Config/XComGameData_SoldierSkills.ini` and set it back to `4`.

---

## Requirements

- **XCOM 2: War of the Chosen** — required. This does nothing on the base game.
- **Shen's Last Gift** — required. Every value here lives in the `DLC_3` config layer, which is the DLC that owns the SPARK. It is included in WOTC's "Integrated DLC" option, so you do not need the separate campaign toggle, but the DLC files must be installed.
- No Community Highlander. No ModBuddy. No SDK.

## Installation

**1. Drop the folder in place.**

Extract `SparkSustainment` so that this path exists:

```
...\steamapps\common\XCOM 2\XCom2-WarOfTheChosen\XComGame\Mods\SparkSustainment\
```

The `Mods` folder (with an `s`) is not created by the game — make it yourself if it is missing. Inside `SparkSustainment` you should see `SparkSustainment.XComMod`, `Config\`, and `ReadMe.txt`. The folder name must match the `.XComMod` filename.

**2. Enable it.**

- **New Mod Launcher / Alternative Mod Launcher (AML):** the mod appears in the list as *SPARK Sustainment*. Tick it. Load order does not matter unless you run another SPARK mod.
- **Manual, no launcher:** open `...\XCom2-WarOfTheChosen\XComGame\Config\DefaultModOptions.ini` and add under the existing section:

```ini
[Engine.XComModOptions]
ActiveMods="SparkSustainment"
```

Since the 2K Launcher was retired in late 2025, Steam launches WOTC directly — the *Play War of the Chosen* and *Open New Mod Launcher* entries in the Steam launch-options dialog. Nothing else about the mod folder has changed.

**3. Check it took.**

Start a mission with a SPARK and open its info panel: base HP should read 12, Defense 20, Hacking 15.

## Compatibility

- **Game version:** War of the Chosen, any build from the Tactical Legacy Pack (October 2018) onward. Firaxis has not shipped a balance patch since; the config keys used here are unchanged in every current build, including the 2025 launcher-free releases.
- **Integrated DLC on or off:** both work. The `DLC_3` config layer loads either way.
- **Mid-campaign install:** safe. Newly built and promoted SPARKs pick up the new values immediately.
- **Mid-campaign removal:** the game will recalculate stats on the next rank-up or reload, so a SPARK may sit above vanilla values for a mission or two. Nothing breaks; finish the campaign or accept the drift.
- **Load order conflicts:** any mod that touches the same SPARK values (LWOTC, Mechatronic Warfare, other SPARK buffs) will fight over the same keys. Whichever mod loads last wins per key — there is no merge, because these are scalars. Run one SPARK overhaul at a time.

## Tuning it yourself

Every file is plain text with the vanilla value written in a comment above the line. Open `Config\*.ini`, change a number, restart the game. No rebuild step.

To disable a whole category, delete the corresponding file — the game falls back to vanilla for that config layer.

## File map

```
SparkSustainment\
├─ SparkSustainment.XComMod            mod descriptor (RequiresXPACK=true)
├─ ReadMe.txt                          short in-folder readme
└─ Config\
   ├─ XComGameData.ini                 repair rate
   ├─ XComGameData_CharacterStats.ini  chassis stats, all 5 difficulty sections
   ├─ XComGameData_WeaponData.ini      magazine, hack bonus, death detonation
   ├─ XComGameData_SoldierSkills.ini   ability tuning
   └─ XComGameCore.ini                 plating HP / armour
```

## Changelog

**1.0.0**
- Initial release.
