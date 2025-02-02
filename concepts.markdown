---
layout: page
title: Concepts
---

### Classes, Leveling Up and Skill Points
AbarimMUD has 4 standard RPG classes: Warrior, Thief, Mage and Cleric.
A player chooses one of it as their primary class when creating the character.
The class and level would determine the player hitpoints/mana/moves/etc.
Also there are abilities that are exclusive only for specific classes (aka primary abilities).

### Combat
AbarimMUD combat system is losely based on the Advanced DnD.
Every attack is defined by following attributes: `MinimumDamage`, `MaximumDamage`, `Penetration`, Victim's `ArmorClass`.
Firstly the `RawDamage` is rolled as random number from `MinimumDamage` to `MaximumDamage`.
Then `ArmorAbsorptionFactor` is calculated using following formula:

`ArmorAbsorptionFactor = (100 + ArmorClass - Penetration) / 200`

It is clamped within period [0; 1] afterwards.

Finally the Damage is calculated:

`Damage = RawDamage * (1 - ArmorAbsorptionFactor)`

I.e. if both `Penetration` and `ArmorClass` are zeroes, which are minimum possible values.
Then `ArmorAbsorptionFactor` would be 0.5, or only half of the damage will be applied to the victim.
Which corresponds to the ADnD behavior, where if someone with minimum possible THAC0(20) attacks someone without any armor(AC=10),
then only about half of hits would hit.

### Skills
There are many skills. Each can have 5 levels: Novice, Apprentice, Adept, Expert, Master.

Skills grant various combat/defense parameters and abilities.

#### Backstab

Level|Gains
-----|-----
Novice|Grants Backstab ability. Initial Backstab Multiplier is 2(3 for prime thieves)
Apprentice|+2 Backstab Multiplier
Adept|+2 Backstab Multiplier. Grants 2nd stab. Prime thieves also gain ability 'circlestab'
Expert|+2 Backstab Multiplier
Master|+2 Backstab Multiplier

#### Melee

Level|Gains
-----|-----
Novice|+20 Weapon Penetration. +1 Weapon Attack Per Round. 'Kick' ability
Apprentice|+20 Weapon Penetration
Adept|+20 Weapon Penetration
Expert|+20 Weapon Penetration. +1 Weapon Attack Per Round
Master|+20 Weapon Penetration. Prime warriors gain ability 'parry'

