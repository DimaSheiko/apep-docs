# SPELL

---

> ## spell.cooldown
> _`spell.cooldown || spell.cd`_

#### Parameters

-   `SPELL`: The name or ID of the spell to check the cooldown for.

#### Returns `NUMBER`

-   The remaining cooldown time in `seconds` for the specified spell. Returns 0 if the spell is not on cooldown.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "spell(Nature's Cure).cooldown < 1"},
    {ACTION, "spell(Nature's Cure).cd < 1"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spell.cooldown")(_, "Nature's Cure") < 1
    _A.DSL:Get("spell.cd")(_, "Nature's Cure") < 1
    ```

=== "Lua Mode"

    ```lua
    PLAYER:SpellCooldown("Nature's Cure") < 1
    PLAYER:SpellCD("Nature's Cure") < 1
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

-   `SPELL`: The name or ID of the spell.

#### Returns `NUMBER`

-   The number of charges or stacks available for the spell (e.g., Arcane Missiles, Maelstrom Weapon). Returns 0 if the spell does not use this mechanic.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "spell(Arcane Missiles).count > 0"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spell.count")(_, "Arcane Missiles") > 0
    ```

=== "Lua Mode"

    ```lua
    PLAYER:SpellCount("Arcane Missiles") > 0
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

> ## IsCurrent.Spell
> _`IsCurrent.Spell || Current.Spell`_

#### Parameters

-   `SPELL`: The name or ID of the spell to check.

#### Returns `BOOL`

-   `true` if the specified spell is currently being cast, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "IsCurrent.Spell(Arcane Missiles)"},
    {ACTION, "Current.Spell(Arcane Missiles)"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("IsCurrent.Spell")(_, "Arcane Missiles")
    _A.DSL:Get("Current.Spell")(_, "Arcane Missiles")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:IsCurrentSpell("Arcane Missiles")
    PLAYER:CurrentSpell("Arcane Missiles")
    ```

---

> ## spell.ready

#### Parameters

-   `SPELL`: The name or ID of the spell to check for readiness.

#### Returns `BOOL`

-   `true` if the spell is not currently being cast, its cooldown is finished (or less than GCD), and it is usable (has resources, etc.), `false` otherwise.

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

-   `true` if the unit is within range of the spell, `false` otherwise. For spells with a melee range (0-0 yards), this condition will check if the unit is in melee range.

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

#### Returns `NUMBER, NUMBER`

-   `powerCost`: The amount of resource required to cast the spell.
-   `powerType`: The type of resource required (e.g., 0 for Mana, 1 for Rage, 3 for Energy).

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "spell(Ignore Pain).cost >= 50"},
    ```

=== "Lua Code"

    ```lua
    local cost, powerType = _A.DSL:Get("spell.cost")(_, "Ignore Pain")
    if cost >= 50 then
      -- do something
    end
    ```

=== "Lua Mode"

    ```lua
    local cost, powerType = PLAYER:SpellCost("Ignore Pain")
    if cost >= 50 then
      -- do something
    end
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

> ## spell.maxrange

#### Parameters

-   `SPELL`: The name or ID of the spell to retrieve the maximum range for.

#### Returns `NUMBER`

-   The maximum range of the spell in yards.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "spell(Fireball).maxrange > 30"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spell.maxrange")(_, "Fireball") > 30
    ```

=== "Lua Mode"

    ```lua
    PLAYER:SpellMaxrange("Fireball") > 30
    ```

---

> ## spell.minrange

#### Parameters

-   `SPELL`: The name or ID of the spell to retrieve the minimum range for.

#### Returns `NUMBER`

-   The minimum range of the spell in yards.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "spell(Fireball).minrange < 5"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spell.minrange")(_, "Fireball") < 5
    ```

=== "Lua Mode"

    ```lua
    PLAYER:SpellMinrange("Fireball") < 5
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
