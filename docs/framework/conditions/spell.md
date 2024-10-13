# SPELL

---

> ## spell.cooldown

#### Parameters

-   `SPELL`: The name or ID of the spell to check the cooldown for.

#### Returns `NUMBER`

-   The remaining cooldown time in `seconds` for the specified spell.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "spell(Nature's Cure).cooldown < 1"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spell.cooldown")(_, "Nature's Cure") < 1
    ```

=== "Lua Mode"

    ```lua
    PLAYER:SpellCooldown("Nature's Cure") < 1
    ```

---

> ## spell.recharge

#### Parameters

-   `SPELL`: The name or ID of the spell to check the recharge for.

#### Returns `NUMBER`

-   The remaining recharge time in `seconds` for the specified spell.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "spell(Nature's Cure).recharge < 1"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spell.recharge")(_, "Nature's Cure") < 1
    ```

=== "Lua Mode"

    ```lua
    PLAYER:SpellRecharge("Nature's Cure") < 1
    ```

---

> ## spell.charges

-   If the spell has a recharge time, it takes into account the remaining charges and the time since the last used charge to estimate the fractional charges.

#### Parameters

-   `SPELL`: The name or ID of the spell to check charges for.

#### Returns `NUMBER`

-   The number of available charges for the specified spell.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "spell(Heroic Leap).charges > 1"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spell.charges")(_, "Heroic Leap") > 1
    ```

=== "Lua Mode"

    ```lua
    PLAYER:SpellCharges("Heroic Leap") > 1
    ```

---

> ## spell.count

#### Parameters

-   `SPELL`: The name or ID of the spell to count.

#### Returns `NUMBER`

-   The number of times a spell can be casted.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "spell(Starfire).count == 2"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spell.count")(_, "Starfire") == 1
    ```

=== "Lua Mode"

    ```lua
    PLAYER:SpellCount("Starfire") == 1
    ```

---

> ## spell.usable

#### Parameters

-   `SPELL`: The name or ID of the spell to check the usability for.

#### Returns `BOOL`

-   `true` if the specified spell is usable, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "spell(Swiftmend).usable"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spell.usable")(_, "Swiftmend")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:SpellUsable("Swiftmend")
    ```

---

> ## spell.exists

#### Parameters

-   `SPELL`: The name or ID of the spell to check for existence.

#### Returns `BOOL`

-   `true` if the specified spell exists in the player's spellbook, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "spell(Flourish).exists"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spell.exists")(_, "Flourish")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:SpellExists("Flourish")
    ```

---

> ## spell.ready

#### Parameters

-   `SPELL`: The name or ID of the spell to check for readiness. It considers the spell's cooldown, global cooldown, and network latency.

#### Returns `BOOL`

-   `true` if the specified spell is ready for use, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "spell(Renewal).ready"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spell.ready")(_, "Renewal")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:SpellReady("Renewal")
    ```

---

> ## spell.range

#### Parameters

-   `UNIT`: The target unit to check range against.
-   `SPELL`: The name or ID of the spell to check range for.

#### Returns `BOOL`

-   `true` if the unit is within range of the spell, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.spell(Aimed Shot).range", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spell.range")("UNIT", "Aimed Shot")
    ```

=== "Lua Mode"

    ```lua
    UNIT:SpellRange("Aimed Shot")
    ```

---

> ## spell.cost

#### Parameters

-   `SPELL`: The name or ID of the spell to retrieve costs for.

#### Returns `NUMBER`

-   The amount of `"MANA", "RAGE", "FOCUS", "ENERGY", "HAPPINESS", "RUNES", "RUNIC_POWER", "SOUL_SHARDS", "HOLY_POWER", "STAGGER", "CHI", "FURY", "PAIN", "LUNAR_POWER", "INSANITY"` required to cast the spell.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "spell(Ignore Pain).cost >= 50"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spell.cost")(_, "Ignore Pain") >= 50
    ```

=== "Lua Mode"

    ```lua
    PLAYER:SpellCost("Ignore Pain") >= 50
    ```

---

> ## spell.casttime

#### Parameters

-   `SPELL`: The name or ID of the spell to retrieve the cast time for.

#### Returns `NUMBER`

-   The cast time of the spell in `seconds`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "spell(Aimed Shot).casttime < 0.9"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spell.casttime")(_, "Aimed Shot") < 0.9
    ```

=== "Lua Mode"

    ```lua
    PLAYER:SpellCasttime("Aimed Shot") < 0.9
    ```

---

> ## spell.proc

-   This condition checks if a specified spell is currently active as a proc.

#### Parameters

-   `SPELL`: The name or ID of the spell to check for as a proc.

#### Returns `BOOL`

-   `true` if the spell is currently active as a proc, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "spell(Ferocious Bite).proc"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spell.proc")(_, "Ferocious Bite")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:SpellProc("Ferocious Bite")
    ```

---

> ## enchanted.mainhand

-   This condition checks if the player's main-hand weapon has an enchantment.

#### Returns `BOOL`

-   `true` if the player's main-hand weapon has an enchantment, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "enchanted.mainhand"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("enchanted.mainhand")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:EnchantedMainhand()
    ```

---

> ## enchanted.offhand

-   This condition checks if the player's off-hand weapon has an enchantment.

#### Returns `BOOL`

-   `true` if the player's off-hand weapon has an enchantment, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "enchanted.offhand"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("enchanted.offhand")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:EnchantedOffhand()
    ```

---

> ## hasMainHandEnchant

-   This condition checks if the main hand weapon is enchanted with a specific spell.

#### Parameters

-   `SPELL`: The name or ID of the spell to check for on the main hand weapon enchant.

#### Returns `BOOL`

-   `true` if main hand weapon is enchanted with the spell, false otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "hasMainHandEnchant(Flametongue Weapon)"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("hasMainHandEnchant")(_, "Flametongue Weapon")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:hasMainHandEnchant("Flametongue Weapon")
    ```

---

> ## hasOffHandEnchant

-   This condition checks if the off hand weapon is enchanted with a specific spell.

#### Parameters

-   `SPELL`: The name or ID of the spell to check for on the off hand weapon enchant.

#### Returns `BOOL`

-   `true` if off hand weapon is enchanted with the spell, false otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "hasOffHandEnchant(Windfury Weapon)"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("hasOffHandEnchant")(_, "Windfury Weapon")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:hasOffHandEnchant("Windfury Weapon")
    ```

---

> ## glyph

#### Parameters

-   `SPELL`: The name or ID of the spell to check for in the player's glyph sockets.

#### Returns `BOOL`

-   `true` if the player has a glyph socketed that matches the given spell, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "glyph(Glyph of Stars)"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("glyph")(_, "Glyph of Stars")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Glyph("Glyph of Stars")
    ```

---

> ## mainHand.Charges

-   This condition checks the number of charges for the player's main hand weapon.

#### Returns `NUMBER`

-   The number of charges for the player's main hand weapon.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "mainHand.Charges > 0"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("mainHand.Charges")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:MainHandCharges() > 0
    ```

---

> ## offHand.Charges

-   This condition checks the number of charges for the player's off hand weapon.

#### Returns `NUMBER`

-   The number of charges for the player's off hand weapon.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "offHand.Charges > 0"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("offHand.Charges")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:OffHandCharges() > 0
    ```

---

> ## mainHand.EnchantID

-   This condition checks the enchant ID for the player's main hand weapon.

#### Returns `NUMBER`

-   The enchant ID for the player's main hand weapon.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "mainHand.EnchantID > 0"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("mainHand.EnchantID")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:MainHandEnchantID() > 0
    ```

---

> ## offHand.EnchantID

-   This condition checks the enchant ID for the player's off hand weapon.

#### Returns `NUMBER`

-   The enchant ID for the player's off hand weapon.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "offHand.EnchantID > 0"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("offHand.EnchantID")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:OffHandEnchantID() > 0
    ```
