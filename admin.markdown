---
layout: page
title: Admin's Guide
---

## Overview

Every character can have one of the following roles:
* Player
* Builder
* Administrator
* Owner

### Player
Default role.

### Builder
Builder can edit the game content(areas, mobiles, items, etc) and do basic in-game moderation(kick, ban, mute).

### Administrator
Administrator can do everything Builder can do. Also promote Players to Builders. And wipe problematic players.

### Owner
The game can have only one Owner.

## Json

All of the game data is stored in json: [Data](https://github.com/abarim-mud/AbarimMUD/tree/master/Data)

Hence it's possible to edit the game data using any text editor. Though the server restart is required if the data was edited such way.

## Common Builder Commands

### Commands not related to the building

Name|Description|Example
----|-----------|-------
areas|show list of areas|
force _creature_ _action_|force a creature to do action|force citizen say hi
goto _roomId_|move to room|goto 10
peace|stops the fight in the current room|
respawnarea|respawn the current area|
restore _creature_|fully restores the creature|restore citizen
slain _creature_|slains the creature and awards the experience|slain citizen

### Commands related to the building

Almost all types of the game content could be edited using following commands:
* create
* set
* spawn

### Command Usage

Executing every such command - with fever arguments than required - would reveal its usage.

I.e. executing `set` would result in

`Usage: set item|character|mobile|area|room [_id_] _propertyName_ _params_`

Now executing `set mobile` would result in

`Usage: set mobile _id_ id|keywords|short|long|description|level|flags _params_`

Finally executing `set item citizen flags` would result in

`Usage: set mobile _id_ flags sentinel|nowander|bash|berserk|dodge|kick|parry`

And only executing `set item citizen flags sentinel bash kick` would actually change that mobile flags.

### Id

`_id_` is not required when editing a room or an area. As in that case the room/area is edited where the Builder is located.

### Areas & Rooms

Following command creates a new area: `create area _id_` (i.e. `create area myArea`)

It would create an area with id `_id_` with single room and transfer the Builder there.

Then `set area` could be used to set the various area properties (i.e. `set area name My Area`).

`create room` creates a new room within the area - the Builder is located - and transfers the Builder there.

Then `set room` could be used to set the various room properties (i.e. `set room name Horizontal Street`).

`roomlink` would create a two-way connection between the room - the Builder is located - and specified one.

Example usage: `roomlink east 5`

### Mobiles

Following command create a new mobile: `create mobile _id_` (i.e. `create mobile citizen`)

Then `set mobile _id_` could be used to set the various mobile properties (i.e. `set mobile citizen keywords citizen male`)
