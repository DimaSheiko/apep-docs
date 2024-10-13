# My First Rotation

## Introduction

This guide will walk you through creating a basic rotation using Apep. A rotation helps in automating actions based on certain conditions. Below is an example script written in Lua to set up and customize a combat rotation.

First let create the file in the `ApepFolder/rotations/Hunter/Survival.lua` Make sure to change the file name to match your spec

!!! warning "Different Path for Legion Client"

    In legion versions you need to use the `Rotations` folder in the Apofis addon folder

=== "DSL"

    ```lua
    local _, _A = ...

    local inCombat = {
        {"%target", "!target.exists || target.dead", "nearEnemyCb"},
        {"Serpent Sting", "spell.ready && spell.range && !debuff", "target"},
        {"Explosive Shot", "spell.ready && spell.range", "target"},
    }

    _A.CR:Add(255, { -- (1)!
        name = "Survival Hunter PVE",
        ic = inCombat,
        wow_ver = "5.4.8", -- (2)!
        apep_ver = "1.1",
    })
    ```

    1. Change to your spec, you can find number in rotation folder
        ![Class Spec Table](../../assets/images/framework/Class_Spec_Table.png)
    2. Change to your wow client version

=== "Lua Code"

    ```lua
    local _, _A = ...

    local inCombat = function()
        local player = Object("player")
        if not player then return end
        local target = Object("target")
        local nearEnemyCb = Object("nearEnemyCb")

        if nearEnemyCb and not target or target and target:dead() then
            nearEnemyCb:target()
        end

        if not target then return end

        if player:CanCast("Serpent Sting") and IsSpellInRange("Serpent Sting", target) == 1 and not player:buff("Serpent Sting") then
            target:Cast("Serpent Sting")
        end

        if player:CanCast("Explosive Shot") and IsSpellInRange("Explosive Shot", target) == 1 then
            target:Cast("Explosive Shot")
        end
    end

    _A.CR:Add(255, { -- (1)!
        name = "Survival Hunter PVE",
        ic = inCombat,
        wow_ver = "5.4.8", -- (2)!
        apep_ver = "1.1",
    })
    ```

    1. Change to your spec, you can find number in rotation folder
        ![Class Spec Table](../../assets/images/framework/Class_Spec_Table.png)
    2. Change to your wow client version

### Key Components

-   **Initialization**: Begin by initializing the `mediaPath` and `_A` variables. Then, define a `DSL` function to interact with the API.
-   **Combat Actions (`inCombat`)**: Define actions to perform in combat. These actions are conditional; for example, `Serpent Sting` is cast if it's ready, within range, and not already applied as a debuff.
-   **Configuration**: Add your rotation using `_A.CR:Add`. Specify your spec ID and modify the `name`, `wow_ver`, and `apep_ver` according to your setup.

This basic structure can be modified further to suit different specs and conditions. Be sure to check the rotation folder for more specific spec numbers and adjust the World of Warcraft and Apep versions as your configurations evolve.

### More Examples

For more examples the comunity has created, check out the discord server for more information.
