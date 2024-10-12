# ENEMY COMBAT

---

> ## enemiesCombat

-   This fakeunit retrieves a list of enemies that are in combat with the roster.

#### Returns `TABLE`

-   Returns a table indexed by GUID, containing the enemy units in combat with the roster.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "enemiesCombat"},
    ```

=== "Lua Code"

    ```lua
    local enemiesCb = Object("enemiesCombat") or {}
    for _, Obj in pairs(enemiesCb) do
        print(Obj:Distance())
    end
    ```

---

> ## lowestenemy | loweste | le

-   This fakeunit retrieves the lowest health enemy in combat with the roster.

#### Returns `guid/key`

-   Returns the lowest health enemy in combat with the roster.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "lowestenemy"},
    ```

=== "Lua Code"

    ```lua
    local lowestE = Object("lowestenemy")
    if lowestE then
        print(lowestE.name)
    end
    ```

---

> ## enemybuff | ebuff

-   This fakeunit retrieves an enemy in combat with the roster that has a specific buff.

#### Parameters

-   `STRING/NUMBER`: The name or id of the buff to check for.

#### Returns `guid/key`

-   Returns the guid/key of the specified enemy in combat with the given buff.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "enemybuff(name_of_the_buff)"},
    ```

=== "Lua Code"

    ```lua
    local enemyB = Object("enemybuff(name_of_the_buff)")
    if enemyB then
        print(enemyB.name)
    end
    ```

---

> ## enemynbuff | enbuff

-   This fakeunit retrieves an enemy in combat with the roster that does not have a specific buff.

#### Parameters

-   `STRING/NUMBER`: The name or id of the buff to check for absence.

#### Returns `guid/key`

-   Returns the guid/key of the specified enemy in combat without the given buff.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "enemynbuff(name_of_the_buff)"},
    ```

=== "Lua Code"

    ```lua
    local enemyNB = Object("enemynbuff(name_of_the_buff)")
    if enemyNB then
        print(enemyNB.name)
    end
    ```

---

> ## enemyDebuff | edebuff

-   This fakeunit retrieves an enemy in combat with the roster that has a specific player debuff.

#### Parameters

-   `STRING/NUMBER`: The name or id of the player debuff to check for.

#### Returns `guid/key`

-   Returns the guid/key of the specified enemy in combat with the given player debuff.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "enemyDebuff(Corruption)"},
    ```

=== "Lua Code"

    ```lua
    local enemyD = Object("enemyDebuff(Corruption)")
    if enemyD then
        print(enemyD.name)
    end
    ```

---

> ## enemyNotDebuff | endebuff

-   This fakeunit retrieves an enemy in combat with the roster that does not have a specific player debuff.

#### Parameters

-   `STRING/NUMBER`: The name or id of the player debuff to check for absence.

#### Returns `guid/key`

-   Returns the guid/key of the specified enemy in combat without the given player debuff.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "enemyNotDebuff(Corruption)"},
    ```

=== "Lua Code"

    ```lua
    local enemyND = Object("enemyNotDebuff(Corruption)")
    if enemyND then
        print(enemyND.name)
    end
    ```

---

> ## nearEnemyCb

-   This fakeunit retrieves the nearest enemy in combat with the roster who is also in front.

#### Returns `guid/key`

-   Returns the nearest enemy in combat with the roster who is also in front.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "nearEnemyCb"},
    ```

=== "Lua Code"

    ```lua
    local nearECb = Object("nearEnemyCb")
    if nearECb then
        print(nearECb.name)
    end
    ```

---

> ## enemyCombatID

-   This fakeunit finds enemies in combat with the roster based on their ids.

#### Parameters

-   `NUMBER`: The id of the enemy to search for.

#### Returns `guid/key`

-   Returns the enemy in combat with the roster with the specified id that is closest in distance.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "enemyCombatID(12345)"},
    ```

=== "Lua Code"

    ```lua
    local enemyCb = Object("enemyCombatID(12345)")
    if enemyCb then
        print(enemyCb.name)
    end
    ```

---

> ## bestCandidateForAggro

-   This fakeunit finds the best candidate for casting a specific aggro-inducing spell, based on the threat percentage.

#### Parameters

-   `STRING`: The aggro-inducing spell to check.

#### Returns `guid/key`

-   Returns the best candidate for casting the specified aggro-inducing spell, based on the threat percentage.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "bestCandidateForAggro(Taunt)"},
    ```

=== "Lua Code"

    ```lua
    local bestCand = Object("bestCandidateForAggro(Taunt)")
    if bestCand then
        print(bestCand.name)
    end
    ```
