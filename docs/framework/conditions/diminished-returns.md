# DIMINISHED RETURNS

---

> ## dr.state

This condition checks the diminished returns state for a specific spell on a unit.

#### Parameters

-   `UNIT`: The unit for which to check DR.
-   `SPELL`: The spell for which to check DR.

#### Returns `NUMBER`

-   The diminished state `1`, `0.5`, `0.25`, `0` for the specified spell on the unit, or `-1` if not found.

#### State Description

| State | Description      |
| ----- | ---------------- |
| 1     | Full duration    |
| 0.5   | Half duration    |
| 0.25  | Quarter duration |
| 0     | Immune           |

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "dr(Cyclone).state >= 0.5", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("dr.state")(_, "Cyclone") >= 0.5
    ```

=== "Lua Mode"

    ```lua
    PLAYER:DrState("Cyclone") >= 0.5
    ```

> ## dr.timetomax

_`dr.timetomax || dr.ttm`_

This condition calculates the time remaining until the diminished returns for a specific spell on a unit reach their maximum state.

#### Parameters

-   `UNIT`: The unit for which to calculate the time to maximum DR.
-   `SPELL`: The spell for which to calculate the time to maximum DR.

#### Returns `NUMBER`

-   The time remaining in seconds until the diminished returns reach their maximum state `1` (full duration), or `-1` if not found.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "dr(Cyclone).timetomax <= 0", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("dr.timetomax")(_, "Cyclone") <= 0
    ```

=== "Lua Mode"

    ```lua
    PLAYER:DrTimetomax("Cyclone") <= 0
    ```
