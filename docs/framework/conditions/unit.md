# UNIT

---

> ## is

#### Parameters

-   `UNIT1`: The first unit to compare.
-   `UNIT2`: The second unit to compare.

#### Returns `BOOL`

-   `true` if the two units are the same, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT1.is(UNIT2)", UNIT1},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("is")("UNIT1", "UNIT2")
    ```

=== "Lua Mode"

    ```lua
    UNIT1:Is(UNIT2)
    ```

---

> ## ingroup

#### Parameters

-   `UNIT`: The unit to check for group membership.

#### Returns `BOOL`

-   `true` if the specified unit is in the player's party or raid group, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "ingroup", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("ingroup")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Ingroup()
    ```

---

> ## incdmg

#### Parameters

-   `UNIT`: The unit to calculate incoming damage for.
-   `seconds`: The time frame in seconds to calculate incoming damage for (default is 3 seconds).

#### Returns `NUMBER`

-   The total damage taken by the unit in the specified time frame, or 0 if the target doesn't exist.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.incdmg(3) > 10000", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("incdmg")("UNIT", "3") > 10000
    ```

=== "Lua Mode"

    ```lua
    UNIT:Incdmg(3) > 10000
    ```

---

> ## incdmg.phys

#### Parameters

-   `UNIT`: The unit for which to calculate incoming physical damage.
-   `seconds`: The time frame in seconds to calculate incoming physical damage for (default is 3 seconds).

#### Returns `NUMBER`

-   The total damage taken by the unit in the specified time frame, or 0 if the target doesn't exist.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.incdmg.phys(3) > 10000", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("incdmg.phys")("UNIT", "3") > 10000
    ```

=== "Lua Mode"

    ```lua
    UNIT:IncdmgPhys(3) > 10000
    ```

---

> ## incdmg.magic

#### Parameters

-   `UNIT`: The unit for which to calculate incoming magic damage.
-   `seconds`: The time frame in seconds to calculate incoming magic damage for (default is 3 seconds).

#### Returns `NUMBER`

-   The total damage taken by the unit in the specified time frame, or 0 if the target doesn't exist.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.incdmg.magic(3) > 10000", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("incdmg.magic")("UNIT", "3") > 10000
    ```

=== "Lua Mode"

    ```lua
    UNIT:IncdmgMagic(3) > 10000
    ```

---

> ## boss

#### Parameters

-   `UNIT`: The unit to check for boss status.

#### Returns `BOOL`

-   `true` if the unit is a boss, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.boss", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("boss")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Boss()
    ```

---

> ## elite

#### Parameters

-   `UNIT`: The unit to check for elite classification.

#### Returns `BOOL`

-   `true` if the unit has an elite classification, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.elite", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("elite")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Elite()
    ```

---

> ## classification

#### Parameters

-   `UNIT`: The unit to check for classification.
-   `classif`: The classification string to compare with.

    | **`classif`** |
    | ------------- |
    | worldboss     |
    | rareelite     |
    | elite         |
    | rare          |
    | normal        |
    | trivial       |
    | minus         |

#### Returns `BOOL`

-   `true` if the unit's classification matches the given classif, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.classification(rare)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("classification")("UNIT", "rare")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Classification("rare")
    ```

---

> ## id

#### Parameters

-   `UNIT`: The unit to check for the expected ID.
-   `id`: The expected ID to compare against.

#### Returns `BOOL`

-   `true` if the unit's ID matches the expected ID, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.id(1589)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("id")("UNIT", "1589")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Id(1589)
    ```

---

> ## threat

#### Parameters

-   `UNIT`: The unit to check for threat percentage towards the player.

#### Returns `NUMBER`

-   The unit's threat percentage against the player. At 100% the player will become the primary target.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.threat >= 80", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("threat")("UNIT") >= 80
    ```

=== "Lua Mode"

    ```lua
    UNIT:Threat() >= 80
    ```

---

> ## aggro

#### Parameters

-   `UNIT`: The unit to check for aggro on the player.

#### Returns `BOOL`

-   `true` if the target has aggro on the player, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.aggro", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("aggro")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Aggro()
    ```

---

> ## moving

#### Parameters

-   `UNIT`: The unit to check if is currently moving

#### Returns `BOOL`

-   `true` if the unit is moving, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.moving", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("moving")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Moving()
    ```

---

> ## IsMovingForward

#### Parameters

-   `UNIT`: The unit to check if it is moving forward.

#### Returns `BOOL`

-   `true` if the unit is moving forward, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.IsMovingForward", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("IsMovingForward")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsMovingForward()
    ```

---

> ## IsMovingBackward

#### Parameters

-   `UNIT`: The unit to check if it is moving backward.

#### Returns `BOOL`

-   `true` if the unit is moving backward, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.IsMovingBackward", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("IsMovingBackward")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsMovingBackward()
    ```

---

> ## IsStrafeLeft

#### Parameters

-   `UNIT`: The unit to check if it is strafing left.

#### Returns `BOOL`

-   `true` if the unit is strafing left, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.IsStrafeLeft", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("IsStrafeLeft")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsStrafeLeft()
    ```

---

> ## IsStrafeRight

#### Parameters

-   `UNIT`: The unit to check if it is strafing right.

#### Returns `BOOL`

-   `true` if the unit is strafing right, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.IsStrafeRight", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("IsStrafeRight")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsStrafeRight()
    ```

---

> ## predictPosition

#### Parameters

-   `UNIT`: The unit whose position is to be predicted.
-   `seconds`: The time in seconds into the future for which to predict the unit's position.

#### Returns `NUMBER, NUMBER, NUMBER | NIL`

-   The predicted `x, y, z` coordinates of the unit, or `nil` if the prediction cannot be made.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.predictPosition(3)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("predictPosition")("UNIT", "3")
    ```

=== "Lua Mode"

    ```lua
    UNIT:PredictPosition(3)
    ```

---

> ## currentSpeed

#### Parameters

-   `UNIT`: The unit whose current speed to retrieve.

#### Returns `NUMBER`

-   The current speed of the unit in yards per second.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.currentSpeed > 5", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("currentSpeed")("UNIT") > 5
    ```

=== "Lua Mode"

    ```lua
    UNIT:CurrentSpeed() > 5
    ```

---

> ## walkSpeed

#### Parameters

-   `UNIT`: The unit whose walking speed to retrieve.

#### Returns `NUMBER`

-   The walking speed of the unit in yards per second.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.walkSpeed > 2", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("walkSpeed")("UNIT") > 2
    ```

=== "Lua Mode"

    ```lua
    UNIT:WalkSpeed() > 2
    ```

---

> ## runSpeed

#### Parameters

-   `UNIT`: The unit whose running speed to retrieve.

#### Returns `NUMBER`

-   The running speed of the unit in yards per second.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.runSpeed > 7", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("runSpeed")("UNIT") > 7
    ```

=== "Lua Mode"

    ```lua
    UNIT:RunSpeed() > 7
    ```

---

> ## backSpeed

#### Parameters

-   `UNIT`: The unit whose backward speed to retrieve.

#### Returns `NUMBER`

-   The backward speed of the unit in yards per second.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.backSpeed > 3", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("backSpeed")("UNIT") > 3
    ```

=== "Lua Mode"

    ```lua
    UNIT:BackSpeed() > 3
    ```

---

> ## swimSpeed

#### Parameters

-   `UNIT`: The unit whose swimming speed to retrieve.

#### Returns `NUMBER`

-   The swimming speed of the unit in yards per second.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.swimSpeed > 4", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("swimSpeed")("UNIT") > 4
    ```

=== "Lua Mode"

    ```lua
    UNIT:SwimSpeed() > 4
    ```

---

> ## target

#### Parameters

-   `UNIT1`: The unit whose target will be checked.
-   `UNIT2`: The unit to compare the target against.

#### Returns `BOOL`

-   `true` if the target of the specified unit1 matches the given unit2, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT1.target(UNIT2)", UNIT1},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("target")("UNIT1", "UNIT2")
    ```

=== "Lua Mode"

    ```lua
    UNIT1:Target(UNIT2)
    ```

---

> ## targetme

-   This condition checks if the specified unit is targeting the player.

#### Parameters

-   `UNIT`: The unit to check for targeting.

#### Returns `BOOL`

-   `true` if the unit is targeting the player, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.targetme", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("targetme")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsTargetMe()
    ```

---

> ## isplayer
>
> _`isplayer || player`_

#### Parameters

-   `UNIT`: The unit to be checked.

#### Returns `BOOL`

-   `true` if the unit is a player-controlled unit, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.isplayer", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("isplayer")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Isplayer()
    ```

---

> ## inphase

#### Parameters

-   `UNIT`: The unit to be checked for being in the same phase.

#### Returns `BOOL`

-   `true` if the unit is in the same phase as the player, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.inphase", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("inphase")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Inphase()
    ```

---

> ## exists

#### Parameters

-   `UNIT`: The unit to be checked for existence.

#### Returns `BOOL`

-   `true` if the unit exists, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.exists", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("exists")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Exists()
    ```

---

> ## guid

#### Parameters

-   `UNIT`: The unit for which to retrieve the GUID.

#### Returns `STRING`

-   The GUID of the target, or nil if the target is not valid.

#### _Example:_

=== "Lua Code"

    ```lua
    _A.DSL:Get("guid")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT.guid
    or
    UNIT:Guid()
    ```

---

> ## visible

#### Parameters

-   `UNIT`: The unit to check for visibility.

#### Returns `BOOL`

-   `true` if the unit is visible, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.visible", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("visible")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Visible()
    ```

---

> ## dead

#### Parameters

-   `UNIT`: The unit to check for death or ghost state.

#### Returns `BOOL`

-   `true` if the unit is dead or a ghost, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.dead", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("dead")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Dead()
    ```

---

> ## alive

#### Parameters

-   `UNIT`: The unit to check for being alive.

#### Returns `BOOL`

-   `true` if the unit is alive, `false` if it is dead or a ghost.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.alive", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("alive")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Alive()
    ```

---

> ## infront

#### Parameters

-   `UNIT`: The unit to check if the player is facing.

#### Returns `BOOL`

-   `true` if the player is facing the unit, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.infront", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("infront")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Infront()
    ```

---

> ## infrontof

#### Parameters

-   `UNIT1`: The unit that is checked to be in front.
-   `UNIT2`: The unit to check if it is facing UNIT.

#### Returns `BOOL`

-   `true` if unit2 is facing unit1, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT1.infrontof(UNIT2)", UNIT1},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("infrontof")("UNIT1", "UNIT2")
    ```

=== "Lua Mode"

    ```lua
    UNIT1:Infrontof(UNIT2)
    ```

---

> ## behind

#### Parameters

-   `UNIT`: The unit to check if the player is behind.

#### Returns `BOOL`

-   `true` if player is behind the unit, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.behind", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("behind")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Behind()
    ```

---

> ## behindof

#### Parameters

-   `UNIT1`: The unit to check if it is behind unit2.
-   `UNIT2`: The reference unit.

#### Returns `BOOL`

-   `true` if unit1 is behind unit2, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT1.behindof(UNIT2)", UNIT1},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("behindof")("UNIT1", "UNIT2")
    ```

=== "Lua Mode"

    ```lua
    UNIT1:Behindof(UNIT2)
    ```

---

> ## inConeOf

#### Parameters

-   `UNIT1`: The unit to check if it is within the cone.
-   `UNIT2_ANGLE`: The reference unit and the cone angle (optional, default angle is 180 degrees). Provide as a string in the format "unit2, angle".

#### Returns `BOOL`

-   `true` if unit1 is within the specified cone angle in front of unit2, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT1.inConeOf(UNIT2, 120)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("inConeOf")("UNIT1", "UNIT2, 120")
    ```

=== "Lua Mode"

    ```lua
    UNIT1:InConeOf(UNIT2, 120)
    ```

---

> ## lastmoved

#### Parameters

-   `UNIT`: The unit to check for movement.

#### Returns `NUMBER`

-   The `time in seconds` since the unit was last moved, or `0` if the unit is not valid or has not moved.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.lastmoved", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("lastmoved")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Lastmoved()
    ```

---

> ## movingfor

#### Parameters

-   `UNIT`: The unit to check for movement.

#### Returns `NUMBER`

-   The `time in seconds` that the unit has been continuously moving, or `0` if the unit is not valid or is not moving.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.movingfor", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("movingfor")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Movingfor()
    ```

---

> ## pvp

#### Parameters

-   `UNIT`: The unit to check for PvP flag with the player.

#### Returns `BOOL`

-   `true` if the unit is flagged for PvP, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.pvp", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("pvp")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Pvp()
    ```

---

> ## friend

#### Parameters

-   `UNIT`: The unit to check for friendly status.

#### Returns `BOOL`

-   `true` if the unit is friendly, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.friend", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("friend")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Friend()
    ```

---

> ## canassist

#### Parameters

-   `UNIT`: The unit to check for assist eligibility.

#### Returns `BOOL`

-   `true` if the player can assist the unit, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.canassist", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("canassist")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Canassist()
    ```

---

> ## enemy
>
> _`enemy || canattack`_

#### Parameters

-   `UNIT`: The unit to check for enemy status or attack eligibility.

#### Returns `BOOL`

-   `true` if the unit is an enemy, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.enemy", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("enemy")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Enemy()
    ```

---

> ## range

#### Parameters

-   `UNIT`: The unit to measure combat range against.

#### Returns `NUMBER`

-   The combat range between the player and the unit, or 999 if the range cannot be determined.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.range < 20", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("range")("UNIT") < 20
    ```

=== "Lua Mode"

    ```lua
    UNIT:Range() < 20
    ```

---

> ## rangefrom

#### Parameters

-   `UNIT1`: The first unit to measure combat range from.
-   `UNIT2`: The second unit to measure combat range to.

#### Returns `NUMBER`

-   The combat range between the two units, or 999 if the range cannot be determined.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT1.rangefrom(UNIT2) < 20", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("rangefrom")("UNIT1", "UNIT2") < 20
    ```

=== "Lua Mode"

    ```lua
    UNIT1:Rangefrom(UNIT2) < 20
    ```

---

> ## distance

#### Parameters

-   `UNIT`: The unit to measure distance against.

#### Returns `NUMBER`

-   The distance between the player and the unit, or 999 if the distance cannot be determined.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.distance < 20", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("distance")("UNIT") < 20
    ```

=== "Lua Mode"

    ```lua
    UNIT:Distance() < 20
    ```

---

> ## distancefrom

#### Parameters

-   `UNIT1`: The first unit to measure distance from.
-   `UNIT2`: The second unit to measure distance to.

#### Returns `NUMBER`

-   The distance between the two units, or 999 if the range cannot be determined.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT1.distancefrom(UNIT2) < 20", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("distancefrom")("UNIT1", "UNIT2") < 20
    ```

=== "Lua Mode"

    ```lua
    UNIT1:Distancefrom(UNIT2) < 20
    ```

---

> ## level

#### Parameters

-   `UNIT`: The unit whose level to retrieve.

#### Returns `NUMBER`

-   The level of the unit, or `-1` if the level cannot be determined.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.level >= 45", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("level")("UNIT") >= 45
    ```

=== "Lua Mode"

    ```lua
    UNIT:Level() >= 45
    ```

---

> ## combat

#### Parameters

-   `UNIT`: The unit to check for combat status.

#### Returns `BOOL`

-   `true` if the unit is in combat, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.combat", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("combat")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Combat()
    ```

---

> ## role

#### Parameters

-   `UNIT`: The unit whose role to retrieve.

#### Returns `STRING`

-   The role assigned to the target unit: `"TANK", "HEALER", "DAMAGER", or "UNKNOWN"` if the role cannot be determined.

    !!! info "For WOTLK version"

        For WOTLK version returns `TANK`, `HEALER`, `DAMAGER`, `MELEE`, `CASTER`, `NONE`

#### _Example:_

=== "Lua Code"

    ```lua
    _A.DSL:Get("role")("UNIT") == "HEALER"
    ```

=== "Lua Mode"

    ```lua
    UNIT.role == "HEALER"
    or
    UNIT:Role() == "HEALER"
    ```

---

> ## hasrole

#### Parameters

-   `UNIT`: The unit to check for the role.
-   `expectedRole` The expected role to search for within the unit's role.

    `"TANK", "HEALER", "DAMAGER", or "UNKNOWN"`

#### Returns `BOOL`

-   `true` if the unit has a role containing the expected name, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.hasrole(TANK)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("hasrole")("UNIT", "TANK")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Hasrole("TANK")
    ```

---

> ## name

#### Parameters

-   `UNIT`: The unit whose name to retrieve.

#### Returns `STRING`

-   The name of the unit, or `Unknown` if the name cannot be determined.

#### _Example:_

=== "Lua Code"

    ```lua
    _A.DSL:Get("name")("UNIT") == "Gul'dan"
    ```

=== "Lua Mode"

    ```lua
    UNIT.name == "Gul'dan"
    or
    UNIT:Name() == "Gul'dan"
    ```

---

> ## hasname

#### Parameters

-   `UNIT`: The unit to check for the name.
-   `expectedName` The expected name to search for within the unit's name.

#### Returns `BOOL`

-   `true` if the unit has a name containing the expected name, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.hasname(Gul'dan)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("hasname")("UNIT", "Gul'dan")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Hasname("Gul'dan")
    ```

---

> ## creature.type

#### Parameters

-   `UNIT`: The unit whose creature type to retrieve.

#### Returns `STRING`

-   The _`localized`_ creature type of the unit, or `nil` if the creature type cannot be determined.

    -   enUS
        `"Aberration"`, `"Beast"`, `"Critter"`, `"Demon"`, `"Dragonkin"`, `"Elemental"`, `"Gas Cloud"`, `"Giant"`, `"Humanoid"`, `"Mechanical"`,
        `"Non-combat Pet"`, `"Not specified"`, `"Totem"`, `"Undead"`, `"Wild Pet"`

#### _Example:_

=== "Lua Code"

    ```lua
    _A.DSL:Get("creature.type")("UNIT") ~= "Undead"
    ```

=== "Lua Mode"

    ```lua
    UNIT:CreatureType() ~= "Undead"
    ```

---

> ## hascreature.type

#### Parameters

-   `UNIT`: The unit to check for the creature type.
-   `expectedType` The _`localized`_ expected creature type to compare with.

#### Returns `BOOL`

-   `true` if the unit has the expected creature type, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.hascreature.type(Humanoid)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("hascreature.type")("UNIT", "Humanoid")
    ```

=== "Lua Mode"

    ```lua
    UNIT:HascreatureType("Humanoid")
    ```

---

> ## class

#### Parameters

-   `UNIT`: The unit whose class to retrieve.

#### Returns `STRING`

-   The class of the unit, or `Unknown` if the name cannot be determined.

#### _Example:_

=== "Lua Code"

    ```lua
    _A.DSL:Get("class")("UNIT") == "DEATHKNIGHT"
    ```

=== "Lua Mode"

    ```lua
    UNIT:Class() == "DEATHKNIGHT"
    ```

---

> ## hasclass

#### Parameters

-   `UNIT`: The unit to check for the class.
-   `expectedClass` The expected class name to compare with.

#### Returns `BOOL`

-   `true` if the unit belongs to the expected class, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.hasclass(WARRIOR)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("hasclass")("UNIT", "WARRIOR")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Hasclass("WARRIOR")
    ```

---

> ## inmelee

#### Parameters

-   `UNIT`: The unit to check for melee range.

#### Returns `BOOL`

-   `true` if the target unit is within melee range, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.inmelee", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("inmelee")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Inmelee()
    ```

---

> ## inranged

#### Parameters

-   `UNIT`: The unit to check for ranged combat range.

#### Returns `BOOL`

-   `true` if the unit is within the ranged combat range of 40, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.inranged", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("inranged")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Inranged()
    ```

---

> ## timetodie
>
> _`timetodie || deathin || ttd`_

#### Parameters

-   `UNIT`: The unit for which to estimate time to death.

#### Returns `NUMBER`

-   The estimated time to death in `seconds`. Returns a high value if is a dummy.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.ttd > 8", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("ttd")("UNIT") > 8
    ```

=== "Lua Mode"

    ```lua
    UNIT:Ttd() > 8
    ```

---

> ## charmed

#### Parameters

-   `UNIT`: The unit to check for being charmed.

#### Returns `BOOL`

-   `true` if the unit is charmed, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.charmed", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("charmed")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Charmed()
    ```

---

> ## timetopercent
>
> _`timetopercent || ttp`_

#### Parameters

-   `UNIT`: The unit for which to estimate time to reach a specific health percentage.
-   `PERCENTAGE`: The health percentage (0-100) to which you want to estimate the time. If not provided or invalid, defaults to 0%.

#### Returns `NUMBER`

-   The estimated time to X percentage in seconds. Returns a high value if the calculation cannot be performed.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.ttp(20) > 35", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("ttp")("UNIT", "20") > 35
    ```

=== "Lua Mode"

    ```lua
    UNIT:Ttp(20) > 35
    ```

---

> ## isdummy

#### Parameters

-   `UNIT`: The unit to check for being a dummy unit.

#### Returns `BOOL`

-   `true` if the unit is a dummy unit, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.isdummy", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("isdummy")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Isdummy()
    ```

---

> ## haste

#### Parameters

-   `UNIT`: The unit for which to retrieve the spell haste percentage.

#### Returns `NUMBER`

-   The spell haste `percentage` of the specified unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.haste > 30", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("haste")("UNIT") > 30
    ```

=== "Lua Mode"

    ```lua
    UNIT:Haste() > 30
    ```

---

> ## connected

#### Parameters

-   `UNIT`: The unit to check for being connected to the game world.

#### Returns `BOOL`

-   `true` if the specified unit is connected to the game world, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.connected", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("connected")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Connected()
    ```

---

> ## combat.time

#### Parameters

-   `UNIT`: The unit to check for combat time duration.

#### Returns `NUMBER`

-   The time duration in `seconds` for which the specified unit has been in combat.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.combat.time > 5", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("combat.time")("UNIT") > 5
    ```

=== "Lua Mode"

    ```lua
    UNIT:CombatTime() > 5
    ```

---

> ## los

#### Parameters

-   `UNIT`: The unit to check for line of sight.

#### Returns `BOOL`

-   `true` if there is line of sight between the player character and the specified unit, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.los", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("los")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Los()
    ```

---

> ## losfrom

#### Parameters

-   `UNIT1`: The first unit to check from.
-   `UNIT2`: The second unit to check line of sight to.

#### Returns `BOOL`

-   `true` if there is line of sight between the two specified units, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT1.losfrom(UNIT2)", UNIT1},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("losfrom")("UNIT1", "UNIT2")
    ```

=== "Lua Mode"

    ```lua
    UNIT1:Losfrom(UNIT2)
    ```

---

> ## hasloot

#### Parameters

-   `UNIT`: The unit to check for loot availability.

#### Returns `BOOL`

-   `true` if the specified unit has loot that can be looted by the player character, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.hasloot", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("hasloot")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Hasloot()
    ```

---

> ## tagged.byme

-   This condition checks if the specified unit is tagged by the player.

#### Parameters

-   `UNIT`: The unit to check for tagging.

#### Returns `BOOL`

-   `true` if the unit is tagged by the player, otherwise `false`.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.tagged.byme", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("tagged.byme")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsTaggedByMe()
    ```

---

> ## tagged.byother

-   This condition checks if the specified unit is tagged by other players.

#### Parameters

-   `UNIT`: The unit to check for tagging.

#### Returns `BOOL`

-   `true` if the unit is tagged by other players, otherwise `false`.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.tagged.byother", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("tagged.byother")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsTaggedByOther()
    ```

---

> ## spec

#### Parameters

-   `UNIT`: The unit for which to retrieve the specialization ID.

#### Returns `NUMBER`

-   The specialization ID of the specified unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.spec=73", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spec")("UNIT") == 73
    ```

=== "Lua Mode"

    ```lua
    UNIT:Spec() == 73
    ```

---

> ## hasSpec

#### Parameters

-   `UNIT`: The unit for which to check the specialization.
-   `expectedSpecId`: The expected specialization ID.

#### Returns `BOOL`

-   `true` if the unit has the expected specialization ID, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.hasSpec(73)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("hasSpec")("UNIT", "73")
    ```

=== "Lua Mode"

    ```lua
    UNIT:HasSpec(73)
    ```

---

> ## delay

#### Parameters

-   `UNIT`: The unit to check for the delay.
-   `name_secs`: A string containing the name and delay time (in seconds) separated by a comma.

#### Returns `BOOL`

-   `true` if the delay has passed, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.delay(delayName, 0.5)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("delay")("UNIT", "delayName, 0.5")
    ```

=== "Lua Mode"

    ```lua
    UNIT:delay("delayName", 0.5)
    ```

---

> ## timeout

#### Parameters

-   `UNIT`: The unit to check for the timeout.
-   `name_secs`: A string containing the name and timeout duration (in seconds) separated by a comma.

#### Returns `BOOL`

-   `true` if the timeout has not been reached, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.timeout(timeoutName, 0.5)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("timeout")("UNIT", "timeoutName, 0.5")
    ```

=== "Lua Mode"

    ```lua
    UNIT:timeout("timeoutName, 0.5")
    ```

---

> ## frame.visible

#### Parameters

-   `name`: The name of the frame to check for visibility.

#### Returns `BOOL`

-   `true` if the frame is currently shown, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.frame(TaxiFrame).visible", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("frame.visible")("UNIT", "TaxiFrame")
    ```

=== "Lua Mode"

    ```lua
    UNIT:frameVisible("TaxiFrame")
    ```

---

> ## sitting

#### Parameters

-   `UNIT`: The unit to check if it is sitting.

#### Returns `BOOL`

-   `true` if the unit is sitting, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.sitting", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("sitting")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsSitting()
    ```

---

> ## influenced

#### Parameters

-   `UNIT`: The unit to check if it is influenced.

#### Returns `BOOL`

-   `true` if the unit is influenced, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.influenced", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("influenced")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsInfluenced()
    ```

---

> ## controlled.byme

#### Parameters

-   `UNIT`: The unit to check if it is controlled by the player.

#### Returns `BOOL`

-   `true` if the unit is controlled by the player, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.controlled.byme", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("controlled.byme")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsPlayerControlled()
    ```

---

> ## istotem

#### Parameters

-   `UNIT`: The unit to check if it is a totem.

#### Returns `BOOL`

-   `true` if the unit is a totem, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.istotem", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("istotem")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsTotem()
    ```

---

> ## attackable

#### Parameters

-   `UNIT`: The unit to check if it is attackable.

#### Returns `BOOL`

-   `true` if the unit is attackable, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.attackable", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("attackable")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsNotAttackable()
    ```

---

> ## looting

#### Parameters

-   `UNIT`: The unit to check if it is looting.

#### Returns `BOOL`

-   `true` if the unit is looting, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.looting", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("looting")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsLooting()
    ```

---

> ## pet.incombat

#### Parameters

-   `UNIT`: The unit to check if the pet is in combat.

#### Returns `BOOL`

-   `true` if the pet is in combat, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.pet.incombat", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("pet.incombat")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsPetInCombat()
    ```

---

> ## pvp.flagged

#### Parameters

-   `UNIT`: The unit to check if it is flagged for PvP.

#### Returns `BOOL`

-   `true` if the unit is flagged for PvP, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.pvp.flagged", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("pvp.flagged")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsPvPFlagged()
    ```

---

> ## choked

#### Parameters

-   `UNIT`: The unit to check if it is choked.

#### Returns `BOOL`

-   `true` if the unit is choked, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.choked", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("choked")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsChoked()
    ```

---

> ## pacified

#### Parameters

-   `UNIT`: The unit to check if it is pacified.

#### Returns `BOOL`

-   `true` if the unit is pacified, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.pacified", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("pacified")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsPacified()
    ```

---

> ## stunned

#### Parameters

-   `UNIT`: The unit to check if it is stunned.

#### Returns `BOOL`

-   `true` if the unit is stunned, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.stunned", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("stunned")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsStunned()
    ```

---

> ## istaxi

#### Parameters

-   `UNIT`: The unit to check if it is on a taxi flight.

#### Returns `BOOL`

-   `true` if the unit is on a taxi flight, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.istaxi", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("istaxi")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsTaxiFlight()
    ```

---

> ## disarmed

#### Parameters

-   `UNIT`: The unit to check if it is disarmed.

#### Returns `BOOL`

-   `true` if the unit is disarmed, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.disarmed", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("disarmed")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsDisarmed()
    ```

---

> ## confused

#### Parameters

-   `UNIT`: The unit to check if it is confused.

#### Returns `BOOL`

-   `true` if the unit is confused, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.confused", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("confused")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsConfused()
    ```

---

> ## fleeing

#### Parameters

-   `UNIT`: The unit to check if it is fleeing.

#### Returns `BOOL`

-   `true` if the unit is fleeing, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.fleeing", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("fleeing")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsFleeing()
    ```

---

> ## possessed

#### Parameters

-   `UNIT`: The unit to check if it is possessed.

#### Returns `BOOL`

-   `true` if the unit is possessed, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.possessed", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("possessed")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsPossessed()
    ```

---

> ## selectable

#### Parameters

-   `UNIT`: The unit to check if it is selectable.

#### Returns `BOOL`

-   `true` if the unit is selectable, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.selectable", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("selectable")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsNotSelectable()
    ```

---

> ## skinnable

#### Parameters

-   `UNIT`: The unit to check if it is skinnable.

#### Returns `BOOL`

-   `true` if the unit is skinnable, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.skinnable", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("skinnable")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsSkinnable()
    ```

---

> ## mounted

#### Parameters

-   `UNIT`: The unit to check if it is mounted.

#### Returns `BOOL`

-   `true` if the unit is mounted, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.mounted", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("mounted")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsInMount()
    ```

---

> ## dazed

#### Parameters

-   `UNIT`: The unit to check if it is dazed.

#### Returns `BOOL`

-   `true` if the unit is dazed, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.dazed", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("dazed")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsDazed()
    ```

---

> ## sheathed

#### Parameters

-   `UNIT`: The unit to check if it is sheathed.

#### Returns `BOOL`

-   `true` if the unit is sheathed, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.sheathed", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("sheathed")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsSheathed()
    ```

---

> ## feign.death

#### Parameters

-   `UNIT`: The unit to check if it is feigning death.

#### Returns `BOOL`

-   `true` if the unit is feigning death, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.feign.death", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("feign.death")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IsFeignDeath()
    ```

---
