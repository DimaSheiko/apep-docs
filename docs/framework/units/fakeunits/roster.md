# ROSTER

---

> ## roster

-   This fake unit retrieves the list of units in the roster.

#### Returns `TABLE`

-   Returns a table indexed by GUID, containing the friendly units.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "roster"},
    ```

=== "Lua Code"

    ```lua
    local roster = Object("roster") or {}
    for _, Obj in pairs(roster) do
        print(Obj:Distance()) -- (1)!
    end
    ```

    1. Do something with the object

---

> ## lowest

-   This fake unit retrieves the lowest health unit in the roster, optionally filtered by role.

#### Parameters

-   `STRING(Optional)`: The role to filter by.

#### Returns `guid/key`

-   Returns the lowest health roster.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "lowest"},
    ```

=== "Lua Code"

    ```lua
    local lowest = Object("lowest")
    if lowest then
        print(lowest.name) -- (1)!
    end
    ```

    1. Do something with the lowest object

---

> ## lowestRange

-   This fake unit retrieves the lowest health unit in the roster within a specified range.

#### Parameters

-   `NUMBER`: The maximum range to consider for the units.

#### Returns `guid/key`

-   Returns the lowest health roster within a specified range.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "lowestRange(20)"},
    ```

=== "Lua Code"

    ```lua
    local lowest20 = Object("lowestRange(20)")
    if lowest20 then
        print(lowest20.name) -- (1)!
    end
    ```

    1. Do something with the lowest20 object

---

> ## lowestPet

-   This fake unit retrieves the lowest health non-player unit (pet) in the roster.

#### Returns `guid/key`

-   Returns the lowest unit (pet) in the roster.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "lowestPet"},
    ```

=== "Lua Code"

    ```lua
    local lowestPet = Object("lowestPet")
    if lowestPet then
        print(lowestPet.name) -- (1)!
    end
    ```

    1. Do something with the lowestPet object

---

> ## lowestpredicted | lowestp

-   This fake unit retrieves the lowest predicted health unit in the roster, optionally filtered by role.

#### Parameters

-   `STRING(Optional)`: The role to filter by.

#### Returns `guid/key`

-   Returns the lowest predicted health roster.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "lowestp"},
    ```

=== "Lua Code"

    ```lua
    local lowestp = Object("lowestp")
    if lowestp then
        print(lowestp.name) -- (1)!
    end
    ```

    1. Do something with the lowestp object

---

> ## lowestbuff | lbuff

-   This fake unit retrieves the lowest health unit in the roster who has a specific buff, optionally filtered by role.

#### Parameters

-   `STRING`: The name of the buff to check for.
-   `STRING(Optional)`: The role to filter by.

#### Returns `guid/key`

-   Returns the lowest health roster who has the specific buff.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "lbuff(Rejuvenation)"},
    ```

=== "Lua Code"

    ```lua
    local lbuff = Object("lbuff(Rejuvenation)")
    if lbuff then
        print(lbuff.name) -- (1)!
    end
    ```

    1. Do something with the lbuff object

---

> ## lowestnotbuff | lnbuff

-   This fake unit retrieves the lowest health unit in the roster who does not have a specific buff, optionally filtered by role.

#### Parameters

-   `STRING`: The name of the buff to check for absence.
-   `STRING(Optional)`: The role to filter by.

#### Returns `guid/key`

-   Returns the lowest health roster who does not have the specific buff.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "lnbuff(Rejuvenation)"},
    ```

=== "Lua Code"

    ```lua
    local lnbuff = Object("lnbuff(Rejuvenation)")
    if lnbuff then
        print(lnbuff.name) -- (1)!
    end
    ```

    1. Do something with the lnbuff object

---

> ## lowestdebuff | ldebuff

-   This fake unit retrieves the lowest health unit in the roster who has a specific debuff, optionally filtered by role.

#### Parameters

-   `STRING`: The name of the debuff to check for.
-   `STRING(Optional)`: The role to filter by.

#### Returns `guid/key`

-   Returns the lowest health roster who has the specific debuff.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "ldebuff(Corruption)"},
    ```

=== "Lua Code"

    ```lua
    local ldebuff = Object("ldebuff(Corruption)")
    if ldebuff then
        print(ldebuff.name) -- (1)!
    end
    ```

    1. Do something with the ldebuff object

---

> ## lowestnotdebuff | lndebuff

-   This fake unit retrieves the lowest health unit in the roster who does not have a specific debuff, optionally filtered by role.

#### Parameters

-   `STRING`: The name of the debuff to check for absence.
-   `STRING(Optional)`: The role to filter by.

#### Returns `guid/key`

-   Returns the lowest health roster who does not have the specific debuff.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "lndebuff(Corruption)"},
    ```

=== "Lua Code"

    ```lua
    local lndebuff = Object("lndebuff(Corruption)")
    if lndebuff then
        print(lndebuff.name) -- (1)!
    end
    ```

    1. Do something with the lndebuff object

---

> ## lowestDebuffType | ldebufft

-   This fake unit retrieves the lowest health unit in the roster who has a specific debuff type.

#### Parameters

-   `STRING`: The name of the debuff type to check for.

#### Returns `guid/key`

-   Returns the lowest health roster who has the specific debuff type.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "ldebufft(Magic)"},
    ```

=== "Lua Code"

    ```lua
    local ldebufft = Object("ldebufft(Magic)")
    if ldebufft then
        print(ldebufft.name) -- (1)!
    end
    ```

    1. Do something with the ldebufft object

---

> ## tank

-   This fake unit retrieves the tank in the roster based on a priority calculated using the maximum health and role multiplier.

#### Returns `guid/key`

-   Returns the tank roster.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "tank1"},
    {ACTION, ACTION, "tank2"},
    ```

=== "Lua Code"

    ```lua
    local tank1 = Object("tank1")
    local tank2 = Object("tank2")
    if tank1 then
        print(tank1.name) -- (1)!
    end
    if tank2 then
        print(tank2.name) -- (2)!
    end
    ```

    1. Do something with the tank1 object
    2. Do something with the tank2 object

---

> ## healer

-   This fake unit retrieves the healer in the roster based on a priority calculated using the current health.

#### Returns `guid/key`

-   Returns the healer roster.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "healer"},
    ```

=== "Lua Code"

    ```lua
    local healer = Object("healer")
    if healer then
        print(healer.name) -- (1)!
    end
    ```

    1. Do something with the healer object

---

> ## damager

-   This fake unit retrieves the damager in the roster based on a priority calculated using the current health.

#### Returns `guid/key`

-   Returns the damager roster.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "damager"},
    ```

=== "Lua Code"

    ```lua
    local damager = Object("damager")
    if damager then
        print(damager.name) -- (1)!
    end
    ```

    1. Do something with the damager object

---

> ## mostTargetedRoster

-   This fake unit retrieves the unit in the roster that is most targeted by enemies.

#### Returns `guid/key`

-   Returns the most targeted unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "mostTargetedRoster"},
    ```

=== "Lua Code"

    ```lua
    local mostT = Object("mostTargetedRoster")
    if mostT then
        print(mostT.name) -- (1)!
    end
    ```

    1. Do something with the mostT object

---

> ## heal_dist_radius_min_avghp

-   This fake unit finds the unit in the roster with the highest number of nearby allies within a certain distance radius and an average health percentage below a specified threshold.

#### Parameters

-   `NUMBER`: The distance to check for.
-   `NUMBER`: The radius to check for.
-   `NUMBER`: The minimum group size.
-   `NUMBER`: The average health in % to check for.
-   `NUMBER(optional, default: 100)`: The individual health threshold for players to be considered for healing.

#### Returns `guid/key`

-   The unit with the most nearby members and whose average health is the lowest percentage.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, CONDITIONS, "heal_dist_radius_min_avghp(40, 10, 4, 60)"}, -- (1)!
    ```

    1. Assumes threshold of 100

        If you want to specify the individual health threshold, use this:
        ```lua
        {ACTION, CONDITIONS, "heal_dist_radius_min_avghp(40, 10, 4, 60, 90)"}, -- (1)!
        ```

        1. 90 Threshold

=== "Lua Code"

    ```lua
    local member = Object("heal_dist_radius_min_avghp(40, 10, 4, 60)") -- (1)!
    if member then
        print(member.name) -- (2)!
    end
    ```

    1. Assumes threshold of 100

        If you want to specify the individual health threshold, use this:

        ```lua
        local member = Object("heal_dist_radius_min_avghp(40, 10, 4, 60, 90)") -- (1)!
        ```

        1. 90 Threshold

    2. Do something with the member object

---
