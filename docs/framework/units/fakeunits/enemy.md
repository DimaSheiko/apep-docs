# ENEMY

---

> ## enemies

-   This fake unit retrieves a list of enemy units from the Object Manager.

#### Returns `TABLE`

-   Returns a table indexed by GUID, containing the enemy units.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "enemies"},
    ```

=== "Lua Code"

    ```lua
    local enemies = Object("enemies") or {}
    for _, Obj in pairs(enemies) do
        print(Obj:Distance()) -- (1)!
    end
    ```

    1. Do something with the object

---

> ## nearEnemy

-   This fake unit finds the nearest enemy that is also in front of the player.

#### Returns `guid/key`

-   Returns the nearest enemy in front of the player.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "nearEnemy"},
    ```

=== "Lua Code"

    ```lua
    local nearE = Object("nearEnemy")
    if nearE then
        print(nearE.name) -- (1)!
    end
    ```

    1. Do something with the nearE object

---

> ## enemyID

-   This fake unit finds enemies with a specific ID.

#### Parameters

-   `NUMBER`: The id of the enemy to search for.

#### Returns `guid/key`

-   Returns the enemy with the specified ID that is closest in distance.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "enemyID(12345)"},
    ```

=== "Lua Code"

    ```lua
    local enemy = Object("enemyID(12345)")
    if enemy then
        print(enemy.name) -- (1)!
    end
    ```

    1. Do something with the enemy object

---

> ## lowestEnemyInRange

-   This fake unit finds the lowest health enemy within a specified range from a target.

#### Parameters

-   `NUMBER`: The range to compare.
-   `STRING`: The unit with which to compare the range.

#### Returns `guid/key`

-   Returns the lowest health enemy within the specified range of the unit.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "lowestEnemyInRange(40, player)"},
    ```

=== "Lua Code"

    ```lua
    local lowestEnemy40 = Object("lowestEnemyInRange(40, player)")
    if lowestEnemy40 then
        print(lowestEnemy40.name) -- (1)!
    end
    ```

    1. Do something with the lowestEnemy40 object

---

> ## enemyTotemID

-   This fake unit finds enemies (totems) with a specific ID.

#### Parameters

-   `NUMBER`: The id of the enemy (totem) to search for.

#### Returns `guid/key`

-   Returns the enemy (totem) with the specified ID.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "enemyTotemID(8888)"},
    ```

=== "Lua Code"

    ```lua
    local totem = Object("enemyTotemID(8888)")
    if totem then
        print(totem.name) -- (1)!
    end
    ```

    1. Do something with the totem object

---

> ## enemyTotemName

-   This fake unit finds enemies (totems) based on their name.

#### Parameters

-   `STRING`: The name of the enemy (totem) to search for.

#### Returns `guid/key`

-   Returns the enemy (totem) with the specified name.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "enemyTotemName(totem_name)"},
    ```

=== "Lua Code"

    ```lua
    local totem = Object("enemyTotemName(totem_name)")
    if totem then
        print(totem.name) -- (1)!
    end
    ```

    1. Do something with the totem object

---
