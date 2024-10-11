# TALENTS

---

> ## talent

-   This condition checks if the specified talent is active on the player.

#### Returns `BOOL`

-   `true` if the specified talent is active, `false` otherwise.

#### _Example:_

```lua
-- DSL Mode
{ACTION, "talent(Avatar)"},

-- in Lua code
_A.DSL:Get("talent")(_, "Avatar")

-- Lua Mode
PLAYER:Talent("Avatar")
```
