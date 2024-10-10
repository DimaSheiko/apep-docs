# ARTIFACTS
---


> ## artifact.enabled

- This condition checks if a specific artifact trait is enabled for a given spell.

#### Parameters
- `spell`: The spell for which to check if the artifact trait is enabled.

#### Returns `BOOL`
- `true` if the artifact trait is enabled for the spell, `false` otherwise.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "artifact(Dragon Scales).enabled"},

-- in Lua code
_A.DSL:Get("artifact.enabled")(_, "Dragon Scales")

-- Lua Mode
PLAYER:ArtifactEnabled("Dragon Scales")
```

***


> ## artifact.acquired_power

- This condition returns the amount of acquired artifact power for a specific artifact by its ID.

#### Parameters
- `artifactID`: The ID of the artifact for which to retrieve the acquired artifact power.

#### Returns `NUMBER`
- The amount of acquired artifact power for the specified artifact.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "artifact(128289).acquired_power"},

-- in Lua code
_A.DSL:Get("artifact.acquired_power")(_, "128289")

-- Lua Mode
PLAYER:ArtifactAcquired_power(128289)
```

***


> ## artifact.active_id

- This condition returns the ID of the currently active artifact.

#### Returns `NUMBER`
- The ID of the currently active artifact.

#### *Example:*
```lua
-- DSL Mode
N/A

-- in Lua code
_A.DSL:Get("artifact.active_id")()

-- Lua Mode
PLAYER:ArtifactActive_id()
```

***


> ## artifact.knowledge

- This condition returns the amount of artifact knowledge the player has.

#### Returns `NUMBER`
- The amount of artifact knowledge.

#### *Example:*
```lua
-- DSL Mode
N/A

-- in Lua code
_A.DSL:Get("artifact.knowledge")()

-- Lua Mode
PLAYER:ArtifactKnowledge()
```

***


> ## artifact.power

- This condition returns the artifact power of a specific artifact.

#### Parameters
- `artifactID`: The ID of the artifact.

#### Returns `NUMBER`
- The artifact power of the specified artifact.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "artifact(93).power"},

-- in Lua code
_A.DSL:Get("artifact.power")(_, "93")

-- Lua Mode
PLAYER:ArtifactPower(93)
```

***


> ## artifact.relics

- This condition returns the relics of a specific artifact.

#### Parameters
- `artifactID`: The ID of the artifact.

#### Returns `TABLE`
- The relics associated with the specified artifact.

#### *Example:*
```lua
-- DSL Mode
N/A

-- in Lua code
local artifactTable = _A.DSL:Get("artifact.relics")(_, "128289")

-- Lua Mode
local artifactTable = PLAYER:ArtifactRelics(128289)
```


***


> ## artifact.num_obtained

- This condition returns the number of obtained artifacts.

#### Returns `NUMBER`
- The number of artifacts obtained by the player.

#### *Example:*
```lua
-- DSL Mode
N/A

-- in Lua code
_A.DSL:Get("artifact.num_obtained")()

-- Lua Mode
PLAYER:ArtifactNum_obtained()
```
