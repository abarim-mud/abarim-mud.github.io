---
layout: page
title: Concepts
---

### Classes, Leveling Up and Universal Skill Points
AbarimMUD would have 4 standard RPG classes: Warrior, Thief, Mage and Cleric.
A player would choose one of it as their primary class when creating the character.
The class would determine the player hitpoints/mana/moves/penetration(see #Combat)/etc.
Also every class would have list of skills unlocked on different levels.
However there would be also a possibility to gain other classes' skills.

It would work through Universal Skill Points(USP). A player would gain one USP every 5 levels.
Which could be traded for an other class skill or spell.

It's important to note that skills/spells would have learning dependencies on each other.
And it won't be possible to trade USP for higher tier skill/spell without acquiring the lower tier.

Also a few skill would be marked as exclusive only for specific classes(aka primary skills). 
It won't be possible to trade such skills for USP.

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