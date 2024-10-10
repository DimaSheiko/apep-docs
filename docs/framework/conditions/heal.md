# HEAL
---


> ## health

- This condition returns the health percentage of the specified unit.

#### Parameters
- `UNIT`: The unit to retrieve the health percentage from.

#### Returns `NUMBER`
- The health percentage of the unit.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.health >= 80", UNIT},

-- in Lua code
_A.DSL:Get("health")("UNIT") >= 80

-- Lua Mode
UNIT:Health() >= 80
```

***

> ## health.actual

- This condition returns the actual health value of the specified unit.

#### Parameters
- `UNIT`: The unit to retrieve the actual health value from.

#### Returns `NUMBER`
- The actual health value of the unit.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.health.actual >= 35000", UNIT},

-- in Lua code
_A.DSL:Get("health.actual")("UNIT") >= 35000

-- Lua Mode
UNIT:HealthActual() >= 35000
```

***

> ## health.max

- This condition returns the maximum health value of the specified unit.

#### Parameters
- `UNIT`: The unit to retrieve the maximum health value from.

#### Returns `NUMBER`
- The maximum health value of the unit.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.health.max >= 150000", UNIT},

-- in Lua code
_A.DSL:Get("health.max")("UNIT") >= 150000

-- Lua Mode
UNIT:HealthMax() >= 150000
```

***


> ## health.predicted
  *`health.predicted || healthp`*

- This condition return the predicted health percentage of the specified unit.

#### Parameters
- `UNIT`: The unit to calculate the predicted health percentage for.

#### Returns `NUMBER`
- The predicted health percentage of the target unit.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.health.predicted >= 80", UNIT},

-- in Lua code
_A.DSL:Get("health.predicted")("UNIT") >= 80

-- Lua Mode
UNIT:HealthPredicted() >= 80
```

***

> ## health.predicted.actual

- This condition returns the predicted actual health value of the specified unit

#### Parameters
- `UNIT`: The unit to retrieve the predicted actual health value from.

#### Returns `NUMBER`
- The predicted actual health value of the unit.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.health.predicted.actual >= 35000", UNIT},

-- in Lua code
_A.DSL:Get("health.predicted.actual")("UNIT") >= 35000

-- Lua Mode
UNIT:HealthPredictedActual() >= 35000
```

***


> ## area.heal

- This condition counts the number of units within a specified range of a target unit whose health is below a certain threshold.

#### Parameters
- `UNIT`: The unit to calculate the area healing for.
- `ARGS`: A string containing two arguments separated by a comma:
    - `distance`: The maximum distance within which to count units.
    - `health`: The health threshold below which to count units.

#### Returns `NUMBER`
- The number of units within the specified range of the target unit whose health is below the threshold.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.area(40, 80).heal >= 4", UNIT},

-- in Lua code
_A.DSL:Get("area.heal")("UNIT", "40, 80") >= 4

-- Lua Mode
UNIT:AreaHeal(40, 80) >= 4
```

***


> ## area.heal.infront

- This condition counts the number of units within a specified range of a unit whose health is below a certain threshold and are in front of the unit.

#### Parameters
- `UNIT`: The unit to calculate the area healing for.
- `ARGS`: A string containing two arguments separated by a comma:
    - `distance`: The maximum distance within which to count units.
    - `health`: The health threshold below which to count units.

#### Returns `NUMBER`
- The number of units within the specified range of the unit whose health is below the threshold and are in front of the unit.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.area(40, 80).heal.infront >= 4", UNIT},

-- in Lua code
_A.DSL:Get("area.heal.infront")("UNIT", "40, 80") >= 4

-- Lua Mode
UNIT:AreaHealInfront(40, 80) >= 4
```


