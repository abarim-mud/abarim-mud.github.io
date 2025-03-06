---
layout: page
title: Player's Guide
---

## Overview

This guide is aimed towards the experienced MUD players in order to help them get familiar with AbarimMUD.

## Classes, Leveling Up and Skill Points
AbarimMUD has 4 standard RPG classes: Warrior, Rogue, Mage and Cleric.
A player chooses one of it as their primary class when creating the character.
The class and level would determine the player hitpoints/mana/moves/etc.
Also there are abilities that are exclusive only for specific classes (aka primary abilities).

## Starting Up

AbarimMUD is 6-direction MUD(north, south, east, west, up, down).

Check the [cartography](/cartography.html) section.
You'll start in the Northern Midgaard in the room "Temple Altar" (#19087).

You could always return to that room using command `recall`, which costs 35 mana.

Very important command is `score`. It shows the info about your character.

## Combat

AbarimMUD is hack'n'slash game: you kill stuff for the experience and watch the numbers grow.

So in order to start this activity go to area 'Haon Dor'(s, 8w). All mobiles aren't aggressive there. Hence it's safe to walk around.

You could evaluate a potential fight with mobile using command `consider _mobileName`. If it seems ok, then you might initiate a fight.

You could it multiple ways. The most obvious way is through command `kill monster`.
However if you're playing a rogue, then it makes sense to start the fight with backstab (`ba monster`).

There's very useful utility command `fightskill`. It allows you to specify attack action that will be done every fight round.
I.e. if you do `fightskill kick`, then you'll kick an enemy every round.
You could turn it off using command `fightskill off`

If you're playing a rogue, then there's another useful command `stabweapon`. It allows you to assign a stab weapon that 
you'll automatically switch to when doing the backstab.
Rogues start wielding an iron dagger and having an iron sword in inventory.
So if you do `remove dagger`, `wield sword` and `stabweapon dagger`. 
Then you'll wield the iron sword. And when you do the stab, the game will automatically switch to the dagger 
when doing the backstab and switch back to the sword after.

## Replenishment

Your hps/mana/mvs will replenish over time. However there is a way to significally speed that up. The way is using potions.

Every new character receives 5 replenishment potions for every of 3 stats(hps, mana and moves).
In order to use it execute `quaff healing` or `quaff mana`. It'll boost the regen of the corresponding stat for one minute.

Such potions are random pop from any types of mobiles. Also it's possible to purchase more of such potions in the Alchemist store.
Finally it's possible to exchange potions of different types there.

## Level Ups and Skills

There are many skills. Each skill can have 5 levels of the advancement: Novice, Apprentice, Adept, Expert, Master.
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
