---
layout: page
title: Combat
---

Every attack is defined by following attributes: `MinimumDamage`, `MaximumDamage`, `AttackBonus`, victim's `ArmorClass`.

Also every attacks consists of two stages: determining whether there was hit or miss and - if there was a hit - calculating actual damage.

First stage is consists of following steps:
1. Rolling 1d200. Result is named `AttackDice`. If `AttackDice` is less or equal then 10, then it's a miss. 
   If it is bigger or equal then 190, then it's hit.
2. If `AttackDice` is bigger then 10 and less than 190, then `AttackRoll` is calculated following way:
   `AttackRoll = AttackDice + AttackBonus - 100`
3. If `AttackRoll` is bigger or equal to the victim's `ArmorClass`, then it's a hit. Otherwise it's a miss.

Now if there was a hit then the damage is calculated, which is just random number from `MinimumDamage` to `MaximumDamage`.

I.e. if both `AttackBonus` and `ArmorClass` are zeroes, which are minimum possible values.
Then there would be 50% probability of hit.