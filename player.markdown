---
layout: page
title: Player's Guide
---

## Creating Account and Character

## Starting Up: Movement, Recall, First Command

AbarimMUD is 6-direction MUD(north, south, east, west, up, down).

Check the [cartography](/cartography.html) section.
You'll start in the Northern Midgaard in the room "The Temple Of Midgaard" (#3001).

You could always return to that room using command `recall`, which costs 35 mana.

It makes sense to do `fightskill kick` right after entering the game.
It'll make the character automatically kick enemies every round during a fight.
You could turn it off using command `fightskill off`

Very important command is `score`. It shows the info about your character.

## Combat

AbarimMUD is hack'n'slash game: you kill stuff for the experience and watch the numbers grow.

So in order to start this activity go `4n, e`(area `Newbie Zone`) and initiate a fight with a newbie monster.

You could it multiple ways. The most obvious way is through command `kill monster`.
However if you're playing a Rogue, then it makes sense to start the fight with backstab (`ba monster`).

Another important command is `consider`. It compares your power vs target's power and measures who'll win in a fight.

## Replenishment

Your hps/mana/mvs will replenish over time. However there is a way to significally speed that up. The way is using potions.

Every new character receives 5 replenishment potions for every of 3 stats(hps, mana and moves).
In order to use it execute `quaff healing` or `quaff mana`. It'll boost the regen of the corresponding stat for one minute.

It's possible to purchase more of such potions in the Alchemist store.

