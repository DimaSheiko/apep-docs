# ESSENCES

---

> ## essence.rank

-   This condition retrieves the rank of a specific essence by name and slot(optional).

#### Parameters

-   `args`(string): A string in the format `essenceName, slotName` or just `essenceName`.
    -   `essenceName`: The name of the essence to check for rank.
    -   `slotName`: The slot name to check for rank (optional, can be "main" or "passive").

#### Returns `NUMBER`

-   The rank of the specified essence in the specified slot.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "essence(Essence of the Focusing Iris, passive).rank >= 2"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("essence.rank")(_, "The Well of Existence, main") >= 2
    ```

=== "Lua Mode"

    ```lua
    PLAYER:EssenceRank("Blood of the Enemy, main") >= 2
    ```

```

```
