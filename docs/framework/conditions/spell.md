# SPELL

---

> ## spell.cooldown

#### Parameters

-   `SPELL`: The name or ID of the spell to check the cooldown for.

#### Returns `NUMBER`

-   The remaining cooldown time in `seconds` for the specified spell.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "spell(Nature's Cure).cooldown < 1"},

-- in Lua code
_A.DSL:Get("spell.cooldown")(_, "Nature's Cure") < 1

-- Lua Mode
PLAYER:SpellCooldown("Nature's Cure") < 1
```

---

> ## spell.recharge

#### Parameters

-   `SPELL`: The name or ID of the spell to check the recharge for.

#### Returns `NUMBER`

-   The remaining recharge time in `seconds` for the specified spell.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "spell(Nature's Cure).recharge < 1"},

-- in Lua code
_A.DSL:Get("spell.recharge")(_, "Nature's Cure") < 1

-- Lua Mode
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

```lua
-- DSL Mode
{ACTION, "spell(Heroic Leap).charges > 1"},

-- in Lua code
_A.DSL:Get("spell.charges")(_, "Heroic Leap") > 1

-- Lua Mode
PLAYER:SpellCharges("Heroic Leap") > 1
```

---

> ## spell.count

#### Parameters

-   `SPELL`: The name or ID of the spell to count.

#### Returns `NUMBER`

-   The number of times a spell can be casted.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "spell(Starfire).count == 2"},

-- in Lua code
_A.DSL:Get("spell.count")(_, "Starfire") == 1

-- Lua Mode
PLAYER:SpellCount("Starfire") == 1
```

---

> ## spell.usable

#### Parameters

-   `SPELL`: The name or ID of the spell to check the usability for.

#### Returns `BOOL`

-   `true` if the specified spell is usable, `false` otherwise.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "spell(Swiftmend).usable"},

-- in Lua code
_A.DSL:Get("spell.usable")(_, "Swiftmend")

-- Lua Mode
PLAYER:SpellUsable("Swiftmend")
```

---

> ## spell.exists

#### Parameters

-   `SPELL`: The name or ID of the spell to check for existence.

#### Returns `BOOL`

-   `true` if the specified spell exists in the player's spellbook, `false` otherwise.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "spell(Flourish).exists"},

-- in Lua code
_A.DSL:Get("spell.exists")(_, "Flourish")

-- Lua Mode
PLAYER:SpellExists("Flourish")
```

---

> ## spell.ready

#### Parameters

-   `SPELL`: The name or ID of the spell to check for readiness.It considers the spell's cooldown, global cooldown, and network latency.

#### Returns `BOOL`

-   `true` if the specified spell is ready for use, `false` otherwise.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "spell(Renewal).ready"},

-- in Lua code
_A.DSL:Get("spell.ready")(_, "Renewal")

-- Lua Mode
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

```lua
-- DSL Mode
{ACTION, "UNIT.spell(Aimed Shot).range", UNIT},

-- in Lua code
_A.DSL:Get("spell.range")("UNIT", "Aimed Shot")

-- Lua Mode
UNIT:SpellRange("Aimed Shot")
```

---

> ## spell.cost

#### Parameters

-   `SPELL`: The name or ID of the spell to retrieve costs for.

#### Returns `NUMBER`

-   The amount of `"MANA", "RAGE", "FOCUS", "ENERGY", "HAPPINESS", "RUNES", "RUNIC_POWER", "SOUL_SHARDS", "HOLY_POWER", "STAGGER", "CHI", "FURY", "PAIN", "LUNAR_POWER", "INSANITY"` required to cast the spell.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "spell(Ignore Pain).cost >= 50"},

-- in Lua code
_A.DSL:Get("spell.cost")(_, "Ignore Pain") >= 50

-- Lua Mode
PLAYER:SpellCost("Ignore Pain") >= 50
```

---

> ## spell.casttime

#### Parameters

-   `SPELL`: The name or ID of the spell to retrieve the cast time for.

#### Returns `NUMBER`

-   The cast time of the spell in `seconds`.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "spell(Aimed Shot).casttime < 0.9"},

-- in Lua code
_A.DSL:Get("spell.casttime")(_, "Aimed Shot") < 0.9

-- Lua Mode
PLAYER:SpellCasttime("Aimed Shot") < 0.9
```

---

> ## spell.proc

-   This condition checks if a specified spell is currently active as a proc.

#### Parameters

-   `SPELL`: The name or ID of the spell to check for as a proc.

#### Returns `BOOL`

-   `true` if the spell is currently active as a proc, `false` otherwise.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "spell(Ferocious Bite).proc"},

-- in Lua code
_A.DSL:Get("spell.proc")(_, "Ferocious Bite")

-- Lua Mode
PLAYER:SpellProc("Ferocious Bite")
```

---

> ## enchanted.mainhand

-   This condition checks if the player's main-hand weapon has an enchantment.

#### Returns `BOOL`

-   `true` if the player's main-hand weapon has an enchantment, `false` otherwise.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "enchanted.mainhand"},

-- in Lua code
_A.DSL:Get("enchanted.mainhand")()

-- Lua Mode
PLAYER:EnchantedMainhand()
```

---

> ## enchanted.offhand

-   This condition checks if the player's off-handweapon has an enchantment.

#### Returns `BOOL`

-   `true` if the player's off-hand weapon has an enchantment, `false` otherwise.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "enchanted.offhand"},

-- in Lua code
_A.DSL:Get("enchanted.offhand")()

-- Lua Mode
PLAYER:EnchantedOffhand()
```

---

> ## hasMainHandEnchant

-   This condition checks if the main hand weapon is enchanted with a specific spell.

#### Parameters

-   `SPELL`: The name or ID of the spell to check for on the main hand weapon enchant.

#### Returns BOOL

-   `true` if main hand weapon is enchanted with the spell, false otherwise.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "hasMainHandEnchant(Flametongue Weapon)"},

-- in Lua code
_A.DSL:Get("hasMainHandEnchant")(_, "Flametongue Weapon")

-- Lua Mode
PLAYER:hasMainHandEnchant("Flametongue Weapon")
```

---

> ## hasOffHandEnchant

-   This condition checks if the off hand weapon is enchanted with a specific spell.

#### Parameters

-   `SPELL`: The name or ID of the spell to check for on the off hand weapon enchant.

#### Returns BOOL

-   `true` if off hand weapon is enchanted with the spell, false otherwise.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "hasOffHandEnchant(Windfury Weapon)"},

-- in Lua code
_A.DSL:Get("hasOffHandEnchant")(_, "Windfury Weapon")

-- Lua Mode
PLAYER:hasOffHandEnchant("Windfury Weapon")
```

---

> ## glyph

#### Parameters

-   `SPELL`: The name or ID of the spell to check for in the player's glyph sockets.

#### Returns `BOOL`

-   `true` if the player has a glyph socketed that matches the given spell, `false` otherwise.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "glyph(Glyph of Stars)"},

-- in Lua code
_A.DSL:Get("glyph")(_, "Glyph of Stars")

-- Lua Mode
PLAYER:Glyph("Glyph of Stars")
```

---
