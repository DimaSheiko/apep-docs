# Create own fakeunit

You can create your own fakeunits by using the `_A.FakeUnits:Add` method.

## Syntax

The basic syntax for creating a fakeunit is as follows:

```lua
_A.FakeUnits:Add('name', function)
```

## Example

```lua
local function GetEnemy(num, near, inCombat)
    local tempTable = {}
    local tbl = inCombat and _A.OM:Get('EnemyCombat') or _A.OM:Get('Enemy')
    for _, Obj in pairs(tbl) do
        if Obj:infront() then
            tempTable[#tempTable+1] = { guid = Obj.guid, distance = Obj:distance() }
        end
    end
    if #tempTable>1 then
        table.sort( tempTable, function(a,b) return near and (a.distance < b.distance) or (a.distance > b.distance) end )
    end
    return tempTable[num] and tempTable[num].guid
end

-- Nearest enemy
_A.FakeUnits:Add('nearEnemy', function(num)
    return GetEnemy(num, true, false)
end)

-- Nearest enemy in combat with the Roster
_A.FakeUnits:Add('nearEnemyCb', function(num)
    return GetEnemy(num, true, true)
end)

-- Farthest enemy
_A.FakeUnits:Add('farEnemy', function(num)
    return GetEnemy(num, false, false)
end)

-- Farthest enemy in combat with the Roster
_A.FakeUnits:Add('farEnemyCb', function(num)
    return GetEnemy(num, false, true)
end)
```
