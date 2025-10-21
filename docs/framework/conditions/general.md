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
-   `UI_KEY` (optional): The name of the UI element. Defaults to the current combat routine's name.

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
    {ACTION, "ui(some_other_key, MyOtherUI)" },
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("ui")(_, "ashamane_key")
    _A.DSL:Get("ui")(_, "some_other_key,MyOtherUI")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Ui("ashamane_key")
    PLAYER:Ui("some_other_key,MyOtherUI")
    ```

---

> ## timetomax

#### Parameters

-   `UNIT`: The unit to check. Defaults to `"player"` if not specified.

#### Returns `NUMBER`

-   The time in seconds it will take for the unit's primary resource (e.g., Mana, Rage, Energy) to reach its maximum value, based on current regeneration rate.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "timetomax < 5"},
    {ACTION, "target.timetomax > 2"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("timetomax")() < 5
    _A.DSL:Get("timetomax")("target") > 2
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Timetomax() < 5
    TARGET:Timetomax() > 2
    ```

---

> ## gcd

-   This condition calculates the Global Cooldown (GCD) duration for the player's class.
-   **Note:** The provided code registers `GCDRemains`, which returns the time *remaining* on the GCD, not its total duration. The documentation below reflects the actual `GCDRemains` function.

#### Returns `NUMBER`

-   The time remaining on the GCD in seconds. Returns `0` if GCD is not active.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "gcd <= 0.1"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("GCDRemains")() <= 0.1
    ```

=== "Lua Mode"

    ```lua
    PLAYER:GCDRemains() <= 0.1
    ```

---

> ## interruptible

#### Parameters

-   `UNIT`: The unit to check.

#### Returns `BOOL`

-   `true` if the unit is currently casting or channeling a spell that can be interrupted, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.interruptible"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("interruptible")("target")
    ```

=== "Lua Mode"

    ```lua
    TARGET:Interruptible()
    ```

---

> ## castid

#### Parameters

-   `UNIT`: The unit to check.

#### Returns `NUMBER`

-   The spell ID of the spell the unit is currently casting. Returns `0` if not casting.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.castid == 133"}, -- e.g., "Fireball"
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("castid")("target") == 133
    ```

=== "Lua Mode"

    ```lua
    TARGET:Castid() == 133
    ```

---

> ## channelid

#### Parameters

-   `UNIT`: The unit to check.

#### Returns `NUMBER`

-   The spell ID of the spell the unit is currently channeling. Returns `0` if not channeling.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.channelid == 5143"}, -- e.g., "Arcane Missiles"
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("channelid")("target") == 5143
    ```

=== "Lua Mode"

    ```lua
    TARGET:Channelid() == 5143
    ```

---

> ## castTargetKEY

#### Parameters

-   `UNIT`: The unit whose cast target is being checked.

#### Returns `STRING`

-   A key or pointer identifying the target of the unit's current cast or channel. Returns `nil` if not casting/channeling or no specific target.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.castTargetKEY == some_pointer_value"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("castTargetKEY")("target") == some_pointer_value
    ```

=== "Lua Mode"

    ```lua
    TARGET:CastTargetKEY() == some_pointer_value
    ```

---

> ## castTargetGUID

#### Parameters

-   `UNIT`: The unit whose cast target is being checked.

#### Returns `STRING`

-   The GUID (Globally Unique Identifier) of the target of the unit's current cast or channel. Returns `nil` if not casting/channeling or no specific target.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.castTargetGUID == PlayerGUID"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("castTargetGUID")("target") == PlayerGUID
    ```

=== "Lua Mode"

    ```lua
    TARGET:CastTargetGUID() == PlayerGUID
    ```

---

> ## iscasting.any.spell
>
> _`iscasting.any.spell || isCastingAny`_

#### Parameters

-   `UNIT`: The unit to check for casting or channeling.

#### Returns `BOOL`

-   `true` if the specified unit is currently casting or channeling a spell, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.isCastingAny"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("isCastingAny")("target")
    ```

=== "Lua Mode"

    ```lua
    TARGET:IsCastingAnySpell()
    ```

---

> ## iscasting

#### Parameters

-   `UNIT`: The unit to check for casting.
-   `NameOrID`: The name or ID of the spell to check against.

#### Returns `BOOL`

-   `true` if the specified unit is currently casting the specified spell, `false` otherwise. This does not check for channeling.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.iscasting(Regrowth)", target},
    {ACTION, "target.iscasting(740)", target}, -- (1)!
    ```

    1. Tranquility

=== "Lua Code"

    ```lua
    _A.DSL:Get("isCasting")("target", "Regrowth")
    _A.DSL:Get("isCasting")("target", "740") -- (1)!
    ```

    1. Tranquility

=== "Lua Mode"

    ```lua
    TARGET:Iscasting("Regrowth")
    TARGET:Iscasting(740) -- (1)!
    ```

    1. Tranquility

---

> ## ischanneling

#### Parameters

-   `UNIT`: The unit to check for channeling.
-   `NameOrID`: The name or ID of the spell to check against.

#### Returns `BOOL`

-   `true` if the specified unit is currently channeling the specified spell, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.ischanneling(Arcane Missiles)", target},
    {ACTION, "target.ischanneling(5143)", target}, -- (1)!
    ```

    1. Arcane Missiles

=== "Lua Code"

    ```lua
    _A.DSL:Get("isChanneling")("target", "Arcane Missiles")
    _A.DSL:Get("isChanneling")("target", "5143") -- (1)!
    ```

    1. Arcane Missiles

=== "Lua Mode"

    ```lua
    TARGET:Ischanneling("Arcane Missiles")
    TARGET:Ischanneling(5143) -- (1)!
    ```

    1. Arcane Missiles

---

> ## iscasting.on.me
>
> _`iscasting.on.me || isCastingOnMe`_

#### Parameters

-   `UNIT`: The unit to check for casting or channeling.

#### Returns `BOOL`

-   `true` if the specified unit is casting or channeling a spell targeted at the player, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.isCastingOnMe", target},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("isCastingOnMe")("target")
    ```

=== "Lua Mode"

    ```lua
    TARGET:IscastingOnMe()
    ```

---

> ## casting.percent

#### Parameters

-   `UNIT`: The unit to check for casting or channeling.

#### Returns `NUMBER`

-   The percentage of completion for the current cast or channel. Returns `0` if not casting or channeling.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.casting.percent >= 60", target},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("casting.percent")("target") >= 60
    ```

=== "Lua Mode"

    ```lua
    TARGET:CastingPercent() >= 60
    ```

---

> ## channeling.percent

#### Parameters

-   `UNIT`: The unit to check for channeling.

#### Returns `NUMBER`

-   The percentage of completion for the current channel. Returns `0` if not channeling.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.channeling.percent >= 60", target},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("channeling.percent")("target") >= 60
    ```

=== "Lua Mode"

    ```lua
    TARGET:ChannelingPercent() >= 60
    ```

---

> ## casting.delta

#### Parameters

-   `UNIT`: The unit to check for casting or channeling.

#### Returns `NUMBER`, `NUMBER`, `BOOL`, `BOOL`

-   1st - The time remaining for the current cast/channel in seconds.
-   2nd - The total cast/channel time in seconds.
-   3rd - `true` if the ability is being channeled, `false` if it's a cast.
-   4th - `true` if the spell is not interruptible, `false` otherwise.
-   Returns `0` for all values if not casting or channeling.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.casting.delta < 0.5", target},
    ```

=== "Lua Code"

    ```lua
    local remaining, total, ischanneled, notInterruptible = _A.DSL:Get("casting.delta")("target")
    ```

=== "Lua Mode"

    ```lua
    local remaining, total, ischanneled, notInterruptible = TARGET:CastingDelta()
    ```

---

> ## casting.length

#### Parameters

-   `UNIT`: The unit to check for casting or channeling.

#### Returns `NUMBER`

-   The length (duration) of the current cast or channel in seconds. Returns `0` if not casting or channeling.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.casting.length > 1.5", target},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("casting.length")("target") > 1.5
    ```

=== "Lua Mode"

    ```lua
    TARGET:CastingLength() > 1.5
    ```

---

> ## casting.remaining

#### Parameters

-   `UNIT`: The unit to check for casting or channeling.

#### Returns `NUMBER`

-   The remaining time in seconds for the current cast or channel. Returns `999` if not currently casting or channeling.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.casting.remaining < 0.5", target},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("casting.remaining")("target") < 0.5
    ```

=== "Lua Mode"

    ```lua
    TARGET:CastingRemaining() < 0.5
    ```

---

> ## casting

This condition checks if a unit is currently casting a specific spell.

#### Parameters

-   `UNIT`: The unit to check for casting.
-   `SPELL`: The spell to check if the unit is casting.

#### Returns `BOOL`

-   `true` if the unit is casting the specified spell, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.casting(Regrowth)", target},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("casting")("target", "Regrowth")
    ```

=== "Lua Mode"

    ```lua
    TARGET:Casting("Regrowth")
    ```

---

> ## channeling

This condition checks if a unit is currently channeling a specific spell.

#### Parameters

-   `UNIT`: The unit to check for channeling.
-   `SPELL`: The spell to check if the unit is channeling.

#### Returns `BOOL`

-   `true` if the unit is channeling the specified spell, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.channeling(Arcane Missiles)", target},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("channeling")("target", "Arcane Missiles")
    ```

=== "Lua Mode"

    ```lua
    TARGET:Channeling("Arcane Missiles")
    ```

---

> ## interruptAt

#### Parameters

-   `UNIT`: The unit whose casting to evaluate for interruption.
-   `PERCENTAGE` (optional): The percentage threshold to interrupt the cast (default: 35, with a random variance of -5 to +5). For channeled spells, the threshold is effectively 30%.

#### Returns `BOOL`

-   `true` if the cast/channel has passed the specified percentage threshold and is interruptible, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.interruptAt(60)", target},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("interruptAt")("target", "60")
    ```

=== "Lua Mode"

    ```lua
    TARGET:InterruptAt(60)
    ```

---

> ## stunAt

#### Parameters

-   `UNIT`: The unit whose casting to evaluate for stunning.
-   `PERCENTAGE` (optional): The percentage threshold to stun the cast (default: 35, with a random variance of -5 to +5). For channeled spells, the threshold is effectively 30%.

#### Returns `BOOL`

-   `true` if the cast/channel has passed the specified percentage threshold, `false` otherwise. This does not check if the spell is interruptible.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.stunAt(60)", target},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("stunAt")("target", "60")
    ```

=== "Lua Mode"

    ```lua
    TARGET:StunAt(60)
    ```

---

> ## custom.interrupts

-   This condition checks if a custom interrupt action is defined (in the plugin's custom tables) for the spell the target is currently casting.

#### Parameters

-   `UNIT`: The unit whose casting to evaluate for a custom interrupt.

#### Returns `BOOL`

-   `true` if a custom interrupt action is defined for the currently casting spell, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.custom.interrupts", target},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("custom.interrupts")("target")
    ```

=== "Lua Mode"

    ```lua
    TARGET:CustomInterrupts()
    ```

---

> ## custom.stuns

-   This condition checks if a custom stun action is defined (in the plugin's custom tables) for the spell the target is currently casting.

#### Parameters

-   `UNIT`: The unit whose casting to evaluate for a custom stun.

#### Returns `BOOL`

-   `true` if a custom stun action is defined for the currently casting spell, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.custom.stuns", target},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("custom.stuns")("target")
    ```

=== "Lua Mode"

    ```lua
    TARGET:CustomStuns()
    ```

---

> ## custom.cc

-   This condition checks if the unit has any debuff listed in the custom crowd control (CC) table (defined in the plugin).

#### Parameters

-   `UNIT`: The unit to check for custom CC debuffs.

#### Returns `BOOL`

-   `true` if a custom CC debuff is present on the unit, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.custom.cc", target},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("custom.cc")("target")
    ```

=== "Lua Mode"

    ```lua
    TARGET:CustomCc()
    ```

---

> ## custom.dispels

-   This condition checks if the unit has any dispellable debuff listed in the custom dispels table (defined in the plugin).

#### Parameters

-   `UNIT`: The unit to check for custom dispellable debuffs.

#### Returns `BOOL`

-   `true` if a custom dispellable debuff is present on the unit, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.custom.dispels", target},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("custom.dispels")("target")
    ```

=== "Lua Mode"

    ```lua
    TARGET:CustomDispels()
    ```

---

> ## custom.purges

-   This condition checks if the unit has any purgable buff listed in the custom purges table (defined in the plugin).

#### Parameters

-   `UNIT`: The unit to check for custom purgable buffs.

#### Returns `BOOL`

-   `true` if a custom purgable buff is present on the unit, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.custom.purges", target},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("custom.purges")("target")
    ```

=== "Lua Mode"

    ```lua
    TARGET:CustomPurges()
    ```

---

> ## isnear

#### Parameters

-   `UNIT`: The unit to check distance from (typically `"player"`).
-   `ARGS`: A string containing `TARGET_ID,DISTANCE`.
    -   `TARGET_ID`: The NPC ID of the target unit to check proximity to.
    -   `DISTANCE`: The maximum distance in yards to be considered "near".

#### Returns `BOOL`

-   `true` if an enemy unit with the specified `TARGET_ID` is found within `DISTANCE` yards of the first `UNIT`, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "isnear(12345, 30)"}, -- Check if an enemy with ID 12345 is within 30 yards of the player.
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("isnear")(_, "12345,30")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Isnear("12345,30")
    ```

---

> ## bagSpace

#### Returns `NUMBER`

-   The total number of free bag slots across all bags.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "bagSpace > 0"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("bagSpace")() > 0
    ```

=== "Lua Mode"

    ```lua
    PLAYER:BagSpace() > 0
    ```

---

> ## timeout
>
> _`timeout || to`_

#### Parameters

-   `UNIT`: The unit this timeout is associated with. Can be a unit ID or GUID.
-   `NAME_XTIME`: A string containing `NAME,XTIME`.
    -   `NAME`: A unique identifier for this specific timeout.
    -   `XTIME`: The time in seconds the timeout will remain active.

#### Returns `BOOL`

-   `true` when first called or while the timeout is active (i.e., less than `XTIME` seconds have passed). Returns `false` once `XTIME` seconds have elapsed since the first call with the given `UNIT` and `NAME`. After returning `false`, the timeout is reset.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.to(bloodlust_window, 40)", target}, -- Will be true for 40s after first use, then false.
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("timeout")("target", "bloodlust_window,40")
    ```

=== "Lua Mode"

    ```lua
    TARGET:Timeout("bloodlust_window,40")
    ```

---

> ## frame.visible

#### Parameters

-   `NAME`: The name of the UI frame to check.

#### Returns `BOOL`

-   `true` if a UI frame with the given `NAME` exists, is of type table, its name matches `NAME`, and it is currently shown (`IsShown()` returns true). `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "frame.visible(MyCustomFrame)"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("frame.visible")(_, "MyCustomFrame")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:FrameVisible("MyCustomFrame")
    ```

---

> ## spell.AutocastEnabled

#### Parameters

-   `SPELL`: The name or ID of the spell to check.

#### Returns `BOOL`

-   `true` if the spell is auto-castable and auto-cast is currently enabled for that spell, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "spell.AutocastEnabled(Arcane Intellect)"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spell.AutocastEnabled")(_, "Arcane Intellect")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:SpellAutocastEnabled("Arcane Intellect")
