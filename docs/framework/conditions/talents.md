# TALENTS

---

> ## talent

-   This condition checks if the specified talent is active or learned by the player.
    -   In modern WoW versions (Mists of Pandaria and later), talents are typically enabled/disabled. This condition returns `true` if the talent is enabled.
    -   In older WoW versions, talents have ranks. This condition returns `true` if the talent is learned with at least the specified rank.

#### Parameters

-   `ARG`:
    -   **Modern WoW**: The name of the talent (e.g., "Avatar") or its column and row as a string (e.g., "3,1").
    -   **Older WoW**: The name of the talent (e.g., "Improved Frostbolt") or the talent name and rank as a string (e.g., "Improved Frostbolt 2").

#### Returns `BOOL`

-   `true` if the talent condition is met, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    -- Modern WoW (by name)
    {ACTION, "talent(Avatar)"},
    -- Modern WoW (by column, row)
    {ACTION, "talent(3,1)"},
    -- Older WoW (by name, checks for at least rank 1)
    {ACTION, "talent(Improved Frostbolt)"},
    -- Older WoW (by name and rank, checks for at least rank 2)
    {ACTION, "talent(Improved Frostbolt 2)"},
    ```

=== "Lua Code"

    ```lua
    -- Modern WoW (by name)
    _A.DSL:Get("talent")(_, "Avatar")
    -- Modern WoW (by column, row)
    _A.DSL:Get("talent")(_, "3,1")
    -- Older WoW (by name, checks for at least rank 1)
    _A.DSL:Get("talent")(_, "Improved Frostbolt")
    -- Older WoW (by name and rank, checks for at least rank 2)
    _A.DSL:Get("talent")(_, "Improved Frostbolt 2")
    ```

=== "Lua Mode"

    ```lua
    -- Modern WoW (by name)
    PLAYER:Talent("Avatar")
    -- Modern WoW (by column, row)
    PLAYER:Talent("3,1")
    -- Older WoW (by name, checks for at least rank 1)
    PLAYER:Talent("Improved Frostbolt")
    -- Older WoW (by name and rank, checks for at least rank 2)
    PLAYER:Talent("Improved Frostbolt 2")
    ```
