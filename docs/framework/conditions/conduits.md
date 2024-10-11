# CONDUITS

---

> ## conduit.rank

-   This condition returns the rank of a conduit by its spell name or ID.

#### Parameters

-   `spell`: The name or ID of the conduit spell.

#### Returns `NUMBER`

-   The rank of the conduit. If not found, returns 0.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "conduit(Harm Denial).rank >= 2"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("conduit.rank")(_, "Harm Denial") >= 2
    ```

=== "Lua Mode"

    ```lua
    PLAYER:ConduitRank("Harm Denial") >= 2
    ```

---

> ## conduit.active

-   This condition checks if a conduit with the given spell name or ID is active (has a rank greater than 0).

#### Parameters

-   `spell`: The name or ID of the conduit spell.

#### Returns `BOOL`

-   `true` if the conduit is active, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "conduit(Harm Denial).active"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("conduit.active")(_, "Harm Denial")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:ConduitActive("Harm Denial")
    ```
