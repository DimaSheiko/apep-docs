# AZERITE
---


> ## azerite.count

- This condition returns the number of equipment items that contain Azerite power for a specific spell.

#### Parameters
- `spell`: The name of the spell to check for Azerite power.

#### Returns `NUMBER`
- The number of equipment items that contain Azerite power for the specified spell.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "azerite(Dance of Death).count >= 2"},

-- in Lua code
_A.DSL:Get("azerite.count")(_, "Dance of Death") >= 2

-- Lua Mode
PLAYER:AzeriteCount("Dance of Death") >= 2
```

***


> ## azerite.active

- This condition checks if the specified spell has active Azerite power.

#### Parameters
- `spell`: The spell for which to check active Azerite power.

#### Returns `BOOL`
- `true` if the specified spell has active Azerite power, `false` otherwise.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "azerite(Overflowing Mists).active"},

-- in Lua code
_A.DSL:Get("azerite.active")(_, "Overflowing Mists")

-- Lua Mode
PLAYER:AzeriteActive("Overflowing Mists")
```
