# DEBUFF

---

> ## debuff
>
> _`debuff || debuff.up`_

-   It only checks for `player` applied debuffs.

#### Parameters

-   `UNIT`: The unit to check for the debuff.
-   `NAME`: The name or ID of the debuff to check.

#### Returns `BOOL`

-   `true` if the specified debuff name or ID is active on the unit, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.debuff(Corruption)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("debuff")("UNIT", "Corruption")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Debuff("Corruption")
    ```

---

> ## debuff.any
>
> _`debuff.any || debuff.any.up`_

-   It checks for both `player and non-player` applied debuffs.

#### Parameters

-   `UNIT`: The unit to check for the debuff.
-   `NAME`: The name or ID of the debuff to check.

#### Returns `BOOL`

-   `true` if the specified debuff name or ID is active on the unit, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.debuff(Chains of Ice).any", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("debuff.any")("UNIT", "Chains of Ice")
    ```

=== "Lua Mode"

    ```lua
    UNIT:DebuffAny("Chains of Ice")
    ```

---

> ## debuff.stack
>
> _`debuff.stack || debuff.count`_

-   It checks for player-applied debuff stacks.

#### Parameters

-   `UNIT`: The unit to check for the debuff stacks.
-   `NAME`: The name or ID of the debuff to check.

#### Returns `NUMBER`

-   The number of stacks of the specified debuff on the unit, or 0 if not present.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.debuff(Razorice).stack >= 3", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("debuff.stack")("UNIT", "Razorice") >= 3
    ```

=== "Lua Mode"

    ```lua
    UNIT:DebuffStack("Razorice") >= 3
    ```

---

> ## debuff.stack.any
>
> _`debuff.stack.any || debuff.count.any`_

-   It checks for all debuff sources, not just player-applied debuffs.

#### Parameters

-   `UNIT`: The unit to check for the debuff stacks.
-   `NAME`: The name or ID of the debuff to check.

#### Returns `NUMBER`

-   The number of stacks of the specified debuff on the unit, or 0 if not present.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.debuff(Necrotic Rot).stack.any >= 25", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("debuff.stack.any")("UNIT", "Necrotic Rot") >= 25
    ```

=== "Lua Mode"

    ```lua
    UNIT:DebuffStackAny("Necrotic Rot") >= 25
    ```

---

> ## debuff.duration
>
> _`debuff.duration || debuff.remains`_

-   It checks for player-applied debuffs only.

#### Parameters

-   `UNIT`: The unit to check for the remaining duration of the debuff.
-   `NAME`: The name or ID of the debuff to check.

#### Returns `NUMBER`

-   The remaining duration of the specified debuff on the unit in `seconds`, or 0 if not present.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.debuff(Corruption).duration", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("debuff.duration")("UNIT", "Corruption")
    ```

=== "Lua Mode"

    ```lua
    UNIT:DebuffDuration("Corruption")
    ```

---

> ## debuff.totalduration

-   It checks for player-applied debuffs only.

#### Parameters

-   `UNIT`: The unit to check for the total duration of the debuff.
-   `NAME`: The name or ID of the debuff to check.

#### Returns `NUMBER`

-   The total duration of the specified debuff on the unit in `seconds`, or 0 if not present.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.debuff(Corruption).totalduration", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("debuff.totalduration")("UNIT", "Corruption")
    ```

=== "Lua Mode"

    ```lua
    UNIT:DebuffTotalduration("Corruption")
    ```

---

> ## debuff.refreshable

-   This condition checks whether the specified debuff aura on the target unit is refreshable.
-   A debuff is considered refreshable if its remaining duration is less than or equal to `30%` of its total duration.

#### Parameters

-   `UNIT`: The unit to check for the refreshability of the debuff.
-   `NAME`: The name or ID of the debuff to check.

#### Returns `BOOL`

-   `true` if the debuff is refreshable, or `false` if not or if the debuff is not present.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.debuff(Corruption).refreshable", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("debuff.refreshable")("UNIT", "Corruption")
    ```

=== "Lua Mode"

    ```lua
    UNIT:DebuffRefreshable("Corruption")
    ```

---

> ## debuff.duration.any
>
> _`debuff.duration.any || debuff.remains.any`_

-   It checks for all debuff sources, not just player-applied debuffs.

#### Parameters

-   `UNIT`: The unit to check for the remaining duration of the debuff.
-   `NAME`: The name or ID of the debuff to check.

#### Returns `NUMBER`

-   The remaining duration of the specified debuff on the unit in `seconds`, or 0 if not present.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.debuff(Quake).duration.any", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("debuff.duration.any")("UNIT", "Quake")
    ```

=== "Lua Mode"

    ```lua
    UNIT:DebuffDurationAny("Quake")
    ```

---

> ## debuff.many

-   This condition counts the number of instances of the specified debuff applied by the player on the unit.

#### Parameters

-   `UNIT`: The unit to count the instances of the debuff.
-   `NAME`: The name or ID of the debuff to count instances of.

#### Returns `NUMBER`

-   The number of instances of the debuff applied by the player on the unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.debuff(Razorice).many", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("debuff.many")("UNIT", "Razorice")
    ```

=== "Lua Mode"

    ```lua
    UNIT:DebuffMany("Razorice")
    ```

---

> ## debuff.many.any

-   This condition counts the number of instances of the specified debuff on the unit, regardless of the source.

#### Parameters

-   `UNIT`: The unit to count the instances of the debuff.
-   `NAME`: The name or ID of the debuff to count instances of.

#### Returns `NUMBER`

-   The number of instances of the debuff on the target unit, from any source.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.debuff(debuff_name).many.any", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("debuff.many.any")("UNIT", "debuff_name")
    ```

=== "Lua Mode"

    ```lua
    UNIT:DebuffManyAny("debuff_name")
    ```

---

> ## debuff.type

-   This condition checks if the target unit has a debuff with the specified type.

#### Parameters

-   `UNIT`: The unit to check for the debuff with the specified type.
-   `debuff_type`: The type of debuff to check for.

    `"Magic", "Disease", "Poison", "Curse", "Enrage"`

#### Returns `BOOL`

-   `true` if the unit has a debuff with the specified type, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.debuff(Curse).type", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("debuff.type")("UNIT", "Curse")
    ```

=== "Lua Mode"

    ```lua
    UNIT:DebuffType("Curse")
    ```

---

> ## debuff.count.type

-   This condition counts the total number of stacks of all debuffs of a specified type on the target unit.
-   Multiple debuff types can be checked by separating them with `||`.

#### Parameters

-   `UNIT`: The unit to count the debuff stacks on.
-   `debuff_type`: The type of debuff to count stacks for.

    `"Magic", "Disease", "Poison", "Curse", "Enrage"`

#### Returns `NUMBER`

-   The total number of stacks of all debuffs of the specified type(s) on the unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.debuff(Magic || Curse).count.type > 0", UNIT},
    -- Counts stacks of all Magic and Curse debuffs.
    ```
=== "Lua Code"

    ```lua
    _A.DSL:Get("debuff.count.type")("UNIT", "Magic || Curse") > 0
    ```
=== "Lua Mode"

    ```lua
    UNIT:DebuffCountType("Magic || Curse") > 0
    ```

---

> ## dispelType.atRndTime

-   This condition checks if a debuff of a specified dispel type on the target unit is within a random time frame (1 to 3 seconds before its expiration) of its duration, making it a candidate for dispelling.
-   It iterates through all debuffs on the target.

#### Parameters

-   `UNIT`: The unit to check for dispellable debuffs.
-   `dtype`: The dispel type of the debuff to check for.

    `"Magic", "Disease", "Poison", "Curse"`

#### Returns `BOOL`

-   `true` if a debuff of the specified dispel type is found and its remaining time is less than `(total duration - random(1, 3))`, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.dispelType.atRndTime(Magic)", UNIT},
    -- Checks if any Magic debuff is dispellable at a random time.
    ```
=== "Lua Code"

    ```lua
    _A.DSL:Get("dispelType.atRndTime")("UNIT", "Magic")
    ```
=== "Lua Mode"

    ```lua
    UNIT:DispelTypeAtRndTime("Magic")
    ```
