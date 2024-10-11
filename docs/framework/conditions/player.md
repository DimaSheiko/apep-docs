# PLAYER

---

> ## group.members
>
> _`group.members || num.members`_

#### Returns `NUMBER`

-   The number of members in the player's group.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "num.members"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("num.members")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:NumMembers()
    ```

---

> ## issolo

#### Returns `BOOL`

-   `true` if the player is not in a group, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "issolo"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("issolo")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Issolo()
    ```

---

> ## isparty

#### Returns `BOOL`

-   `true` if the player is in a party group, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "isparty"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("isparty")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Isparty()
    ```

---

> ## israid

#### Returns `BOOL`

-   `true` if the player is in a raid group, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "israid"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("israid")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Israid()
    ```

---

> ## group.type

#### Returns `NUMBER`

-   1 if solo, 2 if party, 3 if raid.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "group.type==1"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("group.type")() == 1
    ```

=== "Lua Mode"

    ```lua
    PLAYER:GroupType() == 1
    ```

---

> ## auto.attack
>
> _`auto.attack || auto.shoot`_

-   This condition checks if the player's character is performing an auto-attack or auto-shoot (for hunters).

#### Returns `BOOL`

-   `true` if the character is auto-attacking or auto-shooting, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "auto.attack"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("auto.attack")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:AutoAttack()
    ```

---

> ## swimming

-   This condition checks if the player character is currently swimming.

#### Returns `BOOL`

-   `true` if the player character is swimming, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "swimming"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("swimming")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Swimming()
    ```

---

> ## falling

-   This condition checks if the player character is currently falling.

#### Returns `BOOL`

-   `true` if the player character is falling, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "falling"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("falling")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Falling()
    ```

---

> ## falling.duration

-   This condition provides the duration for which the player character has been falling.

#### Returns `NUMBER`

-   The duration (in `seconds`) for which the player character has been falling.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "falling.duration > 1.5"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("falling.duration")() > 1.5
    ```

=== "Lua Mode"

    ```lua
    PLAYER:FallingDuration() > 1.5
    ```

---

> ## indoors

-   This condition checks if the player character is currently indoors.

#### Returns `BOOL`

-   `true` if the player character is indoors, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "indoors"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("indoors")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Indoors()
    ```

---

> ## mounted

-   This condition checks if the player character is currently mounted.

#### Returns `BOOL`

-   `true` if the player character is mounted, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "mounted"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("mounted")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Mounted()
    ```

---

> ## outcombat.time

-   This condition provides the time duration for which the player character has been out of combat.

#### Returns `NUMBER`

-   The time duration in `seconds` for which the player character has been out of combat.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "outcombat.time > 10"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("outcombat.time")() > 10
    ```

=== "Lua Mode"

    ```lua
    PLAYER:OutcombatTime() > 10
    ```

---

> ## lost.control

-   This condition checks if the player is currently under the effect of any of the control states:
    `stunned`, `sapped`, `disoriented`, `polymorphed`, `incapacitated`, `feared`, `horrified`,
    `fleeing`, `intimidated`, `asleep`, `charmed`, `banished`, `silenced`, `paralyzed`.

#### Returns `BOOL`

-   `true` if the player is in any control states, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "lost.control"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("lost.control")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:LostControl()
    ```

---

> ## out.of.control

-   This condition checks if the player is currently in any of the specified loss of control states:
    `stunned`, `sapped`, `disoriented`, `polymorphed`, `incapacitated`, `feared`, `horrified`,
    `fleeing`, `intimidated`, `asleep`, `charmed`, `banished`, `silenced`, `paralyzed`.

#### Parameters

-   `STATE(s)`: A string containing one or more loss of control states separated by '||'.

#### Returns `BOOL`

-   `true` if the player is in any of the specified loss of control states, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "out.of.control(feared || incapacitate)"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("out.of.control")(_, "feared || incapacitate")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:OutOfControl("feared || incapacitate")
    ```

---

> ## lastcast

-   This condition checks if the last cast performed by the player matches the specified spell.

#### Parameters

-   `SPELL`: The name or ID of the spell to compare with the last cast.

#### Returns `BOOL`

-   `true` if the last cast matches the specified spell, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "lastcast(Vendeta)"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("lastcast")(_, "Vendeta")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Lastcast("Vendeta")
    ```

---

> ## lasttarget

-   This condition checks if the provided unit matches the last target that was used by the player.

#### Parameters

-   `UNIT`: The unit identifier to compare with the last target.

#### Returns `BOOL`

-   `true` if the provided unit matches the last target used by the player, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.lasttarget"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("lasttarget")(_, "UNIT")
    ```

=== "Lua Mode"

    ```lua
    UNIT:lasttarget()
    ```

---

> ## lastcast.succeed

-   This condition checks if the last casted spell by the player succeeded and matches the specified spell.

#### Parameters

-   `SPELL`: The name or ID of the spell to compare with the last cast.

#### Returns `BOOL`

-   `true` if the last casted spell succeeded and matches the specified spell, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "lastcast(Battle Cry).succeed"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("lastcast.succeed")(_, "Battle Cry")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:LastcastSucceed("Battle Cry")
    ```

---

> ## prev.gcd
>
> _`prev.gcd || lastcast.gcd`_

-   These conditions check if the provided spell at a given index matches the last spell cast by the player.
    The index parameter allows checking previous casts within a stored spell history.

#### Parameters

-   `SPELL_INDEX`: A combination of spell identifier or name and an index (optional) to specify a previous cast.

#### Returns `BOOL`

-   `true` if the provided spell at the specified index matches the last spell cast by the player, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "prev(Regrowth, 2).gcd"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("prev.gcd")(_, "Regrowth, 2")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:PrevGcd("Regrowth", 2)
    ```

---

> ## lastcast.seen
>
> _`lastcast.seen || lastcast.viewed`_

-   These conditions check how long ago the player last cast a specific spell.

#### Parameters

-   `SPELL`: The name or ID of the spell to check for in the player's cast history.

#### Returns `NUMBER`

-   The time in `seconds` since the player last cast the specified spell, or `9999` if not found.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "lastcast(Aimed Shot).seen"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("lastcast.seen")(_, "Aimed Shot")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:LastcastSeen("Aimed Shot")
    ```

---

> ## unitLastCast.succeed

-   This condition checks if the provided unit's last cast matches the specified spell.

#### Parameters

-   `UNIT`: The unit to check the last cast for.
-   `SPELL`: The spell identifier or name to compare with the unit's last cast.

#### Returns `BOOL`

-   `true` if the unit's last cast matches the specified spell, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.unitLastCast(Counterspell).succeed"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("unitLastCast.succeed")("UNIT", "Counterspell")
    ```

=== "Lua Mode"

    ```lua
    UNIT:UnitLastCastSucceed("Counterspell")
    ```

---

> ## lastcast.count

-   This condition checks if the provided spell was the last spell cast by the player,
    and returns the number of times that spell was cast consecutively.

#### Parameters

-   `SPELL`: The spell identifier or name to check.

#### Returns `NUMBER`

-   The number of consecutive casts of the provided spell, or `0` if not applicable.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "lastcast(Rejuvenation).count"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("lastcast.count")(_, "Rejuvenation")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:LastcastCount("Rejuvenation")
    ```

---

> ## sform
>
> _`sform || ShapeshiftForm`_

-   This condition retrieves the current shapeshift form ID for the player.

#### Returns `NUMBER`

-   The `ID` of the current shapeshift form, or `nil` if not applicable.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "sform=5"}, -- Bear Form
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("sform")() == 5
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Sform()==5
    ```

---

> ## has.form
>
> _`has.form || has.ShapeshiftForm`_

-   This condition checks if the player has a specific shapeshift form active.

#### Parameters

-   `STRING`: The name of the shapeshift form to check.

#### Returns `BOOL`

-   `true` if the player has the specified shapeshift form, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "has(Swift Flight Form).form"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("has.form")(_, "Swift Flight Form")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:HasForm("Swift Flight Form")
    ```

---

> ## spell.IsTargeting

-   This condition checks if the player is currently in the targeting mode for a spell.

#### Returns `BOOL`

-   `true` if the player is targeting for a spell, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "spell.IsTargeting"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("spell.IsTargeting")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:SpellIsTargeting()
    ```

---

> ## isStealthed

-   This condition checks if the player is currently in a stealthed state.

#### Returns `BOOL`

-   `true` if the player is in stealth, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "isStealthed"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("isStealthed")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:IsStealthed()
    ```

---

> ## isHavingLunch

-   This condition checks if the player has a lunch-related buff active.

#### Returns `BOOL`

-   `true` if the player has a lunch-related buff, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "isHavingLunch"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("isHavingLunch")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:IsHavingLunch()
    ```
