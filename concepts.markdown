---
layout: page
title: Concepts
---

## Classes, Leveling Up and Skill Points
AbarimMUD has 4 standard RPG classes: Warrior, Rogue, Mage and Cleric.
A player chooses one of it as their primary class when creating the character.
The class and level would determine the player hitpoints/mana/moves/etc.
Also there are abilities that are exclusive only for specific classes (aka primary abilities).

## Combat
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

## Skills
There are 10 skills. Each skill can have 5 levels of the advancement: Novice, Apprentice, Adept, Expert, Master.
Gaining/advancing skills grants various parameters and abilities.

Every level a player receives 1 skill point. Also additional skill point every 10th level.
Advancing different skills cost different amount of skill points. 
I.e. advancing Melee skill to the second level costs 2 skill points.
While Lockpicking skill costs 1 skill point.

Eventually it should be possible to max out all skills.

Every skill belongs to the specified class. I.e. Melee skill belongs to Warrior. While Sneak belongs to Rogue.
Advancing a skill occurs by the guildmaster of the corresponding class.

As it was said above advancing a skill costs skill points.
Also it costs gold.
The amount of gold is determined by the total of amount of the skills levels gained already.
The bigger the amount - the bigger the cost.

There's level constraints on the skills' advancement: you can't advance a skill to Apprentice/Adept/Expert/Master 
unless you reached levels 5/10/15/20 if the skill belongs to your class, or unless you reached levels 10/20/30/40 if the skill doesn't.

### Warrior Skills
#### Melee
Melee is the skill to handle weapons. Training it requires hard work and discipline. Thus the advancement of the skill grants some natural armor.

Skill Advancement Cost: 2

Level|Gains
-----|-----
Novice|+2 Armor Class. +20 Weapon Penetration. +1 Weapon Attack Per Round. 'Kick' ability
Apprentice|+2 Armor Class. +20 Weapon Penetration
Adept|+2 Armor Class. +20 Weapon Penetration
Expert|+2 Armor Class. +20 Weapon Penetration. +1 Weapon Attack Per Round. Prime warriors gain ability 'Parry'
Master|+2 Armor Class. +20 Weapon Penetration. Prime warriors gain ability 'Riposte'

#### Smithing
Smithing is the skill to craft/improve equipment.

Skill Advancement Cost: 1

Level|Gains
-----|-----
Novice|Iron and leather
Apprentice|Steel and 
Adept|Dwarven steel and moonstone
Expert|Ebony and draconic
Master|Adamantine and mithril

### Rogue Skills

#### Sneaking
Sneaking is the skill to silently move through shadows and backstab enemies.

Skill Advancement Cost: 2

Level|Gains
-----|-----
Novice|Grants Backstab and Sneak abilities. Initial Backstab Multiplier is 2(3 for prime thieves)
Apprentice|+2 Backstab Multiplier
Adept|+2 Backstab Multiplier. Grants 2nd stab. Prime thieves gain ability 'Circlestab'
Expert|+2 Backstab Multiplier
Master|+2 Backstab Multiplier

#### Speech
Speech is the skill to haggle with greedy traders and to unlock better goods and services.
Also the skill grants Warcry ability, which inspires yourself and allies in the battle.

Skill Advancement Cost: 2

Level|Gains
-----|-----
Novice|+10% better prices. Unlocks tier-1 goods/services. Grants Warcry ability that gives +1 damage/+10 Penetration for 1 minute
Apprentice|+10% better prices. Warcry +1 damage/+10 Penetration
Adept|+10% better prices. Unlocks tier-2 goods/services. Warcry +1 damage/+10 Penetration
Expert|+10% better prices. Warcry +1 damage/+10 Penetration
Master|+10% better prices. Unlocks tier-3 goods/services. Warcry +1 damage/+10 Penetration

#### Lockpicking
Lockpicking is the skill to pick locks(capt. obvious) and disarm traps.

Skill Advancement Cost: 1

Level|Gains
-----|-----
Novice|Allows to deal with Novice locks(1 lockpick)
Apprentice|Allows to deal with Apprentice locks(3 lockpicks)
Adept|Allows to deal with Adept locks(5 lockpicks)
Expert|Allows to deal with Expert locks(7 lockpicks)
Master|Allows to deal with Master locks(10 lockpicks)

### Cleric Skills

#### Restoration
Restoration is the school of magic that provides healing spells and spells to fight with undead.

Skill Advancement Cost: 2

Level|Gains
-----|-----
Novice|Spell 'cure light wounds'
Apprentice|Spells 'cure serious wounds', 'holy wrath'
Adept|Spells 'heal', 'divine shield'(prime Cleric only)
Expert|Spell 'greater heal'
Master|Spell 'restoration'

#### Alchemy
Alchemy is the skill to craft potions.

Skill Advancement Cost: 1

Level|Gains
-----|-----
Novice|Tier-1 potions
Apprentice|Tier-2 potions
Adept|Tier-3 potions
Expert|Tier-4 potions
Master|Tier-5 potions

### Mage Skills

#### Destruction
Restoration is the school of magic that provides spells inflicting the elemtal damage

Skill Advancement Cost: 2

Level|Gains
-----|-----
Novice|
Apprentice|
Adept|
Expert|
Master|

#### Alteration
Alteration is the school of magic that provides spells improving various parameters

Skill Advancement Cost: 2

Level|Gains
-----|-----
Novice|
Apprentice|
Adept|
Expert|
Master|

#### Enhancement
Enhancement is the skill to magically enhance equipment with various powers.

Skill Advancement Cost: 1

Level|Gains
-----|-----
Novice|Tier-1 enhancements
Apprentice|Tier-2 enhancements
Adept|Tier-3 enhancements
Expert|Tier-4 enhancements
Master|Tier-5 enhancements
