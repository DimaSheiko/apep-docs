# ITEM

---

> ## item
>
> _`item || equipped`_

-   Checks whether a specific item is currently equipped by the player.

#### Parameters

-   `NameOrID`: The item name or ID to check for.

#### Returns `BOOL`

-   `true` if the specified item is currently equipped, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "equipped(Draught of Souls)"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("equipped")(_, "Draught of Souls")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Equipped("Draught of Souls")
    ```

---

> ## item.cooldown

-   Checks the cooldown remaining for the player specific item.

#### Parameters

-   `NameOrID`: The item name or ID to check the cooldown for.

#### Returns `NUMBER`

-   The remaining cooldown time in `seconds` for the specified item, or 0 if not on cooldown.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "item(Draught of Souls).cooldown >= 20"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("item.cooldown")(_, "Draught of Souls") >= 20
    ```

=== "Lua Mode"

    ```lua
    PLAYER:ItemCooldown("Draught of Souls") >= 20
    ```

---

> ## item.usable

-   Checks if a specific item is usable by the player. This method accepts item name, item ID, slot name, or slot number.

#### Parameters

-   `NameOrID`: The item name, item ID, slot name (e.g., `"trinket1"`, `"mainhand"`), or slot number to check for usability.

#### Returns `BOOL`

-   `true` if the item is usable, `false` otherwise.

!>**Note:** You can use slot names like `"trinket1"`, `"trinket2"`, `"mainhand"`, etc., or slot numbers (see [SlotAlias table](../../api/apep/index.md#slotalias)).

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "item(Draught of Souls).usable"},
    {ACTION, "item(trinket1).usable"}, -- (1)!
    {ACTION, "item(13).usable"}, -- (2)!
    ```

    1. Using slot name
    2. Using slot number (13 = Trinket0Slot)

=== "Lua Code"

    ```lua
    _A.DSL:Get("item.usable")(_, "Draught of Souls")
    _A.DSL:Get("item.usable")(_, "trinket1")
    _A.DSL:Get("item.usable")(_, 13)
    ```

=== "Lua Mode"

    ```lua
    PLAYER:ItemUsable("Draught of Souls")
    PLAYER:ItemUsable("trinket1")
    PLAYER:ItemUsable(13)
    ```

---

> ## item.IdBySlot

-   Returns the item ID equipped in a given inventory slot.

#### Parameters

-   `SLOT`: The inventory slot to check, by number or name (e.g., `"head"`, `"mainhand"`, `"trinket1"`).

#### Returns `NUMBER`

-   The item ID of the equipped item in that slot, or `-1` if none is found.

!>**Note:** See [SlotAlias table](../../api/apep/index.md#slotalias) for slot names and numbers.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "item.IdBySlot(trinket1) = 79329"}, -- (1)!
    {ACTION, "item.IdBySlot(13) = 79329"}, -- (2)!
    ```

    1. Using slot name
    2. Using slot number (13 = Trinket0Slot)

=== "Lua Code"

    ```lua
    _A.DSL:Get("item.IdBySlot")(_, "trinket1") == 79329
    _A.DSL:Get("item.IdBySlot")(_, 13) == 79329
    ```

=== "Lua Mode"

    ```lua
    PLAYER:ItemIdBySlot("trinket1") == 79329
    PLAYER:ItemIdBySlot(13) == 79329
    ```

---

> ## item.count

-   Checks the count of a specific item in the player's bags.

#### Parameters

-   `NameOrID`: The item name or ID to check the count of.

#### Returns `NUMBER`

-   The count of the specified item in the player's bags.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "item(Healthstone).count > 0"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("item.count")(_, "Healthstone") > 0
    ```

=== "Lua Mode"

    ```lua
    PLAYER:ItemCount("Healthstone") > 0
    ```

---

> ## item.range

-   Checks if the player's target is within range of using a specific item.

#### Parameters

-   `NameOrID`: The item name or ID to check the range for.

#### Returns `BOOL`

-   `true` if the player's target is within range of using the item, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "item(Sunblood Amethyst).range"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("item.range")(_, "Sunblood Amethyst")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:ItemRange("Sunblood Amethyst")
    ```

---

> ## ilevel

-   Returns the average item level of the player.

#### Returns `NUMBER`

-   The average item level of the player.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "ilevel >= 240"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("ilevel")() >= 240
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Ilevel() >= 240
    ```

---

> ## twohand

-   Checks if the player has a two-handed weapon equipped.

#### Returns `BOOL`

-   `true` if the player has a two-handed weapon equipped, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "twohand"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("twohand")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Twohand()
    ```

---

> ## onehand

-   Checks if the player has a one-handed weapon equipped.

#### Returns `BOOL`

-   `true` if the player has a one-handed weapon equipped, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "onehand"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("onehand")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Onehand()
    ```

---

> ## item.enchant

-   Retrieves the enchant ID applied to an equipped item.

#### Parameters

-   `slotname_or_slotid` (string|number): The inventory slot to check. Accepts either:
    -   The numeric slot ID
    -   The slot name

#### Returns `STRING`

-   Returns the enchant ID as a string if found.
-   Returns `"0"` if the item has no enchant or `"-1"` if the slot is empty.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "item.enchant(gloves) = 3603"},
    {ACTION, "item.enchant(10) = 3603"},
    {ACTION, "item.enchant(feet) = 0"},
    {ACTION, "item.enchant(head) = -1"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("item.enchant")(_, "gloves")   --> "3603"
    _A.DSL:Get("item.enchant")(_, 10)         --> "3603"
    _A.DSL:Get("item.enchant")(_, "feet")     --> "0"
    _A.DSL:Get("item.enchant")(_, "head")     --> "-1"
    ```

=== "Lua Mode"

    ```lua
    PLAYER:ItemEnchant("gloves")   --> "3603"
    PLAYER:ItemEnchant(10)         --> "3603"
    PLAYER:ItemEnchant("feet")     --> "0"
    PLAYER:ItemEnchant("head")     --> "-1"
    ```

---

> ## tier

-   Returns the number of equipped items from a specific tier set for the player's class.

#### Parameters

-   `Tnum`: The tier set number (e.g., `"T18", "T19", "T20", etc`).

#### Returns `NUMBER`

-   The number of equipped items from the specified tier set for the player's class.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "tier(T20) >= 2"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("tier")(_, "T20") >= 2
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Tier("T20") >= 2
    ```
