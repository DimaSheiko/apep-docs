# AREA

---

> ## area.enemies

-   This condition counts the number of enemy units within a specified distance of a target unit.

#### Parameters

-   `UNIT`: The unit around which to count enemies.
-   `DISTANCE`: The maximum distance within which to count enemies (default is 40).

#### Returns `NUMBER`

-   The total number of enemy units within the specified distance of the target unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area(20).enemies >= 3", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("area.enemies")("UNIT", "20") >= 3
    ```

=== "Lua Mode"

    ```lua
    UNIT:AreaEnemies(20) >= 3
    ```

---

> ## area_range.enemies

-   This condition counts the number of enemy units within a specified range of a target unit.

#### Parameters

-   `UNIT`: The unit around which to count enemies.
-   `RANGE`: The maximum range within which to count enemies (default is 40).

#### Returns `NUMBER`

-   The total number of enemy units within the specified range of the target unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area_range(20).enemies >= 3", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("area_range.enemies")("UNIT", "20") >= 3
    ```

=== "Lua Mode"

    ```lua
    UNIT:Area_rangeEnemies(20) >= 3
    ```

---

> ## area.combatenemies
>
> _`area.combatenemies || area.cbenemies`_

-   This condition counts the number of enemy combat units within a specified distance of a target unit.

#### Parameters

-   `UNIT`: The unit around which to count enemies.
-   `DISTANCE`: The maximum distance within which to count combat enemies (default is 40).

#### Returns `NUMBER`

-   The total number of combat enemy units within the specified distance of the target unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area(20).combatenemies >= 3", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("area.combatenemies")("UNIT", "20") >= 3
    ```

=== "Lua Mode"

    ```lua
    UNIT:AreaCombatenemies(20) >= 3
    ```

---

> ## area_range.combatenemies
>
> _`area_range.combatenemies || area_range.cbenemies`_

-   This condition counts the number of enemy combat units within a specified range of a target unit. The check is for units with a range less than the specified value.

#### Parameters

-   `UNIT`: The unit around which to count enemies.
-   `RANGE`: The maximum range within which to count combat enemies (default is 40).

#### Returns `NUMBER`

-   The total number of combat enemy units within the specified range of the target unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area_range(20).combatenemies >= 3", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("area_range.combatenemies")("UNIT", "20") >= 3
    ```

=== "Lua Mode"

    ```lua
    UNIT:Area_rangeCombatenemies(20) >= 3
    ```

---

> ## area.enemies.infront

-   This condition counts the number of enemy units within a specified distance that are in front of the provided unit.

#### Parameters

-   `UNIT`: The unit to use as the reference point for checking enemy positions (e.g., "player", "target").
-   `DISTANCE`: The maximum distance to consider for counting enemies (default is 40).

#### Returns `NUMBER`

-   The total count of enemy units that are both within the specified distance and in front of the provided unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area(20).enemies.infront >= 3", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("area.enemies.infront")("UNIT", "20") >= 3
    ```

=== "Lua Mode"

    ```lua
    UNIT:AreaEnemiesInfront(20) >= 3
    ```

---

> ## area_range.enemies.infront

-   This condition counts the number of enemy units within a specified combat range that are in front of the provided unit.

#### Parameters

-   `UNIT`: The unit to use as the reference point for checking enemy positions (e.g., "player", "target").
-   `RANGE`: The maximum combat range to consider for counting enemies (default is 40).

#### Returns `NUMBER`

-   The total count of enemy units that are both within the specified combat range and in front of the provided unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area_range(20).enemies.infront >= 3", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("area_range.enemies.infront")("UNIT", "20") >= 3
    ```

=== "Lua Mode"

    ```lua
    UNIT:Area_rangeEnemiesInfront(20) >= 3
    ```

---

> ## area.combatenemies.infront
>
> _`area.combatenemies.infront || area.cbenemies.infront`_

-   This condition counts the number of enemy combat units within a specified distance that are also in front of a target unit.

#### Parameters

-   `UNIT`: The unit around which to count enemies.
-   `DISTANCE`: The maximum distance within which to count combat enemies (default is 40).

#### Returns `NUMBER`

-   The total number of combat enemy units within the specified distance of the target unit and in front of it.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area(20).combatenemies.infront >= 3", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("area.combatenemies.infront")("UNIT", "20") >= 3
    ```

=== "Lua Mode"

    ```lua
    UNIT:AreaCombatenemiesInfront(20) >= 3
    ```

---

> ## area_range.combatenemies.infront
>
> _`area_range.combatenemies.infront || area_range.cbenemies.infront`_

-   This condition counts the number of enemy combat units within a specified combat range that are also in front of a target unit. The check is for units with a range less than the specified value.

#### Parameters

-   `UNIT`: The unit around which to count enemies.
-   `RANGE`: The maximum combat range within which to count combat enemies (default is 40).

#### Returns `NUMBER`

-   The total number of combat enemy units within the specified combat range of the target unit and in front of it.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area_range(20).combatenemies.infront >= 3", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("area_range.combatenemies.infront")("UNIT", "20") >= 3
    ```

=== "Lua Mode"

    ```lua
    UNIT:Area_rangeCombatenemiesInfront(20) >= 3
    ```

---

> ## area.friendly

-   This condition counts the number of friendly units within a specified distance of a target unit, using interaction range (type 2).

#### Parameters

-   `UNIT`: The target unit around which to count friendly units.
-   `DISTANCE`: The maximum distance within which to count friendly units (default is 40).

#### Returns `NUMBER`

-   The total number of friendly units within the specified distance of the target unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area(20).friendly >= 3", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("area.friendly")("UNIT", "20") >= 3
    ```

=== "Lua Mode"

    ```lua
    UNIT:AreaFriendly(20) >= 3
    ```

---

> ## area.roster

-   This condition counts the number of player units in the raid or party roster within a specified distance of a target unit.

#### Parameters

-   `UNIT`: The target unit around which to count roster units.
-   `DISTANCE`: The maximum distance within which to count roster units (default is 40).

#### Returns `NUMBER`

-   The total number of roster units within the specified distance of the target unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area(20).roster >= 3", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("area.roster")("UNIT", "20") >= 3
    ```

=== "Lua Mode"

    ```lua
    UNIT:AreaRoster(20) >= 3
    ```

---

> ## area.friendly.infront

-   This condition counts the number of friendly units within a specified distance from the target unit, considering only units that are in front of the target. Uses interaction range (type 2) for distance check.

#### Parameters

-   `UNIT`: The target unit around which to count friendly units.
-   `DISTANCE`: The maximum distance within which to count friendly units (default is 40).

#### Returns `NUMBER`

-   The total number of friendly units within the specified distance from the target unit and in front of it.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area(20).friendly.infront >= 3", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("area.friendly.infront")("UNIT", "20") >= 3
    ```

=== "Lua Mode"

    ```lua
    UNIT:AreaFriendlyInfront(20) >= 3
    ```

---

> ## area.incdmg

-   This condition calculates the total incoming damage for all units in the raid or party roster within a specified distance from the target unit.

#### Parameters

-   `UNIT`: The target unit around which to calculate the incoming damage from roster units.
-   `DISTANCE`: The maximum distance within which to consider roster units (default is 40).

#### Returns `NUMBER`

-   The total incoming damage from roster units within the specified distance from the target unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area(20).incdmg >= 400000", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("area.incdmg")("UNIT", "20") >= 400000
    ```

=== "Lua Mode"

    ```lua
    UNIT:AreaIncdmg(20) >= 400000
    ```

---

> ## area.dead

-   This condition counts the number of dead units within a specified distance of a target unit. The specific type of "dead" units depends on the Object Manager's "Dead" list.

#### Parameters

-   `UNIT`: The target unit around which to count dead units.
-   `DISTANCE`: The maximum distance within which to count dead units (default is 40).

#### Returns `NUMBER`

-   The total number of dead units within the specified distance of the target unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area(20).dead >= 1", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("area.dead")("UNIT", "20") >= 1
    ```

=== "Lua Mode"

    ```lua
    UNIT:AreaDead(20) >= 1
    ```

---

> ## area.roster.infront

-   This condition counts the number of units in the raid or party roster within a specified distance from the target unit, considering only units that are in front of the target.

#### Parameters

-   `UNIT`: The target unit around which to count roster units.
-   `DISTANCE`: The maximum distance within which to count roster units (default is 40).

#### Returns `NUMBER`

-   The total number of roster units within the specified distance from the target unit and in front of it.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area(20).roster.infront >= 3", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("area.roster.infront")("UNIT", "20") >= 3
    ```

=== "Lua Mode"

    ```lua
    UNIT:AreaRosterInfront(20) >= 3
    ```

---

> ## area.roster.incdmg

-   This condition calculates the total incoming damage for all units in the raid or party roster within a specified distance from the target unit.

#### Parameters

-   `UNIT`: The target unit around which to calculate the incoming damage from roster units.
-   `DISTANCE`: The maximum distance within which to consider roster units (default is 40).

#### Returns `NUMBER`

-   The total incoming damage from roster units within the specified distance from the target unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area(20).roster.incdmg >= 400000", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("area.roster.incdmg")("UNIT", "20") >= 400000
    ```

=== "Lua Mode"

    ```lua
    UNIT:AreaRosterIncdmg(20) >= 400000
    ```

---

> ## area.dead.roster

-   This condition calculates the number of dead player units in the raid or party roster within a specified distance from the target unit.

#### Parameters

-   `UNIT`: The target unit around which to count dead player units in the roster.
-   `DISTANCE`: The maximum distance within which to count roster units (default is 40).

#### Returns `NUMBER`

-   The number of dead player units within the specified distance from the target unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area(20).dead.roster >= 3", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("area.dead.roster")("UNIT", "20") >= 3
    ```

=== "Lua Mode"

    ```lua
    UNIT:AreaDeadRoster(20) >= 3
