---
layout: page
title: Concepts
permalink: /concepts/
order: 2
---

## Multiclassing, Leveling Up, etc

AbarimMUD would have 4 standard RPG classes: Warrior, Thief, Mage and Cleric.
A player would choose one of it as their primary class when creating the character.
However they would be able to level all four. It would happen following way:

Once the player accumulates enough xp, their Character Level would be increased.
And they would be granted additional hp/mana/mv and 1 level point.
They could spend that point at any of four class guilds to gain Class Level.
Gaining Class Level would also cost gold, which amount would depend on their current Character Level.
Raising Class Level would unlock new abilities.
It's also worth to note that the player base Accuracy(see #Combat) would depend solely on the value of the primary Class Level.

## Combat

AbarimMUD combat system is losely based on the Advanced DnD.
Every attack is defined by following attributes: MinimumDamage, MaximumDamage, Accuracy, Victim's ArmorClass.
Firstly the RawDamage is rolled as random number from MinimumDamage to MaximumDamage.
Then ArmorAbsorptionFactor is calculated using following formula:

`ArmorAbsorptionFactor = (100 + ArmorClass - Accuracy) / 200`

It is clamped within period [0; 1] afterwards.

Finally the Damage is calculated:

`Damage = RawDamage * (1 - ArmorAbsorptionFactor)`

I.e. if both Accuracy and ArmorClass are zeroes, which are minimum possible values.
Then ArmorAbsorptionFactor would be 0.5, or only half of the damage will be applied to the victim.
Which corresponds to the ADnD behavior, where if someone with minimum possible THAC0(20) attacks someone without any armor(AC=10),
then only about half of hits would hit.