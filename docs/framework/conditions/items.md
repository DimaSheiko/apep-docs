# ITEM
---


> ## item
  *`item || equipped`*

- Checks whether a specific item is currently equipped by the player.
#### Parameters
- `NameOrID`: The item name or ID to check for.
#### Returns `BOOL`
- `true` if the specified item is currently equipped, `false` otherwise.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "equipped(Draught of Souls)"},

-- in Lua code
_A.DSL:Get("equipped")(_, "Draught of Souls")

-- Lua Mode
PLAYER:Equipped("Draught of Souls")
```

***


> ## item.cooldown

- Checks the cooldown remaining for the player specific item.
#### Parameters
- `NameOrID`: The item name or ID to check the cooldown for.
#### Returns `NUMBER`
- The remaining cooldown time in `seconds` for the specified item, or 0 if not on cooldown.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "item(Draught of Souls).cooldown >= 20"},

-- in Lua code
_A.DSL:Get("item.cooldown")(_, "Draught of Souls") >= 20

-- Lua Mode
PLAYER:ItemCooldown("Draught of Souls") >= 20
```

***


> ## item.usable

- Checks if a specific item is usable by the player.
#### Parameters
- `NameOrID`: The item name or ID to check for usability.
#### Returns `BOOL`
- `true` if the item is usable, `false` otherwise.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "item(Draught of Souls).usable >= 20"},

-- in Lua code
_A.DSL:Get("item.usable")(_, "Draught of Souls") >= 20

-- Lua Mode
PLAYER:ItemUsable("Draught of Souls") >= 20
```

***


> ## item.count

- Checks the count of a specific item in the player's bags.
#### Parameters
- `NameOrID`: The item name or ID to check the count of.
#### Returns `NUMBER`
- The count of the specified item in the player's bags.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "item(Healthstone).count > 0"},

-- in Lua code
_A.DSL:Get("item.count")(_, "Healthstone") > 0

-- Lua Mode
PLAYER:ItemCount("Healthstone") > 0
```

***


> ## item.range

- Checks if the player's target is within range of using a specific item.
#### Parameters
- `NameOrID`: The item name or ID to check the range for.
#### Returns `BOOL`
- `true` if the player's target is within range of using the item, `false` otherwise.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "item(Sunblood Amethyst).range"},

-- in Lua code
_A.DSL:Get("item.range")(_, "Sunblood Amethyst")

-- Lua Mode
PLAYER:ItemRange("Sunblood Amethyst")
```

***


> ## ilevel

- Returns the average item level of the player.
#### Returns `NUMBER`
- The average item level of the player.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "ilevel >= 240"},

-- in Lua code
_A.DSL:Get("ilevel")() >= 240

-- Lua Mode
PLAYER:Ilevel() >= 240
```

***


> ## twohand

- Checks if the player has a two-handed weapon equipped.
#### Returns `BOOL`
- `true` if the player has a two-handed weapon equipped, `false` otherwise.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "twohand"},

-- in Lua code
_A.DSL:Get("twohand")()

-- Lua Mode
PLAYER:Twohand()
```

***


> ## onehand

- Checks if the player has a one-handed weapon equipped.
#### Returns `BOOL`
- `true` if the player has a one-handed weapon equipped, `false` otherwise.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "onehand"},

-- in Lua code
_A.DSL:Get("onehand")()

-- Lua Mode
PLAYER:Onehand()
```

***


> ## tier

- Returns the number of equipped items from a specific tier set for the player's class.
#### Parameters
- `Tnum`: The tier set number (e.g., `"T18", "T19", "T20", etc`).
#### Returns `NUMBER`
- The number of equipped items from the specified tier set for the player's class.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "tier(T20) >= 2"},

-- in Lua code
_A.DSL:Get("tier")(_, "T20") >= 2

-- Lua Mode
PLAYER:Tier("T20") >= 2
```
