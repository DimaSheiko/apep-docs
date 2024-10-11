---
icon: material/function
---

# ACTIONS

In the world of scripting, an `ACTION` represents the core command or operation you want to perform. It can be a spell, a function call, a macro, or any other executable unit. Let's dive into the syntax and explore examples to better grasp the flexibility and functionality offered by the `ACTION` component.

## Syntax

The basic syntax for an `ACTION` is encapsulated within curly braces, with three key elements: `ACTION`, CONDITIONS, and UNIT.

```lua
{ACTION, CONDITIONS, UNIT/FAKEUNIT}
```

Here's a breakdown of each component:

-   **ACTION**: This is the command or operation you want to execute. It could be the name of a spell, a function call, a macro, an item number, or even a reference to a library.

-   **CONDITIONS**: These are the criteria that must be met for the action to take place. Conditions ensure that the action is executed under specific circumstances.

-   **UNIT/FAKEUNIT**: This specifies the target unit for the action. It could be `player`, `target` or any other valid [unit identifier](https://wowpedia.fandom.com/wiki/UnitId) or FakeUnit.

## Examples

### Spell

```lua
{"Charge", CONDITIONS, UNIT}
```

This example represents a spell casting action. Replace `Charge` with the name of the desired spell. Define your specific conditions and target unit accordingly.

### Macro

```lua
{"/cast xxxxxxx", CONDITIONS, UNIT}
```

This example represents a spell casting action. Replace "xxxxxxx" with the name of the desired spell. Define your specific conditions and target unit accordingly.

```lua
{"/use xxxxxxx", CONDITIONS, UNIT}
```

Here, the action involves using an item with the specified item number. Customize the item number, conditions, and target unit based on your requirements.

### Function Call

```lua
{function()
  _A.CastSpellByName("Mangle", "target")
end, CONDITIONS, UNIT}
```

For more complex actions, you can use a Lua function. This example demonstrates a function that casts the spell "Mangle" on the target. Customize the function, conditions, and target unit to suit your scripting requirements.

## Conclusion

The `ACTION` component is the backbone of your scripts, allowing you to perform a wide range of actions, from simple spell casting to intricate function calls. Use this documentation as your guide to crafting powerful and efficient scripts for your projects.
