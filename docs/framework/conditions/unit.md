# UNIT
---


> ## is

#### Parameters
- `UNIT1`: The first unit to compare.
- `UNIT2`: The second unit to compare.
#### Returns `BOOL`
- `true` if the two units are the same, `false` otherwise.


#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT1.is(UNIT2)", UNIT1},

-- in Lua code
_A.DSL:Get("is")("UNIT1", "UNIT2")

-- Lua Mode
UNIT1:Is(UNIT2)
```
***


> ## ingroup

#### Parameters
- `UNIT`: The unit to check for group membership.
#### Returns `BOOL`
- `true` if the specified unit is in the player's party or raid group, `false` otherwise.


#### *Examples:*
```lua
-- DSL Mode
{ACTION, "ingroup", UNIT},

-- in Lua code
_A.DSL:Get("ingroup")("UNIT")

-- Lua Mode
UNIT:Ingroup()
```

***


> ## incdmg

#### Parameters
- `UNIT`: The unit to calculate incoming damage for.
- `seconds`: The time frame in seconds to calculate incoming damage for (default is 3 seconds).

#### Returns `NUMBER`
 - The total damage taken by the unit in the specified time frame, or 0 if the target doesn't exist.


#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.incdmg(3) > 10000", UNIT},

-- in Lua code
_A.DSL:Get("incdmg")("UNIT", "3") > 10000

-- Lua Mode
UNIT:Incdmg(3) > 10000
```

***


> ## incdmg.phys

#### Parameters
- `UNIT`: The unit for which to calculate incoming physical damage.
- `seconds`: The time frame in seconds to calculate incoming physical damage for (default is 3 seconds).

#### Returns `NUMBER`
 - The total damage taken by the unit in the specified time frame, or 0 if the target doesn't exist.


#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.incdmg.phys(3) > 10000", UNIT},

-- in Lua code
_A.DSL:Get("incdmg.phys")("UNIT", "3") > 10000

-- Lua Mode
UNIT:IncdmgPhys(3) > 10000
```

***


> ## incdmg.magic

#### Parameters
- `UNIT`: The unit for which to calculate incoming magic damage.
- `seconds`: The time frame in seconds to calculate incoming magic damage for (default is 3 seconds).

#### Returns `NUMBER`
 - The total damage taken by the unit in the specified time frame, or 0 if the target doesn't exist.


#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.incdmg.magic(3) > 10000", UNIT},

-- in Lua code
_A.DSL:Get("incdmg.magic")("UNIT", "3") > 10000

-- Lua Mode
UNIT:IncdmgMagic(3) > 10000
```

***


> ## boss

#### Parameters
- `UNIT`: The unit to check for boss status.
#### Returns `BOOL`
- `true` if the unit is a boss, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.boss", UNIT},

-- in Lua code
_A.DSL:Get("boss")("UNIT")

-- Lua Mode
UNIT:Boss()
```

***


> ## elite

#### Parameters
- `UNIT`: The unit to check for elite classification.
#### Returns `BOOL`
- `true` if the unit has an elite classification, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.elite", UNIT},

-- in Lua code
_A.DSL:Get("elite")("UNIT")

-- Lua Mode
UNIT:Elite()
```

***


> ## classification

#### Parameters
- `UNIT`: The unit to check for classification.
- `classif`: The classification string to compare with.

    | **`classif`** |
    | - |
    | worldboss     |
    | rareelite     |
    | elite         |
    | rare          |
    | normal        |
    | trivial       |
    | minus         |

#### Returns `BOOL`
- `true` if the unit's classification matches the given classif, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.classification(rare)", UNIT},

-- in Lua code
_A.DSL:Get("classification")("UNIT", "rare")

-- Lua Mode
UNIT:Classification("rare")
```

***


> ## id

#### Parameters
- `UNIT`: The unit to check for the expected ID.
- `id`: The expected ID to compare against.
#### Returns `BOOL`
- `true` if the unit's ID matches the expected ID, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.id(1589)", UNIT},

-- in Lua code
_A.DSL:Get("id")("UNIT", "1589")

-- Lua Mode
UNIT:Id(1589)
```

***


> ## threat

#### Parameters
- `UNIT`: The unit to check for threat percentage towards the player.
#### Returns `NUMBER`
- The unit's threat percentage against the player. At 100% the player will become the primary target.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.threat >= 80", UNIT},

-- in Lua code
_A.DSL:Get("threat")("UNIT") >= 80

-- Lua Mode
UNIT:Threat() >= 80
```

***


> ## aggro

#### Parameters
- `UNIT`: The unit to check for aggro on the player.
#### Returns `BOOL`
- `true` if the target has aggro on the player, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.aggro", UNIT},

-- in Lua code
_A.DSL:Get("aggro")("UNIT")

-- Lua Mode
UNIT:Aggro()
```

***


> ## moving

#### Parameters
- `UNIT`: The unit to check if is currently moving
#### Returns `BOOL`
- `true` if the unit is moving, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.moving", UNIT},

-- in Lua code
_A.DSL:Get("moving")("UNIT")

-- Lua Mode
UNIT:Moving()
```

***


> ## target

#### Parameters
- `UNIT1`: The unit whose target will be checked.
- `UNIT2`: The unit to compare the target against.
#### Returns `BOOL`
- `true` if the target of the specified unit1 matches the given unit2, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT1.target(UNIT2)", UNIT1},

-- in Lua code
_A.DSL:Get("target")("UNIT1", "UNIT2")

-- Lua Mode
UNIT1:Target(UNIT2)
```

***


> ## isplayer
  *`isplayer || player`*

#### Parameters
- `UNIT`: The unit to be checked.
#### Returns `BOOL`
- `true` if the unit is a player-controlled unit, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.isplayer", UNIT},

-- in Lua code
_A.DSL:Get("isplayer")("UNIT")

-- Lua Mode
UNIT:Isplayer()
```

***


> ## inphase

#### Parameters
- `UNIT`: The unit to be checked for being in the same phase.
#### Returns `BOOL`
- `true` if the unit is in the same phase as the player, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.inphase", UNIT},

-- in Lua code
_A.DSL:Get("inphase")("UNIT")

-- Lua Mode
UNIT:Inphase()
```

***


> ## exists

#### Parameters
- `UNIT`: The unit to be checked for existence.
#### Returns `BOOL`
- `true` if the unit exists, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.exists", UNIT},

-- in Lua code
_A.DSL:Get("exists")("UNIT")

-- Lua Mode
UNIT:Exists()
```

***


> ## guid

#### Parameters
- `UNIT`: The unit for which to retrieve the GUID.
#### Returns `STRING`
- The GUID of the target, or nil if the target is not valid.

#### *Examples:*
```lua
-- DSL Mode
N/A

-- in Lua code
_A.DSL:Get("guid")("UNIT")

-- Lua Mode
UNIT.guid
or
UNIT:Guid()
```

***


> ## visible

#### Parameters
- `UNIT`: The unit to check for visibility.
#### Returns `BOOL`
- `true` if the unit is visible, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.visible", UNIT},

-- in Lua code
_A.DSL:Get("visible")("UNIT")

-- Lua Mode
UNIT:Visible()
```

***


> ## dead

#### Parameters
- `UNIT`: The unit to check for death or ghost state.
#### Returns `BOOL`
- `true` if the unit is dead or a ghost, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.dead", UNIT},

-- in Lua code
_A.DSL:Get("dead")("UNIT")

-- Lua Mode
UNIT:Dead()
```

***


> ## alive

#### Parameters
- `UNIT`: The unit to check for being alive.
#### Returns `BOOL`
- `true` if the unit is alive, `false` if it is dead or a ghost.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.alive", UNIT},

-- in Lua code
_A.DSL:Get("alive")("UNIT")

-- Lua Mode
UNIT:Alive()
```

***


> ## infront

#### Parameters
- `UNIT`: The unit to check if the player is facing.
#### Returns `BOOL`
- `true` if the player is facing the unit, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.infront", UNIT},

-- in Lua code
_A.DSL:Get("infront")("UNIT")

-- Lua Mode
UNIT:Infront()
```

***


> ## infrontof

#### Parameters
- `UNIT1`: The unit that is checked to be in front.
- `UNIT2`: The unit to check if it is facing UNIT.
#### Returns `BOOL`
- `true` if unit2 is facing unit1, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT1.infrontof(UNIT2)", UNIT1},

-- in Lua code
_A.DSL:Get("infrontof")("UNIT1", "UNIT2")

-- Lua Mode
UNIT1:Infrontof(UNIT2)
```

***


> ## behind

#### Parameters
- `UNIT`: The unit to check if the player is behind.
#### Returns `BOOL`
- `true` if player is behind the unit, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.behind", UNIT},

-- in Lua code
_A.DSL:Get("behind")("UNIT")

-- Lua Mode
UNIT:Behind()
```

***


> ## behindof

#### Parameters
- `UNIT1`: The unit to check if it is behind unit2.
- `UNIT2`: The reference unit.
#### Returns `BOOL`
- `true` if unit1 is behind unit2, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT1.behindof(UNIT2)", UNIT1},

-- in Lua code
_A.DSL:Get("behindof")("UNIT1", "UNIT2")

-- Lua Mode
UNIT1:Behindof(UNIT2)
```

***


> ## inConeOf

#### Parameters
- `UNIT1`: The unit to check if it is within the cone.
- `UNIT2_ANGLE`: The reference unit and the cone angle (optional, default angle is 180 degrees). Provide as a string in the format "unit2, angle".
#### Returns `BOOL`
- `true` if unit1 is within the specified cone angle in front of unit2, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT1.inConeOf(UNIT2, 120)", UNIT},

-- in Lua code
_A.DSL:Get("inConeOf")("UNIT1", "UNIT2, 120")

-- Lua Mode
UNIT1:InConeOf(UNIT2, 120)
```

***


> ## lastmoved

#### Parameters
- `UNIT`: The unit to check for movement.
#### Returns `NUMBER`
- The `time in seconds` since the unit was last moved, or `0` if the unit is not valid or has not moved.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.lastmoved", UNIT},

-- in Lua code
_A.DSL:Get("lastmoved")("UNIT")

-- Lua Mode
UNIT:Lastmoved()
```

***


> ## movingfor

#### Parameters
- `UNIT`: The unit to check for movement.
#### Returns `NUMBER`
- The `time in seconds` that the unit has been continuously moving, or `0` if the unit is not valid or is not moving.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.movingfor", UNIT},

-- in Lua code
_A.DSL:Get("movingfor")("UNIT")

-- Lua Mode
UNIT:Movingfor()
```

***


> ## pvp

#### Parameters
- `UNIT`: The unit to check for PvP flag with the player.
#### Returns `BOOL`
- `true` if the unit is flagged for PvP, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.pvp", UNIT},

-- in Lua code
_A.DSL:Get("pvp")("UNIT")

-- Lua Mode
UNIT:Pvp()
```

***


> ## friend

#### Parameters
- `UNIT`: The unit to check for friendly status.
#### Returns `BOOL`
- `true` if the unit is friendly, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.friend", UNIT},

-- in Lua code
_A.DSL:Get("friend")("UNIT")

-- Lua Mode
UNIT:Friend()
```

***


> ## canassist

#### Parameters
- `UNIT`: The unit to check for assist eligibility.
#### Returns `BOOL`
- `true` if the player can assist the unit, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.canassist", UNIT},

-- in Lua code
_A.DSL:Get("canassist")("UNIT")

-- Lua Mode
UNIT:Canassist()
```

***


> ## enemy
  *`enemy || canattack`*

#### Parameters
- `UNIT`: The unit to check for enemy status or attack eligibility.
#### Returns `BOOL`
- `true` if the unit is an enemy, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.enemy", UNIT},

-- in Lua code
_A.DSL:Get("enemy")("UNIT")

-- Lua Mode
UNIT:Enemy()
```

***


> ## range

#### Parameters
- `UNIT`: The unit to measure combat range against.
#### Returns `NUMBER`
- The combat range between the player and the unit, or 999 if the range cannot be determined.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.range < 20", UNIT},

-- in Lua code
_A.DSL:Get("range")("UNIT") < 20

-- Lua Mode
UNIT:Range() < 20
```

***


> ## rangefrom

#### Parameters
- `UNIT1`: The first unit to measure combat range from.
- `UNIT2`: The second unit to measure combat range to.
#### Returns `NUMBER`
- The combat range between the two units, or 999 if the range cannot be determined.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT1.rangefrom(UNIT2) < 20", UNIT},

-- in Lua code
_A.DSL:Get("rangefrom")("UNIT1", "UNIT2") < 20

-- Lua Mode
UNIT1:Rangefrom(UNIT2) < 20
```

***


> ## distance

#### Parameters
- `UNIT`: The unit to measure distance against.
#### Returns `NUMBER`
- The distance between the player and the unit, or 999 if the distance cannot be determined.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.distance < 20", UNIT},

-- in Lua code
_A.DSL:Get("distance")("UNIT") < 20

-- Lua Mode
UNIT:Distance() < 20
```

***


> ## distancefrom

#### Parameters
- `UNIT1`: The first unit to measure distance from.
- `UNIT2`: The second unit to measure distance to.
#### Returns `NUMBER`
- The distance between the two units, or 999 if the range cannot be determined.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT1.distancefrom(UNIT2) < 20", UNIT},

-- in Lua code
_A.DSL:Get("distancefrom")("UNIT1", "UNIT2") < 20

-- Lua Mode
UNIT1:Distancefrom(UNIT2) < 20
```

***


> ## level

#### Parameters
- `UNIT`: The unit whose level to retrieve.
#### Returns `NUMBER`
- The level of the unit, or `-1` if the level cannot be determined.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.level >= 45", UNIT},

-- in Lua code
_A.DSL:Get("level")("UNIT") >= 45

-- Lua Mode
UNIT:Level() >= 45
```

***


> ## combat

#### Parameters
- `UNIT`: The unit to check for combat status.
#### Returns `BOOL`
- `true` if the unit is in combat, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.combat", UNIT},

-- in Lua code
_A.DSL:Get("combat")("UNIT")

-- Lua Mode
UNIT:Combat()
```

***


> ## role

#### Parameters
- `UNIT`: The unit whose role to retrieve.
#### Returns `STRING`
- The role assigned to the target unit: `"TANK", "HEALER", "DAMAGER", or "UNKNOWN"` if the role cannot be determined.

#### *Examples:*
```lua
-- DSL Mode
N/A

-- in Lua code
_A.DSL:Get("role")("UNIT") == "HEALER"

-- Lua Mode
UNIT.role == "HEALER"
or
UNIT:Role() == "HEALER"
```

***


> ## hasrole

#### Parameters
- `UNIT`: The unit to check for the role.
- `expectedRole` The expected role to search for within the unit's role.

    `"TANK", "HEALER", "DAMAGER", or "UNKNOWN"`
#### Returns `BOOL`
- `true` if the unit has a role containing the expected name, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.hasrole(TANK)", UNIT},

-- in Lua code
_A.DSL:Get("hasrole")("UNIT", "TANK")

-- Lua Mode
UNIT:Hasrole("TANK")
```

***


> ## name

#### Parameters
- `UNIT`: The unit whose name to retrieve.
#### Returns `STRING`
- The name of the unit, or `Unknown` if the name cannot be determined.

#### *Examples:*
```lua
-- DSL Mode
N/A

-- in Lua code
_A.DSL:Get("name")("UNIT") == "Gul'dan"

-- Lua Mode
UNIT.name == "Gul'dan"
or
UNIT:Name() == "Gul'dan"
```

***


> ## hasname

#### Parameters
- `UNIT`: The unit to check for the name.
- `expectedName` The expected name to search for within the unit's name.
#### Returns `BOOL`
- `true` if the unit has a name containing the expected name, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.hasname(Gul'dan)", UNIT},

-- in Lua code
_A.DSL:Get("hasname")("UNIT", "Gul'dan")

-- Lua Mode
UNIT:Hasname("Gul'dan")
```

***


> ## creature.type

#### Parameters
- `UNIT`: The unit whose creature type to retrieve.
#### Returns `STRING`
- The *`localized`* creature type of the unit, or `nil` if the creature type cannot be determined.

    - enUS
    `"Aberration"`, `"Beast"`, `"Critter"`, `"Demon"`, `"Dragonkin"`, `"Elemental"`, `"Gas Cloud"`, `"Giant"`, `"Humanoid"`, `"Mechanical"`,
     `"Non-combat Pet"`, `"Not specified"`, `"Totem"`, `"Undead"`, `"Wild Pet"`



#### *Examples:*
```lua
-- DSL Mode
N/A

-- in Lua code
_A.DSL:Get("creature.type")("UNIT") ~= "Undead"

-- Lua Mode
UNIT:CreatureType() ~= "Undead"
```

***


> ## hascreature.type

#### Parameters
- `UNIT`: The unit to check for the creature type.
- `expectedType` The *`localized`* expected creature type to compare with.
#### Returns `BOOL`
- `true` if the unit has the expected creature type, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.hascreature.type(Humanoid)", UNIT},

-- in Lua code
_A.DSL:Get("hascreature.type")("UNIT", "Humanoid")

-- Lua Mode
UNIT:HascreatureType("Humanoid")
```

***


> ## class

#### Parameters
- `UNIT`: The unit whose class to retrieve.
#### Returns `STRING`
- The class of the unit, or `Unknown` if the name cannot be determined.

#### *Examples:*
```lua
-- DSL Mode
N/A

-- in Lua code
_A.DSL:Get("class")("UNIT") == "DEATHKNIGHT"

-- Lua Mode
UNIT:Class() == "DEATHKNIGHT"
```

***


> ## hasclass

#### Parameters
- `UNIT`: The unit to check for the class.
- `expectedClass` The expected class name to compare with.
#### Returns `BOOL`
- `true` if the unit belongs to the expected class, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.hasclass(WARRIOR)", UNIT},

-- in Lua code
_A.DSL:Get("hasclass")("UNIT", "WARRIOR")

-- Lua Mode
UNIT:Hasclass("WARRIOR")
```

***


> ## inmelee

#### Parameters
- `UNIT`: The unit to check for melee range.
#### Returns `BOOL`
- `true` if the target unit is within melee range, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.inmelee", UNIT},

-- in Lua code
_A.DSL:Get("inmelee")("UNIT")

-- Lua Mode
UNIT:Inmelee()
```

***


> ## inranged

#### Parameters
- `UNIT`: The unit to check for ranged combat range.
#### Returns `BOOL`
- `true` if the unit is within the ranged combat range of 40, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.inranged", UNIT},

-- in Lua code
_A.DSL:Get("inranged")("UNIT")

-- Lua Mode
UNIT:Inranged()
```

***


> ## timetodie
  *`timetodie || deathin || ttd`*

#### Parameters
- `UNIT`: The unit for which to estimate time to death.
#### Returns `NUMBER`
- The estimated time to death in `seconds`. Returns a high value if is a dummy.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.ttd > 8", UNIT},

-- in Lua code
_A.DSL:Get("ttd")("UNIT") > 8

-- Lua Mode
UNIT:Ttd() > 8
```

***


> ## charmed

#### Parameters
- `UNIT`: The unit to check for being charmed.
#### Returns `BOOL`
- `true` if the unit is charmed, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.charmed", UNIT},

-- in Lua code
_A.DSL:Get("charmed")("UNIT")

-- Lua Mode
UNIT:Charmed()
```

***


> ## isdummy

#### Parameters
- `UNIT`: The unit to check for being a dummy unit.
#### Returns `BOOL`
- `true` if the unit is a dummy unit, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.isdummy", UNIT},

-- in Lua code
_A.DSL:Get("isdummy")("UNIT")

-- Lua Mode
UNIT:Isdummy()
```

***


> ## haste

#### Parameters
- `UNIT`: The unit for which to retrieve the spell haste percentage.
#### Returns `NUMBER`
- The spell haste `percentage` of the specified unit.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.haste > 30", UNIT},

-- in Lua code
_A.DSL:Get("haste")("UNIT") > 30

-- Lua Mode
UNIT:Haste() > 30
```

***


> ## connected

#### Parameters
- `UNIT`: The unit to check for being connected to the game world.
#### Returns `BOOL`
- `true` if the specified unit is connected to the game world, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.connected", UNIT},

-- in Lua code
_A.DSL:Get("connected")("UNIT")

-- Lua Mode
UNIT:Connected()
```

***


> ## combat.time

#### Parameters
- `UNIT`: The unit to check for combat time duration.
#### Returns `NUMBER`
- The time duration in `seconds` for which the specified unit has been in combat.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.combat.time > 5", UNIT},

-- in Lua code
_A.DSL:Get("combat.time")("UNIT") > 5

-- Lua Mode
UNIT:CombatTime() > 5
```

***


> ## los

#### Parameters
- `UNIT`: The unit to check for line of sight.
#### Returns `BOOL`
- `true` if there is line of sight between the player character and the specified unit, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.los", UNIT},

-- in Lua code
_A.DSL:Get("los")("UNIT")

-- Lua Mode
UNIT:Los()
```

***


> ## losfrom

#### Parameters
- `UNIT1`: The first unit to check from.
- `UNIT2`: The second unit to check line of sight to.
#### Returns `BOOL`
- `true` if there is line of sight between the two specified units, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT1.losfrom(UNIT2)", UNIT1},

-- in Lua code
_A.DSL:Get("losfrom")("UNIT1", "UNIT2")

-- Lua Mode
UNIT1:Losfrom(UNIT2)
```

***


> ## hasloot

#### Parameters
- `UNIT`: The unit to check for loot availability.
#### Returns `BOOL`
- `true` if the specified unit has loot that can be looted by the player character, `false` otherwise.

#### *Examples:*
```lua
-- DSL Mode
{ACTION, "UNIT.hasloot", UNIT},

-- in Lua code
_A.DSL:Get("hasloot")("UNIT")

-- Lua Mode
UNIT:Hasloot()
```
