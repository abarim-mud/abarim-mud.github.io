---
layout: page
title: Player's Guide
permalink: /player/
order: 2
---

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