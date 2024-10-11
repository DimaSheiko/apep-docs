# DBM

---

> ## dbm

-   This condition checks the remaining time of a specific event timer from the `Deadly Boss Mods` (DBM) addon.

#### Parameters

-   `event`(string): The name of the event timer to check.

#### Returns `NUMBER`

-   The remaining time of the specified DBM event timer, or a default value of 999 if the timer is not found.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "dbm(Pull in) < 3"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("dbm")(_, "Pull in") < 3
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Dbm("Pull in") < 3
    ```
