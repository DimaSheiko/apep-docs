# HEAL

---

> ## health

-   This condition returns the health percentage of the specified unit.

#### Parameters

-   `UNIT`: The unit to retrieve the health percentage from.

#### Returns `NUMBER`

-   The health percentage of the unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.health >= 80", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("health")("UNIT") >= 80
    ```

=== "Lua Mode"

    ```lua
    UNIT:Health() >= 80
    ```

---

> ## health.actual

-   This condition returns the actual health value of the specified unit.

#### Parameters

-   `UNIT`: The unit to retrieve the actual health value from.

#### Returns `NUMBER`

-   The actual health value of the unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.health.actual >= 35000", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("health.actual")("UNIT") >= 35000
    ```

=== "Lua Mode"

    ```lua
    UNIT:HealthActual() >= 35000
    ```

---

> ## health.max

-   This condition returns the maximum health value of the specified unit.

#### Parameters

-   `UNIT`: The unit to retrieve the maximum health value from.

#### Returns `NUMBER`

-   The maximum health value of the unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.health.max >= 150000", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("health.max")("UNIT") >= 150000
    ```

=== "Lua Mode"

    ```lua
    UNIT:HealthMax() >= 150000
    ```

---

> ## health.predicted
>
> _`health.predicted || healthp`_

-   This condition returns the predicted health percentage of the specified unit.

#### Parameters

-   `UNIT`: The unit to calculate the predicted health percentage for.

#### Returns `NUMBER`

-   The predicted health percentage of the target unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.health.predicted >= 80", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("health.predicted")("UNIT") >= 80
    ```

=== "Lua Mode"

    ```lua
    UNIT:HealthPredicted() >= 80
    ```

---

> ## health.predicted.actual

-   This condition returns the predicted actual health value of the specified unit.

#### Parameters

-   `UNIT`: The unit to retrieve the predicted actual health value from.

#### Returns `NUMBER`

-   The predicted actual health value of the unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.health.predicted.actual >= 35000", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("health.predicted.actual")("UNIT") >= 35000
    ```

=== "Lua Mode"

    ```lua
    UNIT:HealthPredictedActual() >= 35000
    ```

---

> ## area.heal

-   This condition counts the number of player units within a specified distance of a target unit that have health equal to or below a certain threshold.

#### Parameters

-   `UNIT`: The central unit to check around.
-   `ARGS`: A string containing two arguments separated by a comma:
    -   `distance` (optional, default: 20): The maximum distance from the central unit.
    -   `health` (optional, default: 100): The health percentage threshold (units with health <= this value are counted).

#### Returns `NUMBER`

-   The total count of player units within the specified distance and health threshold.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area(40, 80).heal >= 4", UNIT},
    ```
    *This action will trigger if there are at least 4 player units within 40 yards of `UNIT` who have 80% health or less.*

=== "Lua Code"

    ```lua
    _A.DSL:Get("area.heal")("UNIT", "40, 80") >= 4
    ```

=== "Lua Mode"

    ```lua
    UNIT:AreaHeal(40, 80) >= 4
    ```

---

> ## area.heal.infront

-   This condition counts the number of player units within a specified distance of a target unit, have health below a certain threshold, and are located in front of the target unit.

#### Parameters

-   `UNIT`: The central unit to check around and whose 'front' is considered.
-   `ARGS`: A string containing two arguments separated by a comma:
    -   `distance` (optional, default: 20): The maximum distance from the central unit.
    -   `health` (optional, default: 100): The health percentage threshold (units with health < this value are counted).

#### Returns `NUMBER`

-   The total count of player units within the specified distance, below the health threshold, and in front of the central unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area(40, 80).heal.infront >= 4", UNIT},
    ```
    *This action will trigger if there are at least 4 player units within 40 yards of `UNIT`, in front of `UNIT`, and who have less than 80% health.*

=== "Lua Code"

    ```lua
    _A.DSL:Get("area.heal.infront")("UNIT", "40, 80") >= 4
    ```

=== "Lua Mode"

    ```lua
    UNIT:AreaHealInfront(40, 80) >= 4
    ```

---

> ## area.roster.avrHP

-   This condition calculates the average health of player units within a specified range of a given unit, considering only those units whose health is at or below a certain threshold. It returns both the average health and the count of units considered.

#### Parameters

-   `UNIT`: The central unit.
-   `ARGS`: A string containing two arguments separated by a comma:
    -   `range`: The maximum distance from the central unit.
    -   `threshold` (optional, default: 100): The maximum health percentage for a unit to be included in the calculation (e.g., if 50, only units with 50% health or less are considered).

#### Returns `NUMBER, NUMBER`

-   The first return value is the average health percentage of the qualifying units. Returns `100` if no units meet the criteria.
-   The second return value is the count of units that were included in the average calculation.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.area.roster.avrHP(30, 60) < 50", UNIT},
    ```
    *This action will trigger if the average health of units within 30 yards of `UNIT` that have 60% health or less is below 50%.*

=== "Lua Code"

    ```lua
    local avgHP, count = _A.DSL:Get("area.roster.avrHP")("UNIT", "30, 60")
    if avgHP < 50 then
        -- Action logic
    end
    ```
    *Note: DSL typically uses the first return value for comparisons.*

=== "Lua Mode"

    ```lua
    local avgHP, count = UNIT:AreaRosterAvrHP(30, 60)
    if avgHP < 50 then
        -- Action logic
    end
    ```

---

> ## healAverage

-   This condition calculates the average health percentage of all player units within a specified radius from the player.

#### Parameters

-   `UNIT`: This parameter is typically ignored in the function's logic, which always calculates around the player. It's usually the player unit itself.
-   `RADIUS`: The radius around the player within which to calculate the average health.

#### Returns `NUMBER`

-   The average health percentage of player units within the specified radius. Returns `101` if no units are found.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "player.healAverage(40) < 70", player},
    ```
    *This action will trigger if the average health of all player units within a 40-yard radius of the player is less than 70%.*

=== "Lua Code"

    ```lua
    _A.DSL:Get("healAverage")("player", "40") < 70
    ```

=== "Lua Mode"

    ```lua
    player:HealAverage(40) < 70
    ```

---

> ## healAverageOf

-   This condition calculates the average health percentage of the 'N' closest player units within a specified radius from the player.

#### Parameters

-   `UNIT`: This parameter is typically ignored in the function's logic, which always calculates around the player. It's usually the player unit itself.
-   `ARGS`: A string containing two arguments separated by a comma:
    -   `num`: The number of closest units to consider for the average.
    -   `radius`: The radius around the player to search for units.

#### Returns `NUMBER`

-   The average health percentage of the 'N' closest player units within the specified radius. Returns `101` if no units are found.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "player.healAverageOf(5, 30) < 60", player},
    ```
    *This action will trigger if the average health of the 5 closest player units within a 30-yard radius of the player is less than 60%.*

=== "Lua Code"

    ```lua
    _A.DSL:Get("healAverageOf")("player", "5, 30") < 60
    ```

=== "Lua Mode"

    ```lua
    player:HealAverageOf(5, 30) < 60
