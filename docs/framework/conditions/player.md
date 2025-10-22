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
> _`auto.attack || isattacking || auto.shoot`_

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
>
> _`mounted || ImMounted`_

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

> ## incombat.time

-   This condition provides the time duration for which the player character has been in combat.

#### Returns `NUMBER`

-   The time duration in `seconds` for which the player character has been in combat. Returns `0` if not in combat or time is not available.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "incombat.time > 5"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("incombat.time")() > 5
    ```

=== "Lua Mode"

    ```lua
    PLAYER:IncombatTime() > 5
    ```

---

> ## lost.control
>
> _`lost.control || player_lost_control`_

-   This condition checks if the player is currently under the effect of any loss of control.
    -   For WoW version 510 (MoP) and later, it checks against a predefined list of crowd control states: `stunned`, `sapped`, `disoriented`, `polymorphed`, `incapacitated`, `feared`, `horrified`, `fleeing`, `intimidated`, `asleep`, `charmed`, `banished`, `silenced`, `paralyzed`.
    -   For older WoW versions, it uses the native `HasFullControl()` function.

#### Returns `BOOL`

-   `true` if the player is in any loss of control state, otherwise `false`.

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

-   This condition checks if the player is currently in any of the specified loss of control states.
    -   **Note:** Only available for WoW version 510 (MoP) and later. This function relies on `C_LossOfControl` events.

#### Parameters

-   `STATE(s)`: A string containing one or more loss of control states (e.g., `stunned`, `feared`) separated by '||'.

#### Returns `BOOL`

-   `true` if the player is in any of the specified loss of control states, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "out.of.control(feared || incapacitated)"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("out.of.control")(_, "feared || incapacitated")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:OutOfControl("feared || incapacitated")
    ```

---

> ## out.of.control.delayed

-   This condition checks if the player was in any of the specified loss of control states after a short delay (0.7 to 1.7 seconds).
    -   **Note:** Only available for WoW version 510 (MoP) and later. This function relies on `C_LossOfControl` events and a timer.

#### Parameters

-   `STATE(s)`: A string containing one or more loss of control states (e.g., `stunned`, `feared`) separated by '||'.

#### Returns `BOOL`

-   `true` if the player was in any of the specified loss of control states when checked after the delay, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "out.of.control.delayed(stunned || silenced)"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("out.of.control.delayed")(_, "stunned || silenced")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:OutOfControlDelayed("stunned || silenced")
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

> ## lastfakeunit

-   This condition returns the last fake unit that was targeted or used by the player.

#### Returns `STRING`

-   The identifier of the last fake unit (e.g., "arena1", "party2"). May return an empty string or nil if no fake unit was recently used.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "lastfakeunit == 'arena1'"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("lastfakeunit")() == 'arena1'
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Lastfakeunit() == 'arena1'
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

-   These conditions check if the provided spell at a given index matches a previous spell cast by the player.
    The index parameter allows checking previous casts within a stored spell history (1 is the most recent, 2 is the one before, etc.).

#### Parameters

-   `SPELL_INDEX`: A string containing the spell identifier or name, followed by a comma and an index (e.g., `"Regrowth, 2"`).

#### Returns `BOOL`

-   `true` if the provided spell at the specified index matches a previous cast, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "prev.gcd(Regrowth, 2)"},
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
    {ACTION, "lastcast(Aimed Shot).seen < 3"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("lastcast.seen")(_, "Aimed Shot") < 3
    ```

=== "Lua Mode"

    ```lua
    PLAYER:LastcastSeen("Aimed Shot") < 3
    ```

---

> ## lastcast.succeed.on

-   This condition checks if a specific spell was the last successfully casted spell on a target.

#### Parameters

-   `TARGET`: The target unit identifier (e.g., any UnitId like `"player"`, `"target"`, etc., or a unit GUID).
-   `SPELL`: The spell name or spell ID.

#### Returns `BOOL`

-   `true` if the spell was the last successfully casted spell on the target, `false` otherwise.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "lastcast(Moonfire).succeed.on(target)"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("lastcast.succeed.on")("target", "Moonfire")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:LastcastSucceedOn("target", "Moonfire")
    ```

---

> ## lastcast.seen.on
>
> _`lastcast.seen.on || lastcast.viewed.on`_

-   This condition checks how much time has passed since a specific spell was last cast on a target.

#### Parameters

-   `TARGET`: The target unit identifier (e.g., any UnitId like `"player"`, `"target"`, etc., or a unit GUID).
-   `SPELL`: The spell name or spell ID.

#### Returns `NUMBER`

-   The time difference in seconds since the spell was last seen on the target, or `9999` if the spell was not found.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "lastcast(Polymorph).seen.on(target) < 3"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("lastcast.seen.on")("target", "Polymorph") < 3
    ```

=== "Lua Mode"

    ```lua
    PLAYER:LastcastSeenOn("target", "Polymorph") < 3
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
    {ACTION, "lastcast(Rejuvenation).count >= 2"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("lastcast.count")(_, "Rejuvenation") >= 2
    ```

=== "Lua Mode"

    ```lua
    PLAYER:LastcastCount("Rejuvenation") >= 2
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
    {ACTION, "sform=5"}, -- (1)!
    ```

    1. Bear Form

=== "Lua Code"

    ```lua
    _A.DSL:Get("sform")() == 5 -- (1)!
    ```

    1. Bear Form

=== "Lua Mode"

    ```lua
    PLAYER:Sform()==5 -- (1)!
    ```

    1. Bear Form

---

> ## has.form
>
> _`has.form || has.ShapeshiftForm || hasForm || hasShapeshiftForm`_

-   This condition checks if the player has a specific shapeshift form active.

#### Parameters

-   `STRING`: The name of the shapeshift form to check (e.g., "Cat Form", "Bear Form", "Ghost Wolf"). Use "Humanoid Form" to check for no active shapeshift.

#### Returns `BOOL`

-   `true` if the player has the specified shapeshift form, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "has.form(Swift Flight Form)"},
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

-   This condition checks if the player has a lunch-related buff active (e.g., Food, Drink, Refreshment).

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

---

> ## glyph

-   This condition checks if the player has a specific glyph active.

#### Parameters

-   `SPELL`: The spell ID or name of the glyph to check.

#### Returns `BOOL`

-   `true` if the player has the specified glyph, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "glyph(Shadow Word: Death)"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("glyph")(_, "Shadow Word: Death")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Glyph("Shadow Word: Death")
    ```

---

> ## createdBy

-   This condition checks if a specific unit created a particular object or effect.

#### Parameters

-   `UNIT1`: The unit identifier for the creator.
-   `UNIT2`: The unit identifier for the object or effect.

#### Returns `BOOL`

-   `true` if `UNIT1` created `UNIT2`, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {"Mocking Banner", "spell(Mocking Banner).ready && !createdBy(UNIT)", "cursor.ground"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("createdBy")("player", "Mocking Banner")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:CreatedBy("player", "Mocking Banner")
    ```

---

> ## bagSpace

-   This condition checks the available space in the player's bags.

#### Returns `NUMBER`

-   The number of available slots in the player's bags.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "bagSpace > 5"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("bagSpace")() > 5
    ```

=== "Lua Mode"

    ```lua
    PLAYER:BagSpace() > 5
    ```

---

> ## aura

-   This condition checks if the specified unit has an aura with the specified spell.

#### Parameters

-   `UNIT`: The unit to check for the aura.
-   `SPELL`: The spell to check if the unit has an aura with.

#### Returns `BOOL`

-   `true` if the unit has an aura with the specified spell, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.aura(Curse of the Elements)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("aura")("UNIT", "Curse of the Elements")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Aura("Curse of the Elements")
    ```

---

> ## aura.any

-   This condition checks if the specified unit has any aura with the specified spell.

#### Parameters

-   `UNIT`: The unit to check for the aura.
-   `SPELL`: The spell to check if the unit has any aura with.

#### Returns `BOOL`

-   `true` if the unit has any aura with the specified spell, otherwise `false`.

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.aura.any(Curse of the Elements)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("aura.any")("UNIT", "Curse of the Elements")
    ```

=== "Lua Mode"

    ```lua
    UNIT:AuraAny("Curse of the Elements")
    ```

---
