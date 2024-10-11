# TALENTS

---

> ## talent

-   This condition checks if the specified talent is active on the player.

#### Returns `BOOL`

-   `true` if the specified talent is active, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "talent(Avatar)"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("talent")(_, "Avatar")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Talent("Avatar")
    ```
