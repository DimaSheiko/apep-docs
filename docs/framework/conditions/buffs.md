# BUFFS

---

> ## hashero

-   This condition checks if the player has any of the heroism-related buffs.

#### Returns `BOOL`

-   `true` if the player has any of the heroism-related buffs, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "hashero"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("hashero")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Hashero()
    ```

---

> ## hero.duration
>
> _`hero.duration || heroDuration`_

-   Checks for the following heroism-related buffs: Heroism, Bloodlust, Time Warp, Ancient Hysteria, Drums of Rage.

#### Returns `NUMBER`

-   The remaining duration in `seconds` of the active heroism-related buff with the longest duration, or 0 if no such buff is active.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "heroDuration"},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("heroDuration")()
    ```

=== "Lua Mode"

    ```lua
    PLAYER:HeroDuration()
    ```

---

> ## buff
>
> _`buff || buff.up`_

-   It only checks for `player` applied buffs.

#### Parameters

-   `UNIT`: The unit to check for the buff.
-   `NAME`: The name or ID of the buff to check.

#### Returns `BOOL`

-   `true` if the specified buff name or ID is active on the unit, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.buff(Rejuvenation)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("buff")("UNIT", "Rejuvenation")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Buff("Rejuvenation")
    ```

---

> ## buff.any
>
> _`buff.any || buff.any.up`_

-   It checks for both `player and non-player` applied buffs.

#### Parameters

-   `UNIT`: The unit to check for the buff.
-   `NAME`: The name or ID of the buff to check.

#### Returns `BOOL`

-   `true` if the specified buff name or ID is active on the unit, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.buff(Regrowth).any", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("buff.any")("UNIT", "Regrowth")
    ```

=== "Lua Mode"

    ```lua
    UNIT:BuffAny("Regrowth")
    ```

---

> ## buff.stack
>
> _`buff.stack || buff.count`_

-   It checks for player-applied buff stacks.

#### Parameters

-   `UNIT`: The unit to check for the buff stacks.
-   `NAME`: The name or ID of the buff to check.

#### Returns `NUMBER`

-   The number of stacks of the specified buff on the unit, or 0 if not present.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.buff(Ironfur).stack", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("buff.stack")("UNIT", "Ironfur")
    ```

=== "Lua Mode"

    ```lua
    UNIT:BuffStack("Ironfur")
    ```

---

> ## buff.stack.any
>
> _`buff.stack.any || buff.count.any`_

-   It checks for all buff sources, not just player-applied buffs.

#### Parameters

-   `UNIT`: The unit to check for the buff stacks.
-   `NAME`: The name or ID of the buff to check.

#### Returns `NUMBER`

-   The number of stacks of the specified buff on the unit, or 0 if not present.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.buff(Rejuvenation).stack.any", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("buff.stack.any")("UNIT", "Rejuvenation")
    ```

=== "Lua Mode"

    ```lua
    UNIT:BuffStackAny("Rejuvenation")
    ```

---

> ## buff.duration
>
> _`buff.duration || buff.remains`_

-   It checks for player-applied buffs only.

#### Parameters

-   `UNIT`: The unit to check for the remaining duration of the buff.
-   `NAME`: The name or ID of the buff to check.

#### Returns `NUMBER`

-   The remaining duration of the specified buff on the unit in `seconds`, or 0 if not present.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.buff(Rejuvenation).duration", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("buff.duration")("UNIT", "Rejuvenation")
    ```

=== "Lua Mode"

    ```lua
    UNIT:BuffDuration("Rejuvenation")
    ```

---

> ## buff.totalduration

-   It checks for player-applied buffs only.

#### Parameters

-   `UNIT`: The unit to check for the total duration of the buff.
-   `NAME`: The name or ID of the buff to check.

#### Returns `NUMBER`

-   The total duration of the specified buff on the unit in `seconds`, or 0 if not present.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.buff(Rejuvenation).totalduration", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("buff.totalduration")("UNIT", "Rejuvenation")
    ```

=== "Lua Mode"

    ```lua
    UNIT:BuffTotalduration("Rejuvenation")
    ```

---

> ## buff.refreshable

-   This condition checks whether the specified buff aura on the target unit is refreshable.
-   A buff is considered refreshable if its remaining duration is less than or equal to `30%` of its total duration.

#### Parameters

-   `UNIT`: The unit to check for the refreshability of the buff.
-   `NAME`: The name or ID of the buff to check.

#### Returns `BOOL`

-   `true` if the buff is refreshable, or `false` if not or if the buff is not present.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.buff(Rejuvenation).refreshable", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("buff.refreshable")("UNIT", "Rejuvenation")
    ```

=== "Lua Mode"

    ```lua
    UNIT:BuffRefreshable("Rejuvenation")
    ```

---

> ## buff.duration.any
>
> _`buff.duration.any || buff.remains.any`_

-   It checks for all buff sources, not just player-applied buffs.

#### Parameters

-   `UNIT`: The unit to check for the remaining duration of the buff.
-   `NAME`: The name or ID of the buff to check.

#### Returns `NUMBER`

-   The remaining duration of the specified buff on the unit in `seconds`, or 0 if not present.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.buff(Rejuvenation).duration.any", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("buff.duration.any")("UNIT", "Rejuvenation")
    ```

=== "Lua Mode"

    ```lua
    UNIT:BuffDurationAny("Rejuvenation")
    ```

---

> ## buff.many

-   This condition counts the number of instances of the specified buff applied by the player on the unit.

#### Parameters

-   `UNIT`: The unit to count the instances of the buff.
-   `NAME`: The name or ID of the buff to count instances of.

#### Returns `NUMBER`

-   The number of instances of the buff applied by the player on the unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.buff(buff_name).many", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("buff.many")("UNIT", "buff_name")
    ```

=== "Lua Mode"

    ```lua
    UNIT:BuffMany("buff_name")
    ```

---

> ## buff.many.any

-   This condition counts the number of instances of the specified buff on the unit, regardless of the source.

#### Parameters

-   `UNIT`: The unit to count the instances of the buff.
-   `NAME`: The name or ID of the buff to count instances of.

#### Returns `NUMBER`

-   The number of instances of the buff on the target unit, from any source.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.buff(Bolstering).many.any", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("buff.many.any")("UNIT", "Bolstering")
    ```

=== "Lua Mode"

    ```lua
    UNIT:BuffManyAny("Bolstering")
    ```

---

> ## buff.type

-   This condition checks if the target unit has a buff with the specified type.

#### Parameters

-   `UNIT`: The unit to check for the buff with the specified type.
-   `buff_type`: The type of buff to check for.

    `"Magic", "Disease", "Poison", "Curse", "Enrage"`

#### Returns `BOOL`

-   `true` if the unit has a buff with the specified type, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.buff(Magic).type", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("buff.type")("UNIT", "Magic")
    ```

=== "Lua Mode"

    ```lua
    UNIT:BuffType("Magic")
    ```

---

# COUNT FUNCTIONS

---

> ## count.enemies.buffs

-   This condition counts how many enemy units in combat have a specific buff applied by the player.

#### Parameters

-   `BUFF_NAME`: The name or ID of the buff to count.

#### Returns `NUMBER`

-   The number of enemy units in combat that have the specified buff.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "count(Power Word: Shield).enemies.buffs >= 2"},
    ```
=== "Lua Code"

    ```lua
    _A.DSL:Get("count.enemies.buffs")("Power Word: Shield") >= 2
    ```
=== "Lua Mode"

    ```lua
    PLAYER:CountEnemiesBuffs("Power Word: Shield") >= 2
    ```

---

> ## count.friendly.buffs

-   This condition counts how many friendly units in the roster have a specific buff applied by the player.

#### Parameters

-   `BUFF_NAME`: The name or ID of the buff to count.

#### Returns `NUMBER`

-   The number of friendly units that have the specified buff.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "count(Rejuvenation).friendly.buffs >= 3"},
    ```
=== "Lua Code"

    ```lua
    _A.DSL:Get("count.friendly.buffs")("Rejuvenation") >= 3
    ```
=== "Lua Mode"

    ```lua
    PLAYER:CountFriendlyBuffs("Rejuvenation") >= 3
    ```

---

> ## count.friendly.buffsAny

-   This condition counts how many friendly units in the roster have a specific buff, regardless of the source.

#### Parameters

-   `BUFF_NAME`: The name or ID of the buff to count.

#### Returns `NUMBER`

-   The number of friendly units that have the specified buff from any source.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "count(Power Word: Fortitude).friendly.buffsAny == 5"},
    ```
=== "Lua Code"

    ```lua
    _A.DSL:Get("count.friendly.buffsAny")("Power Word: Fortitude") == 5
    ```
=== "Lua Mode"

    ```lua
    PLAYER:CountFriendlyBuffsAny("Power Word: Fortitude") == 5
    ```

---

> ## count.enemies.debuffs

-   This condition counts how many enemy units in combat have a specific debuff applied by the player.

#### Parameters

-   `DEBUFF_NAME`: The name or ID of the debuff to count.

#### Returns `NUMBER`

-   The number of enemy units in combat that have the specified debuff.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "count(Corruption).enemies.debuffs >= 4"},
    ```
=== "Lua Code"

    ```lua
    _A.DSL:Get("count.enemies.debuffs")("Corruption") >= 4
    ```
=== "Lua Mode"

    ```lua
    PLAYER:CountEnemiesDebuffs("Corruption") >= 4
    ```

---

> ## count.enemies.debuffs.any

-   This condition counts how many enemy units in combat have a specific debuff, regardless of the source.

#### Parameters

-   `DEBUFF_NAME`: The name or ID of the debuff to count.

#### Returns `NUMBER`

-   The number of enemy units in combat that have the specified debuff from any source.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "count(Shadow Word: Pain).enemies.debuffs.any >= 1"},
    ```
=== "Lua Code"

    ```lua
    _A.DSL:Get("count.enemies.debuffs.any")("Shadow Word: Pain") >= 1
    ```
=== "Lua Mode"

    ```lua
    PLAYER:CountEnemiesDebuffsAny("Shadow Word: Pain") >= 1
    ```

---

> ## count.friendly.debuffs

-   This condition counts how many friendly units in the roster have a specific debuff applied by the player.

#### Parameters

-   `DEBUFF_NAME`: The name or ID of the debuff to count.

#### Returns `NUMBER`

-   The number of friendly units that have the specified debuff.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "count(Weakened Soul).friendly.debuffs > 0"},
    ```
=== "Lua Code"

    ```lua
    _A.DSL:Get("count.friendly.debuffs")("Weakened Soul") > 0
    ```
=== "Lua Mode"

    ```lua
    PLAYER:CountFriendlyDebuffs("Weakened Soul") > 0
    ```
