# DEBUFF
---


> ## debuff
  *`debuff || debuff.up`*

- It only checks for `player` applied debuffs.
#### Parameters
- `UNIT`: The unit to check for the debuff.
- `NAME`: The name or ID of the debuff to check.
#### Returns `BOOL`
- `true` if the specified debuff name or ID is active on the unit, `false` otherwise.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.debuff(Corruption)", UNIT},

-- in Lua code
_A.DSL:Get("debuff")("UNIT", "Corruption")

-- Lua Mode
UNIT:Debuff("Corruption")
```

***


> ## debuff.any
  *`debuff.any || debuff.any.up`*

- It checks for both `player and non-player` applied debuffs.
#### Parameters
- `UNIT`: The unit to check for the debuff.
- `NAME`: The name or ID of the debuff to check.
#### Returns `BOOL`
- `true` if the specified debuff name or ID is active on the unit, `false` otherwise.


#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.debuff(Chains of Ice).any", UNIT},

-- in Lua code
_A.DSL:Get("debuff.any")("UNIT", "Chains of Ice")

-- Lua Mode
UNIT:DebuffAny("Chains of Ice")
```

***


> ## debuff.stack
  *`debuff.stack || debuff.count`*

- It checks for player-applied debuff stacks.
#### Parameters
- `UNIT`: The unit to check for the debuff stacks.
- `NAME`: The name or ID of the debuff to check.
#### Returns `NUMBER`
- The number of stacks of the specified debuff on the unit, or 0 if not present.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.debuff(Razorice).stack >= 3", UNIT},

-- in Lua code
_A.DSL:Get("debuff.stack")("UNIT", "Razorice") >= 3

-- Lua Mode
UNIT:DebuffStack("Razorice") >= 3
```

***


> ## debuff.stack.any
  *`debuff.stack.any || debuff.count.any`*

- It checks for all debuff sources, not just player-applied debuffs.
#### Parameters
- `UNIT`: The unit to check for the debuff stacks.
- `NAME`: The name or ID of the debuff to check.
#### Returns `NUMBER`
- The number of stacks of the specified debuff on the unit, or 0 if not present.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.debuff(Necrotic Rot).stack.any >= 25", UNIT},

-- in Lua code
_A.DSL:Get("debuff.stack.any")("UNIT", "Necrotic Rot") >= 25

-- Lua Mode
UNIT:DebuffStackAny("Necrotic Rot") >= 25
```

***


> ## debuff.duration
  *`debuff.duration || debuff.remains`*

- It checks for player-applied debuffs only.
#### Parameters
- `UNIT`: The unit to check for the remaining duration of the debuff.
- `NAME`: The name or ID of the debuff to check.
#### Returns `NUMBER`
- The remaining duration of the specified debuff on the unit in `seconds`, or 0 if not present.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.debuff(Corruption).duration", UNIT},

-- in Lua code
_A.DSL:Get("debuff.duration")("UNIT", "Corruption")

-- Lua Mode
UNIT:DebuffDuration("Corruption")
```

***


> ## debuff.totalduration

- It checks for player-applied debuffs only.
#### Parameters
- `UNIT`: The unit to check for the total duration of the debuff.
- `NAME`: The name or ID of the debuff to check.
#### Returns `NUMBER`
- The total duration of the specified debuff on the unit in `seconds`, or 0 if not present.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.debuff(Corruption).totalduration", UNIT},

-- in Lua code
_A.DSL:Get("debuff.totalduration")("UNIT", "Corruption")

-- Lua Mode
UNIT:DebuffTotalduration("Corruption")
```

***


> ## debuff.refreshable

- This condition checks whether the specified debuff aura on the target unit is refreshable.
- A debuff is considered refreshable if its remaining duration is less than or equal to `30%` of its total duration.
#### Parameters
- `UNIT`: The unit to check for the refreshability of the debuff.
- `NAME`: The name or ID of the debuff to check.
#### Returns `BOOL`
- `true` if the debuff is refreshable, or `false` if not or if the debuff is not present.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.debuff(Corruption).refreshable", UNIT},

-- in Lua code
_A.DSL:Get("debuff.refreshable")("UNIT", "Corruption")

-- Lua Mode
UNIT:DebuffRefreshable("Corruption")
```

***


> ## debuff.duration.any
  *`debuff.duration.any || debuff.remains.any`*

- It checks for all debuff sources, not just player-applied debuffs.
#### Parameters
- `UNIT`: The unit to check for the remaining duration of the debuff.
- `NAME`: The name or ID of the debuff to check.
#### Returns `NUMBER`
- The remaining duration of the specified debuff on the unit in `seconds`, or 0 if not present.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.debuff(Quake).duration.any", UNIT},

-- in Lua code
_A.DSL:Get("debuff.duration.any")("UNIT", "Quake")

-- Lua Mode
UNIT:DebuffDurationAny("Quake")
```

***


> ## debuff.many

- This condition counts the number of instances of the specified debuff applied by the player on the unit.
#### Parameters
- `UNIT`: The unit to count the instances of the debuff.
- `NAME`: The name or ID of the debuff to count instances of.
#### Returns `NUMBER`
- The number of instances of the debuff applied by the player on the unit.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.debuff(Razorice).many", UNIT},

-- in Lua code
_A.DSL:Get("debuff.many")("UNIT", "Razorice")

-- Lua Mode
UNIT:DebuffMany("Razorice")
```

***


> ## debuff.many.any

- This condition counts the number of instances of the specified debuff on the unit, regardless of the source.
#### Parameters
- `UNIT`: The unit to count the instances of the debuff.
- `NAME`: The name or ID of the debuff to count instances of.
#### Returns `NUMBER`
- The number of instances of the debuff applied by the player on the target unit.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.debuff(debuff_name).many.any", UNIT},

-- in Lua code
_A.DSL:Get("debuff.many.any")("UNIT", "debuff_name")

-- Lua Mode
UNIT:DebuffManyAny("debuff_name")
```

***


> ## debuff.type

- This condition checks if the target unit has a debuff with the specified type.
#### Parameters
- `UNIT`: The unit to check for the debuff with the specified type.
- `debuff_type`: The type of debuff to check for.

  `"Magic", "Disease", "Poison", "Curse", "Enrage"`
#### Returns `BOOL`
- `true` if the unit has a debuff with the specified type, `false` otherwise.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.debuff(Curse).type", UNIT},

-- in Lua code
_A.DSL:Get("debuff.type")("UNIT", "Curse")

-- Lua Mode
UNIT:DebuffType("Curse")
```
