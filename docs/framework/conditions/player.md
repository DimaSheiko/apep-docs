# PLAYER

---

> ## group.members
>
> _`group.members || num.members`_

#### Returns `NUMBER`

-   The number of members in the player's group.

#### _Example:_

```lua
-- DSL Mode
{ACTION, "num.members"},

-- in Lua code
_A.DSL:Get("num.members")()

-- Lua Mode
PLAYER:NumMembers()
```

---

> ## issolo

#### Returns `BOOL`

-   `true` if the player is not in a group, `false` otherwise.

#### _Example:_

```lua
-- DSL Mode
{ACTION, "issolo"},

-- in Lua code
_A.DSL:Get("issolo")()

-- Lua Mode
PLAYER:Issolo()
```

---

> ## isparty

#### Returns `BOOL`

-   `true` if the player is in a party group, `false` otherwise.

#### _Example:_

```lua
-- DSL Mode
{ACTION, "isparty"},

-- in Lua code
_A.DSL:Get("isparty")()

-- Lua Mode
PLAYER:Isparty()
```

---

> ## israid

#### Returns `BOOL`

-   `true` if the player is in a raid group, `false` otherwise.

#### _Example:_

```lua
-- DSL Mode
{ACTION, "israid"},

-- in Lua code
_A.DSL:Get("israid")()

-- Lua Mode
PLAYER:Israid()
```

---

> ## group.type

#### Returns `NUMBER`

-   1 if solo, 2 if party, 3 if raid.

#### _Example:_

```lua
-- DSL Mode
{ACTION, "group.type==1"},

-- in Lua code
_A.DSL:Get("group.type")() == 1

-- Lua Mode
PLAYER:GroupType() == 1
```

---

> ## auto.attack
>
> _`auto.attack || auto.shoot`_

-   This conditions checks if the player's character is performing an auto-attack or auto-shoot (for hunters).

#### Returns `BOOL`

-   `true` if the character is auto-attacking or auto-shooting, `false` otherwise.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "auto.attack"},

-- in Lua code
_A.DSL:Get("auto.attack")()

-- Lua Mode
PLAYER:AutoAttack()
```

---

> ## swimming

-   This condition checks if the player character is currently swimming.

#### Returns `BOOL`

-   `true` if the player character is swimming, `false` otherwise.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "swimming"},

-- in Lua code
_A.DSL:Get("swimming")()

-- Lua Mode
PLAYER:Swimming()
```

---

> ## falling

-   This condition checks if the player character is currently falling.

#### Returns `BOOL`

-   `true` if the player character is falling, `false` otherwise.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "falling"},

-- in Lua code
_A.DSL:Get("falling")()

-- Lua Mode
PLAYER:Falling()
```

---

> ## falling.duration

-   These conditions provide the duration for which the player character has been falling.

#### Returns `NUMBER`

-   The duration (in `seconds`) for which the player character has been falling.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "falling.duration > 1.5"},

-- in Lua code
_A.DSL:Get("falling.duration")() > 1.5

-- Lua Mode
PLAYER:FallingDuration() > 1.5
```

---

> ## indoors

-   This condition checks if the player character is currently indoors.

#### Returns `BOOL`

-   `true` if the player character is indoors, `false` otherwise.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "indoors"},

-- in Lua code
_A.DSL:Get("indoors")()

-- Lua Mode
PLAYER:Indoors()
```

---

> ## mounted

-   This condition checks if the player character is currently mounted.

#### Returns `BOOL`

-   `true` if the player character is mounted, `false` otherwise.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "mounted"},

-- in Lua code
_A.DSL:Get("mounted")()

-- Lua Mode
PLAYER:Mounted()
```

---

> ## outcombat.time

-   This condition provides the time duration for which the player character has been out of combat.

#### Returns `NUMBER`

-   The time duration in `seconds` for which the player character has been out of combat.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "outcombat.time > 10"},

-- in Lua code
_A.DSL:Get("outcombat.time")() > 10

-- Lua Mode
PLAYER:OutcombatTime() > 10
```

---

> ## lost.control

-   This condition checks if the player is currently under the effect of any of the control states.

#### Returns `BOOL`

-   `true` if the player is in any of control states, otherwise `false`.

    `"stunned", "sapped", "disoriented",	"polymorphed", "incapacitated",`
    `"feared",	"horrified", "fleeing",	"intimidated", "asleep", "charmed",`
    `"banished",	"silenced",	"paralyzed"`

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "lost.control"},

-- in Lua code
_A.DSL:Get("lost.control")()

-- Lua Mode
PLAYER:LostControl()
```

---

> ## out.of.control

-   This condition checks if the player is currently in any of the specified loss of control states.

#### Parameters

-   `STATE(s)`: A string containing one or more loss of control states separated by '||'.

#### Returns `BOOL`

-   `true` if the player is in any of the specified loss of control states, otherwise `false`.

    `"stunned", "sapped", "disoriented",	"polymorphed", "incapacitated",`
    `"feared",	"horrified", "fleeing",	"intimidated", "asleep", "charmed",`
    `"banished",	"silenced",	"paralyzed"`

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "out.of.control(feared || incapacitate)"},

-- in Lua code
_A.DSL:Get("out.of.control")(_, "feared || incapacitate")

-- Lua Mode
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

```lua
-- DSL Mode
{ACTION, "lastcast(Vendeta)"},

-- in Lua code
_A.DSL:Get("lastcast")(_, "Vendeta")

-- Lua Mode
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

```lua
-- DSL Mode
{ACTION, "UNIT.lasttarget"},

-- in Lua code
_A.DSL:Get("lasttarget")(_, "UNIT")

-- Lua Mode
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

```lua
-- DSL Mode
{ACTION, "lastcast(Battle Cry).succeed"},

-- in Lua code
_A.DSL:Get("lastcast.succeed")(_, "Battle Cry")

-- Lua Mode
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

```lua
-- DSL Mode
{ACTION, "prev(Regrowth, 2).gcd"},

-- in Lua code
_A.DSL:Get("prev.gcd")(_, "Regrowth, 2")

-- Lua Mode
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

```lua
-- DSL Mode
{ACTION, "lastcast(Aimed Shot).seen"},

-- in Lua code
_A.DSL:Get("lastcast.seen")(_, "Aimed Shot")

-- Lua Mode
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

```lua
-- DSL Mode
{ACTION, "UNIT.unitLastCast(Counterspell).succeed"},

-- in Lua code
_A.DSL:Get("unitLastCast.succeed")("UNIT", "Counterspell")

-- Lua Mode
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

```lua
-- DSL Mode
{ACTION, "lastcast(Rejuvenation).count"},

-- in Lua code
_A.DSL:Get("lastcast.count")(_, "Rejuvenation")

-- Lua Mode
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

```lua
-- DSL Mode
{ACTION, "sform=5"}, -- Bear Form

-- in Lua code
_A.DSL:Get("sform")() == 5

-- Lua Mode
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

```lua
-- DSL Mode
{ACTION, "has(Swift Flight Form).form"},

-- in Lua code
_A.DSL:Get("has.form")(_, "Swift Flight Form")

-- Lua Mode
PLAYER:HasForm("Swift Flight Form")
```

---

> ## spell.IsTargeting

-   This condition checks if the player is currently in the targeting mode for a spell.

#### Returns `BOOL`

-   `true` if the player is targeting for a spell, otherwise `false`.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "spell.IsTargeting"},

-- in Lua code
_A.DSL:Get("spell.IsTargeting")()

-- Lua Mode
PLAYER:SpellIsTargeting()
```

---

> ## isStealthed

-   This condition checks if the player is currently in a stealthed state.

#### Returns `BOOL`

-   `true` if the player is in stealth, otherwise `false`.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "isStealthed"},

-- in Lua code
_A.DSL:Get("isStealthed")()

-- Lua Mode
PLAYER:IsStealthed()
```

---

> ## isHavingLunch

-   This condition checks if the player has a lunch-related buff active.

#### Returns `BOOL`

-   `true` if the player has a lunch-related buff, otherwise `false`.

#### _Examples:_

```lua
-- DSL Mode
{ACTION, "isHavingLunch"},

-- in Lua code
_A.DSL:Get("isHavingLunch")()

-- Lua Mode
PLAYER:IsHavingLunch()
```
