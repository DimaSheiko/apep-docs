# Getting Started

Apep consists of an _internal API_ and a _Lua-based framework_.

-   The _internal API_ is the foundation of Apep's core. It includes functions that work directly with the game and perform complex tasks. This API supports communication between the Lua framework and the game.

-   The _Lua-based framework_ is like a user-friendly layer above the core. It lets developers use Apep's features without dealing with complex code. This simplifies unlocking advanced features, so developers can focus on their application's logic.

## Understanding apep

**The Apep framework provides users with two distinct modes for performing rotations: `DSL` and `Lua`.**

-   In the `DSL mode`, users can define rotations using a _DSL(domain-specific language specifically)_ designed for expressing rotation logic. This mode simplifies the process of creating complex rotation sequences by offering a streamlined syntax tailored to rotation-related tasks.

-   The `Lua mode` allows users to harness the power and flexibility of the Lua scripting language to define rotations. This mode is particularly useful for users who are already familiar with Lua or require a high degree of customization and fine-tuning in their rotation logic.

!!! info "You should know!"

    Both modes are designed to accommodate different user preferences and skill levels.
    `DSL mode` prioritizes _simplicity_ and ease of use.
    `Lua mode` empowers _advanced users_ with more control.
    Users can choose between these modes based on their requirements, allowing for a versatile and adaptable rotation experience.

## DSL mode:

Apep makes use of a custom DLS (Domain-Specific Language).
Apep DSL was inspired by how Probably Engine used to work, it remains as simple but alot more powerfull.
DSL line (Basic structure):

```lua
{"ACTION", "CONDITION", "UNIT"},

```

| index | name                                       |
| :---: | ------------------------------------------ |
|   1   | [ACTION](framework/actions/index.md)       |
|   2   | [CONDITION](framework/conditions/index.md) |
|   3   | [UNIT](framework/units/index.md)           |

## Lua mode example:

```lua
local player = Unit('player')

print(player:Name())
```
