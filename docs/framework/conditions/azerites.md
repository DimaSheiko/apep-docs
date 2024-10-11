# AZERITE

---

> ## azerite.count

-   This condition returns the number of equipment items that contain Azerite power for a specific spell.

#### Parameters

-   `spell`: The name of the spell to check for Azerite power.

#### Returns `NUMBER`

-   The number of equipment items that contain Azerite power for the specified spell.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "azerite(Dance of Death).count >= 2"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("azerite.count")(_, "Dance of Death") >= 2
    ```

=== "Lua Mode"

    ```lua
    PLAYER:AzeriteCount("Dance of Death") >= 2
    ```

---

> ## azerite.active

-   This condition checks if the specified spell has active Azerite power.

#### Parameters

-   `spell`: The spell for which to check active Azerite power.

#### Returns `BOOL`

-   `true` if the specified spell has active Azerite power, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "azerite(Overflowing Mists).active"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("azerite.active")(_, "Overflowing Mists")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:AzeriteActive("Overflowing Mists")
    ```
