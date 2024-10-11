# GENERAL

---

> ## toggle

#### Parameters

-   `NAME`: The name of the toggle setting to check.

#### Returns `BOOL`

-   `true` if the toggle is enabled, `false` otherwise.

    `"MasterToggle", "Interrupts", "Cooldowns", "AoE"` and `"custom_toggles"`.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "toggle(AoE)"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("toggle")(_, "AoE")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Toggle("AoE")
    ```

---

> ## ui

#### Parameters

-   `KEY`: The name of the key in the GUI configuration to check.

#### Returns `BOOL` or `STRING` or `NUMBER`

-   The value associated with the provided key in the GUI configuration.

#### _Example:_

```lua
local GUI = {
    ...
    {type = "checkbox",	text = "Ashamane's Frenzy", key = "ashamane_key", default = true},
    ...
```

=== "DSL"

    ```lua
    {ACTION, "ui(ashamane_key)" },
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("ui")(_, "ashamane_key")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Ui("ashamane_key")
    ```

---

> ## gcd

-   This condition calculates the Global Cooldown (GCD) duration for the player's class.

#### Returns `NUMBER`

-   The GCD duration in seconds.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "gcd <= 1"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("gcd")() <= 1
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Gcd() <= 1
    ```

---

> ## iscasting.any.spell
>
> _`iscasting.any.spell || iscastingany`_

#### Parameters

-   `UNIT`: The unit to check for casting or channeling.

#### Returns `BOOL`

-   `true` if the specified unit is currently casting or channeling a spell, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.iscastingany", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("iscastingany")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IscastingAnySpell()
    ```

---

> ## iscasting

#### Parameters

-   `UNIT`: The unit to check for casting or channeling.
-   `NameOrID`: The name or ID of the spell to check against.

#### Returns `BOOL`

-   `true` if the specified unit is casting or channeling the specified spell, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.iscasting(Regrowth)", UNIT},
    {ACTION, "UNIT.iscasting(740)", UNIT}, -- (1)!
    ```

    1. Tranquility

=== "Lua Code"

    ```lua
    _A.DSL:Get("iscasting")("UNIT", "Regrowth")
    _A.DSL:Get("iscasting")("UNIT", "740") -- (1)!
    ```

    1. Tranquility

=== "Lua Mode"

    ```lua
    UNIT:Iscasting("Regrowth")
    UNIT:Iscasting(740) -- (1)!
    ```

    1. Tranquility

---

> ## iscasting.on.me
>
> _`iscasting.on.me || isastingonme`_

#### Parameters

-   `UNIT`: The unit to check for casting or channeling.

#### Returns `BOOL`

-   `true` if the specified unit is casting or channeling a spell on the player, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.isastingonme", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("isastingonme")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:IscastingOnMe()
    ```

---

> ## casting.percent

#### Parameters

-   `UNIT`: The unit to check for casting.

#### Returns `NUMBER`

-   The percentage of completion for the casting ability.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.casting.percent >= 60", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("casting.percent")("UNIT") >= 60
    ```

=== "Lua Mode"

    ```lua
    UNIT:CastingPercent() >= 60
    ```

---

> ## channeling.percent

#### Parameters

-   `UNIT`: The unit to check for channeling.

#### Returns `NUMBER`

-   The percentage of completion for the channeling ability.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.channeling.percent >= 60", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("channeling.percent")("UNIT") >= 60
    ```

=== "Lua Mode"

    ```lua
    UNIT:ChannelingPercent() >= 60
    ```

---

> ## casting.delta

#### Parameters

-   `UNIT`: The unit to check for casting.

#### Returns `NUMBER`, `NUMBER`, `BOOL`

-   1st - The time remaining for the current cast in `seconds`.
-   2nd - The total cast time in `seconds`.
-   3rd - `true`if the ability is being channeled, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.casting.delta < 0.5", UNIT},
    ```

=== "Lua Code"

    ```lua
    local remaining, total, ischanneled = _A.DSL:Get("casting.delta")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    local remaining, total, ischanneled = UNIT:CastingDelta()
    ```

---

> ## casting.length

#### Parameters

-   `UNIT`: The unit to check for casting.

#### Returns `NUMBER`

-   The length (duration) of the current cast in `seconds`.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.casting.length > 1.5", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("casting.length")("UNIT") > 1.5
    ```

=== "Lua Mode"

    ```lua
    UNIT:CastingLength() > 1.5
    ```

---

> ## casting.remaining

#### Parameters

-   `UNIT`: The unit to check for casting.

#### Returns `NUMBER`

-   The remaining time in `seconds` for the current cast, returns `999` if not currently casting.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.casting.remaining < 0.5", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("casting.remaining")("UNIT") < 0.5
    ```

=== "Lua Mode"

    ```lua
    UNIT:CastingRemaining() < 0.5
    ```

---

> ## casting

This condition checks(using the `Wow api`) if a unit is currently casting a specific spell.

#### Parameters

-   `UNIT`: The unit to check for casting.
-   `SPELL`: The spell to check if the unit is casting.

#### Returns `BOOL`

-   `true` if the unit is casting the specified spell, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.casting(Regrowth)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("casting")("UNIT", "Regrowth")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Casting("Regrowth")
    ```

---

> ## channeling

This condition checks(using the `Wow api`) if a unit is currently channeling a specific spell.

#### Parameters

-   `UNIT`: The unit to check for channeling.
-   `SPELL`: The spell to check if the unit is channeling.

#### Returns `BOOL`

-   `true` if the unit is channeling the specified spell, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.channeling(Regrowth)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("channeling")("UNIT", "Regrowth")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Channeling("Regrowth")
    ```

---

> ## interruptat

#### Parameters

-   `UNIT`: The unit whose casting to evaluate for interruption.
-   `PERCENTAGE`: The percentage threshold to interrupt the cast (default: 35).

#### Returns `BOOL`

-   `true` if it's a good time to interrupt the cast, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.interruptat(60)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("interruptat")("UNIT", "60")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Interruptat(60)
    ```

---

> ## custom.interrupts

-   This condition checks if a custom stun action is defined(`in the plugin`) for the currently casting spell.

#### Parameters

-   `UNIT`: The unit whose casting to evaluate for custom interrupt.

#### Returns `BOOL`

-   `true` if a custom interrupt action is defined for the currently casting spell, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.custom.interrupts", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("custom.interrupts")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:CustomInterrupts()
    ```

---

> ## custom.stuns

-   This condition checks if a custom stun action is defined(`in the plugin`) for the currently casting spell.

#### Parameters

-   `UNIT`: The unit whose casting to evaluate for custom stun.

#### Returns `BOOL`

-   `true` if a custom stun action is defined for the currently casting spell, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.custom.stuns", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("custom.stuns")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:CustomStuns()
    ```

---

> ## custom.cc

-   This condition checks if a custom cc action is defined(`in the plugin`) for the currently casting spell.

#### Parameters

-   `UNIT`: The unit whose casting to evaluate for custom cc.

#### Returns `BOOL`

-   `true` if a custom cc action is defined for the currently casting spell, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.custom.cc", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("custom.cc")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:CustomCc()
    ```

---

> ## custom.dispels

-   This condition checks if a custom dispellable buffs/debuff is present on the unit. (`in the plugin`)

#### Parameters

-   `UNIT`: The unit to check for custom dispellable buffs/debuffs.

#### Returns `BOOL`

-   `true` if a custom dispellable buff/debuff is present on the unit, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.custom.dispels", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("custom.dispels")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:CustomDispels()
    ```

---

> ## custom.purges

-   This condition checks if a custom purgable buffs/debuff is present on the unit. (`in the plugin`)

#### Parameters

-   `UNIT`: The unit to check for custom purgable buffs/debuffs.

#### Returns `BOOL`

-   `true` if a custom purgable buff/debuff is present on the unit, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.custom.purges", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("custom.purges")("UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:CustomPurges()
    ```
