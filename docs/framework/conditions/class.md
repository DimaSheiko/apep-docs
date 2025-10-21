# CLASS

---

> ## power

-   This condition returns the current amount of a specified power type for the player.
-   Power types are identified by their numeric ID (e.g., 0 for Mana, 1 for Rage, etc.).

#### Parameters

-   `pType` (NUMBER): The numeric ID of the power type.

#### Returns `NUMBER`

-   The current amount of the specified power type, or -1 if the power type is invalid.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "power(1) >= 50"}, -- Checks if Rage (ID 1) is >= 50
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("power")(1) >= 50
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Power(1) >= 50
    ```

---

> ## power.regen

-   This condition calculates and returns the power regeneration rate of the specified unit.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player" if not specified in the DSL, though the function itself expects a target.

#### Returns `NUMBER`

-   The power regeneration rate of the target.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "power.regen >= 5"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("power.regen")("target") >= 5
    ```

=== "Lua Mode"

    ```lua
    PLAYER:PowerRegen() >= 5
    ```

---

> ## shadoworbs

-   This condition returns the current amount of Shadow Orbs the target has.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The current amount of Shadow Orbs.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "shadoworbs >= 3"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("shadoworbs")() >= 3
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Shadoworbs() >= 3
    ```

---

> ## alternate

-   This condition returns the current amount of Alternate power the target has.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The current amount of Alternate power.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "alternate >= 1"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("alternate")() >= 1
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Alternate() >= 1
    ```

---

> ## darkforce

-   This condition returns the current amount of Dark Force power the target has.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The current amount of Dark Force power.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "darkforce > 0"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("darkforce")() > 0
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Darkforce() > 0
    ```

---

> ## burningembers

-   This condition returns the current amount of Burning Embers the target has.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The current amount of Burning Embers.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "burningembers >= 4"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("burningembers")() >= 4
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Burningembers() >= 4
    ```

---

> ## demonicfury

-   This condition returns the current amount of Demonic Fury the target has.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The current amount of Demonic Fury.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "demonicfury >= 200"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("demonicfury")() >= 200
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Demonicfury() >= 200
    ```

---

> ## energy

-   This condition returns the current energy amount of the target.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The current energy amount of the target.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "energy >= 60"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("energy")("target") >= 60
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Energy() >= 60
    ```

---

> ## energy.max
>
> _`energy.max || energyMax`_

-   This condition returns the maximum energy amount of the target.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The maximum energy amount of the target.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "energy.max >= 100"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("energy.max")("target") >= 100
    ```

=== "Lua Mode"

    ```lua
    PLAYER:EnergyMax() >= 100
    ```

---

> ## energy.diff
>
> _`energy.diff || energy.deficit || energydiff`_

-   This condition returns the difference between the maximum energy and the current energy of the target.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The energy deficit (difference) of the target.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "energy.diff >= 20"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("energy.diff")("target") >= 20
    ```

=== "Lua Mode"

    ```lua
    PLAYER:EnergyDiff() >= 20
    ```

---

> ## time.to.max
>
> _`time.to.max || timetomax`_

-   This condition calculates the estimated time in seconds for the target's primary resource to reach its maximum value, based on current regeneration rate.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The estimated time in seconds to reach maximum resource.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "time.to.max < 1"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("time.to.max")("target") < 1
    ```

=== "Lua Mode"

    ```lua
    PLAYER:TimeToMax() < 1
    ```

---

> ## mana.raw

-   This condition returns the current mana of the target.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The raw mana value of the target.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "mana.raw >= 400"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("mana.raw")("target") >= 400
    ```

=== "Lua Mode"

    ```lua
    PLAYER:ManaRaw() >= 400
    ```

---

> ## mana

-   This condition returns the mana percentage of the target.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The percentage of mana (0-100) of the target. Returns 0 if the unit has no mana pool.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "mana >= 80"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("mana")("target") >= 80
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Mana() >= 80
    ```

---

> ## insanity

-   This condition retrieves the current amount of Insanity power of the target.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The current amount of Insanity power.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "insanity >= 80"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("insanity")("target") >= 80
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Insanity() >= 80
    ```

---

> ## ispet
>
> _`ispet || isPet`_

-   This condition checks if the specified unit is a pet. This includes the player's pet, other players' pets, or specific creature types like non-combat pets, wild pets, critters, or totems.

#### Parameters

-   `UNIT`: The unit to check.

#### Returns `BOOL`

-   `true` if the unit is considered a pet, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.ispet"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("ispet")("target")
    ```

=== "Lua Mode"

    ```lua
    TARGET:Ispet()
    ```

---

> ## focus

-   This condition returns the current focus amount of the target.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The focus resource of the specified target.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "focus >= 40"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("focus")("target") >= 40
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Focus() >= 40
    ```

---

> ## focus.max
>
> _`focus.max || focusMax`_

-   This condition retrieves the maximum focus resource of the target.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The maximum focus resource of the target.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "focus.max > 100"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("focus.max")("target") > 100
    ```

=== "Lua Mode"

    ```lua
    PLAYER:FocusMax() > 100
    ```

---

> ## runic.power
>
> _`runic.power || runicpower`_

-   This condition calculates the Runic Power resource of the target.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The Runic Power resource of the target.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "runic.power > 20"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("runic.power")("target") > 20
    ```

=== "Lua Mode"

    ```lua
    PLAYER:RunicPower() > 20
    ```

---

> ## runes

-   This condition calculates the number of available runes for the player. It returns a fractional value if a rune is on cooldown (e.g., 5.5 means 5 runes are ready, and the next will be ready in 0.5 * 10 = 5 seconds).

#### Returns `NUMBER`

-   The number of available runes, including a fractional part for the next cooldown.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "runes > 4.5"}, -- True if 5 runes are ready, or 4 ready and the next one soon.
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("runes")() > 4.5
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Runes() > 4.5
    ```

---

> ## death.runes
>
> _`death.runes || deathrunes`_

-   This condition calculates the number of Death Runes currently available to the player.

#### Returns `NUMBER`

-   The count of available Death Runes.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "death.runes >= 2"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("death.runes")() >= 2
    ```

=== "Lua Mode"

    ```lua
    PLAYER:DeathRunes() >= 2
    ```

---

> ## totalActiveRunes

-   This condition calculates the total number of runes currently active (not on cooldown) for the player.

#### Returns `NUMBER`

-   The total count of active runes.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "totalActiveRunes == 6"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("totalActiveRunes")() == 6
    ```

=== "Lua Mode"

    ```lua
    PLAYER:TotalActiveRunes() == 6
    ```

---

> ## rune.count

-   This condition returns the number of active runes of a specific type and the total number of active runes.
-   Rune types can be specified by name ("blood", "unholy", "frost", "death") or numeric ID (1-4).

#### Parameters

-   `rune` (STRING or NUMBER): The name or ID of the rune type.

#### Returns `NUMBER, NUMBER`

-   The count of active runes of the specified type.
-   The total number of active runes.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "rune.count(blood) >= 2"},
    ```

=== "Lua Code"

    ```lua
    local bloodRunes, totalRunes = _A.DSL:Get("rune.count")(_, "blood")
    bloodRunes >= 2
    ```

=== "Lua Mode"

    ```lua
    local bloodRunes, totalRunes = PLAYER:RuneCount("blood")
    bloodRunes >= 2
    ```

---

> ## maelstrom

-   This condition returns the amount of Maelstrom power on the target.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The amount of Maelstrom power.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "maelstrom > 20"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("maelstrom")("target") > 20
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Maelstrom() > 20
    ```

---

> ## totem

-   This condition checks if a specific totem is currently active for the player.

#### Parameters

-   `totem` (STRING or NUMBER): The spell ID or name of the totem to check for.

#### Returns `BOOL`

-   `true` if the specified totem is currently active, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "totem(Flametongue Totem)"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("totem")(_, "Flametongue Totem")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Totem("Flametongue Totem")
    ```

---

> ## totem.duration

-   This condition calculates the remaining duration (in seconds) of a specific totem.

#### Parameters

-   `totem` (STRING or NUMBER): The spell ID or name of the totem to check the duration for.

#### Returns `NUMBER`

-   The remaining duration of the specified totem in seconds, or 0 if the totem is not active.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "totem(Mana Spring Totem).duration < 0.5"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("totem.duration")(_, "Mana Spring Totem") < 0.5
    ```

=== "Lua Mode"

    ```lua
    PLAYER:TotemDuration("Mana Spring Totem") < 0.5
    ```

---

> ## totem.time

-   This condition returns the maximum duration (in seconds) of a specific totem.

#### Parameters

-   `totem` (STRING or NUMBER): The spell ID or name of the totem to retrieve the maximum duration for.

#### Returns `NUMBER`

-   The maximum duration of the specified totem in seconds, or 0 if the totem is not found.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "totem(Mana Spring Totem).time == 60"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("totem.time")(_, "Mana Spring Totem") == 60
    ```

=== "Lua Mode"

    ```lua
    PLAYER:TotemTime("Mana Spring Totem") == 60
    ```

---

> ## soulshards

-   This condition returns the current number of Soul Shards the target has.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The current number of Soul Shards.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "soulshards >= 3"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("soulshards")("target") >= 3
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Soulshards() >= 3
    ```

---

> ## chi

-   This condition returns the current Chi the target has.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The current number of Chi.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "chi >= 3"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("chi")("target") >= 3
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Chi() >= 3
    ```

---

> ## chi.max
>
> _`chi.max || chiMax`_

-   This condition returns the maximum number of Chi the target can have.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The maximum number of Chi.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "chi.max == 5"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("chi.max")("target") == 5
    ```

=== "Lua Mode"

    ```lua
    PLAYER:ChiMax() == 5
    ```

---

> ## chi.diff
>
> _`chi.diff || chi.deficit || chidiff`_

-   This condition calculates the deficit of Chi (maximum Chi - current Chi) for the target.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The deficit of Chi.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "chi.diff > 2"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("chi.diff")("target") > 2
    ```

=== "Lua Mode"

    ```lua
    PLAYER:ChiDiff() > 2
    ```

---

> ## form

-   This condition retrieves the current shapeshift form index that the player is in.

#### Returns `NUMBER`

-   The shapeshift form index, or 0 if the player is not in any form.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "form == 3"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("form")() == 3
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Form() == 3
    ```

---

> ## stance

-   This condition retrieves the index of the stance that the player is in. This is functionally similar to `form`.

#### Returns `NUMBER`

-   The index of the current stance, or 0 if not in a stance.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "stance == 2"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("stance")() == 2
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Stance() == 2
    ```

---

> ## lunar.power
>
> _`lunar.power || lunarpower || astralpower`_

-   This condition retrieves the current amount of Lunar Power (Astral Power) that the target has.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The amount of Lunar Power.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "lunar.power >= 60"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("lunar.power")("target") >= 60
    ```

=== "Lua Mode"

    ```lua
    PLAYER:LunarPower() >= 60
    ```

---

> ## mushrooms

-   This condition counts the number of Wild Mushroom totems currently active for the player.

#### Returns `NUMBER`

-   The number of active Wild Mushroom totems (typically 0 to 3).

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "mushrooms > 0"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("mushrooms")() > 0
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Mushrooms() > 0
    ```

---

> ## holy.power
>
> _`holy.power || holypower`_

-   This condition retrieves the current amount of Holy Power that the target has.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The amount of Holy Power.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "holy.power >= 3"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("holy.power")("target") >= 3
    ```

=== "Lua Mode"

    ```lua
    PLAYER:HolyPower() >= 3
    ```

---

> ## rage

-   This condition retrieves the current amount of Rage that the target has.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The amount of Rage.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "rage >= 50"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("rage")("target") >= 50
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Rage() >= 50
    ```

---

> ## rage.diff
>
> _`rage.diff || rage.deficit || ragediff`_

-   This condition calculates the deficit of Rage (maximum Rage - current Rage) for the target.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The deficit of Rage.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "rage.diff >= 15"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("rage.diff")("target") >= 15
    ```

=== "Lua Mode"

    ```lua
    PLAYER:RageDiff() >= 15
    ```

---

> ## fury

-   This condition retrieves the current amount of Fury that the target has.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The amount of Fury.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "fury >= 50"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("fury")("target") >= 50
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Fury() >= 50
    ```

---

> ## fury.diff
>
> _`fury.diff || fury.deficit || furydiff`_

-   This condition calculates the deficit of Fury (maximum Fury - current Fury) for the target.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The deficit of Fury.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "fury.diff >= 15"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("fury.diff")("target") >= 15
    ```

=== "Lua Mode"

    ```lua
    PLAYER:FuryDiff() >= 15
    ```

---

> ## pain

-   This condition retrieves the current amount of Pain that the target has.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The amount of Pain.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "pain >= 30"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("pain")("target") >= 30
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Pain() >= 30
    ```

---

> ## arcane.charges
>
> _`arcane.charges || arcanecharges`_

-   This condition retrieves the current number of Arcane Charges that the target has.

#### Parameters

-   `target` (UNIT, optional): The unit to check. Defaults to "player".

#### Returns `NUMBER`

-   The current number of Arcane Charges.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "arcane.charges >= 4"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("arcane.charges")("target") >= 4
    ```

=== "Lua Mode"

    ```lua
    PLAYER:ArcaneCharges() >= 4
    ```

---

> ## combo
>
> _`combo || combo.points || combopoints`_

-   This condition retrieves the current number of Combo Points the player has on the specified target.

#### Parameters

-   `target` (UNIT): The target unit to check combo points against (e.g., "target").

#### Returns `NUMBER`

-   The current number of Combo Points.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.combo >= 4"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("combo")("target") >= 4
    ```

=== "Lua Mode"

    ```lua
    TARGET:Combo() >= 4
    ```

---

> ## combo.max
>
> _`combo.max || combomax`_

-   This condition returns the maximum number of Combo Points the player can have.

#### Returns `NUMBER`

-   The maximum number of Combo Points.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "combo.max == 5"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("combo.max")() == 5
    ```

=== "Lua Mode"

    ```lua
    PLAYER:ComboMax() == 5
    ```

---

> ## combo.diff
>
> _`combo.diff || combo.deficit || combodiff || combopoints.diff || combopoints.deficit || combopointsdiff`_

-   This condition calculates the deficit of Combo Points (maximum Combo Points - current Combo Points) the player has on the specified target.

#### Parameters

-   `target` (UNIT): The target unit to check combo points against.

#### Returns `NUMBER`

-   The deficit of Combo Points.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "target.combo.diff > 2"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("combo.diff")("target") > 2
    ```

=== "Lua Mode"

    ```lua
    TARGET:ComboDiff() > 2
    ```

---

> ## warlock.minions

-   This condition returns the total number of active Warlock minions tracked by the system.

#### Returns `NUMBER`

-   The total number of active Warlock minions.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "warlock.minions > 2"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("warlock.minions")() > 2
    ```

=== "Lua Mode"

    ```lua
    PLAYER:WarlockMinions() > 2
    ```

---

> ## warlock.empower

-   This condition returns the number of Warlock's minions that are currently empowered (e.g., by the Demonic Empowerment spell).

#### Returns `NUMBER`

-   The number of empowered Warlock minions.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "warlock.empower > 3"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("warlock.empower")() > 3
    ```

=== "Lua Mode"

    ```lua
    PLAYER:WarlockEmpower() > 3
    ```

---

> ## warlock.empower.missing

-   This condition returns the number of Warlock's minions that are not currently empowered.

#### Returns `NUMBER`

-   The number of unempowered Warlock minions.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "warlock.empower.missing > 2"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("warlock.empower.missing")() > 2
    ```

=== "Lua Mode"

    ```lua
    PLAYER:WarlockEmpowerMissing() > 2
