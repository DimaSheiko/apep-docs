# FRIENDLY

---

> ## friends

-   This fake unit retrieves a list of friendly units from the Object Manager.

#### Returns `TABLE`

-   Returns a table indexed by GUID, containing the friendly units.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "friends"},
    ```

=== "Lua Code"

    ```lua
    local friends = Object("friends") or {}
    for _, Obj in pairs(friends) do
        print(Obj:Distance()) -- (1)!
    end
    ```

    1. Do something with the object

---

> ## friendlyName

-   This fake unit finds a friendly unit with a specific name.

#### Parameters

-   `STRING`: The name of the friendly unit to search for.

#### Returns `guid/key`

-   Returns the friendly unit with the specified name.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "friendlyName(unit_name)"},
    ```

=== "Lua Code"

    ```lua
    local friend = Object("friendlyName(unit_name)")
    if friend then
        print(friend.id) -- (1)!
    end
    ```

    1. Do something with the friend unit

---

> ## friendlyID

-   This fake unit finds a friendly unit with a specific id.

#### Parameters

-   `NUMBER`: The id of the friendly unit to search for.

#### Returns `guid/key`

-   Returns the friendly unit with the specified id.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "friendlyID(12345)"},
    ```

=== "Lua Code"

    ```lua
    local friend = Object("friendlyID(12345)")
    if friend then
        print(friend.name) -- (1)!
    end
    ```

    1. Do something with the friend unit

---

> ## totemID

-   This fake unit finds a friendly totem with a specific id created by the player.

#### Parameters

-   `NUMBER`: The id of the player totem to search for.

#### Returns `guid/key`

-   Returns the friendly totem created by the player with the specified id.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "totemID(8888)"},
    ```

=== "Lua Code"

    ```lua
    local totem = Object("totemID(8888)")
    if totem then
        print(totem.name) -- (1)!
    end
    ```

    1. Do something with the totem object

---

> ## totemName

-   This fake unit finds a friendly totem with a specific name created by the player.

#### Parameters

-   `STRING`: The name of the totem to search for.

#### Returns `guid/key`

-   Returns the friendly totem created by the player with the specified name.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, ACTION, "totemName(totem_name)"},
    ```

=== "Lua Code"

    ```lua
    local totem = Object("totemName(totem_name)")
    if totem then
        print(totem.name) -- (1)!
    end
    ```

    1. Do something with the totem object

---
