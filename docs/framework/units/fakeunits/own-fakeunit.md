# Create own fakeunit

You can create your own fakeunits by using the `_A.FakeUnits:Add` method. This allows for highly customized unit selections tailored to specific rotation logic.

## Syntax

The basic syntax for creating a fakeunit is as follows:

```lua
_A.FakeUnits:Add('name', function)
```

-   `'name'`: A unique string identifier for your fakeunit. You will use this name in your rotations (e.g., `needTaunt.cast`).
-   `function`: The Lua function that will be executed to determine the unit. This function should return the GUID of the selected unit, or `nil` if no suitable unit is found.

## Example

This example demonstrates how to create a set of fakeunits for selecting enemies based on their distance and combat status.

```lua
-- A helper function to find an enemy based on criteria.
-- @param num: The index of the enemy to return (e.g., 1 for the closest, 2 for the second closest).
-- @param near: If true, sorts by nearest distance. If false, sorts by farthest.
-- @param inCombat: If true, only considers enemies in combat. If false, considers all enemies.
local function GetEnemy(num, near, inCombat)
    local tempTable = {}
    -- Decide which object list to use: all enemies or only those in combat.
    local tbl = inCombat and _A.OM:Get('EnemyCombat') or _A.OM:Get('Enemy')

    -- Iterate through the list of enemies.
    for _, Obj in pairs(tbl) do
        -- For this example, we only want enemies that are in front of the player.
        if Obj:infront() then
            -- Store the enemy's GUID and distance for sorting.
            tempTable[#tempTable+1] = { guid = Obj.guid, distance = Obj:distance() }
        end
    end

    -- If there's more than one candidate, sort them.
    if #tempTable > 1 then
        -- Sort by distance, ascending (nearest) or descending (farthest).
        table.sort( tempTable, function(a,b) return near and (a.distance < b.distance) or (a.distance > b.distance) end )
    end

    -- Return the GUID of the enemy at the requested index.
    -- If the index is out of bounds, it will return nil.
    return tempTable[num] and tempTable[num].guid
end

-- Register the fakeunits using the helper function.
-- (1) Nearest enemy
_A.FakeUnits:Add('nearEnemy', function(num)
    return GetEnemy(num, true, false)
end)

-- (2) Nearest enemy that is in combat with the Roster
_A.FakeUnits:Add('nearEnemyCb', function(num)
    return GetEnemy(num, true, true)
end)

-- (3) Farthest enemy
_A.FakeUnits:Add('farEnemy', function(num)
    return GetEnemy(num, false, false)
end)

-- (4) Farthest enemy that is in combat with the Roster
_A.FakeUnits:Add('farEnemyCb', function(num)
    return GetEnemy(num, false, true)
end)
```

### Advanced Example: `needTaunt`

This more complex example creates a fakeunit that identifies enemies which require a taunt. It's useful for tank rotations to ensure threat is maintained on all targets.

```lua
local _, _A = ... -- Ensure APEP is loaded

-- Registers a "fake unit" named "needTaunt" with the APEP framework.
-- This function identifies enemy combatants that are not currently being tanked by the player
-- and are within range and line of sight of a specified taunt spell.
-- It returns the GUID of the Nth closest such enemy.
_A.FakeUnits:Add("needTaunt", function(targetIndex, tauntSpell)
    local potentialTauntTargets = {}

    -- Iterate through all known enemies.
    for _, enemy in pairs(_A.OM:Get("Enemy")) do
        -- Filter out players and pets to focus on NPC mobs.
        -- Then, check if the enemy is in combat, within spell range, and has line of sight.
        if not enemy.isplayer and not enemy:Ispet() and enemy:Combat() and enemy:spellRange(tauntSpell) and enemy:los() then
            -- Determine if the player is currently the primary threat target for this enemy.
            -- _A.UnitDetailedThreatSituation returns true if the player is tanking, false otherwise.
            local isPlayerTanking = _A.UnitDetailedThreatSituation("player", enemy.guid)
            if not isPlayerTanking then
                -- If the player is not tanking this enemy, add it to our list of potential taunt targets.
                potentialTauntTargets[#potentialTauntTargets + 1] = {
                    guid = enemy.guid,
                    distance = enemy:distance()
                }
            end
        end
    end

    -- If there's more than one potential target, sort them by distance (closest first).
    if #potentialTauntTargets > 1 then
        table.sort(potentialTauntTargets, function(a, b) return a.distance < b.distance end)
    end

    -- Return the GUID of the enemy at the specified index (e.g., 1st, 2nd closest).
    -- If the `targetIndex` is out of bounds (e.g., asking for the 3rd target when only 2 exist),
    -- it will return nil.
    return potentialTauntTargets[targetIndex] and potentialTauntTargets[targetIndex].guid
end)
```

In this advanced example, the `needTaunt` fakeunit takes two arguments:
-   `targetIndex`: The index of the desired target from the sorted list (e.g., `1` for the closest enemy needing a taunt).
-   `tauntSpell`: The spell ID or name of the taunt ability, used to check `spellRange`.

This allows for very specific and dynamic unit selection, such as casting a taunt on the second closest enemy that is out of the player's threat range: `needTaunt(2, 355).cast`.
