# CONDITIONS

In DSL mode, Apep already comes with many conditions to facilitate the creation of rotations (Less lines of code and more readable), `CONDITIONS` are the set of rules or criteria that must be met for an action to take place. They provide a way to control when and how an `ACTION` is executed. Let's dive into the syntax and explore examples to better understand the functionality offered by the `CONDITIONS` component.

For example this line:

```lua
{"Soulstone", "!buff", "player"},
```

Creates a soulstone on the player if he doesn't have the soulstone buff.
`buff` is a condition and as you may have noticed there are already a lot of predefined ones.

But if you want to create a custom condition, you already have to do it yourself.
example:

```lua
-- Register a condition named "class".
-- This condition checks if the specified target unit belongs to the expected class.
-- @param target The unit to check for the class.
-- @param expectedClass The expected class name or class ID to compare with.
-- @return `true` if the target unit belongs to the expected class, `false` otherwise.
_A.DSL:Register('class', function (target, expectedClass)
    local class, _, classID = UnitClass(target)
    if tonumber(expectedClass) then
        return tonumber(expectedClass) == classID
    else
        return expectedClass == class
    end
end)
```

And this is pure lua code.

## DLS Syntax

The basic syntax for `CONDITIONS` is encapsulated within curly braces, as part of the `ACTION` structure. It consists of three key elements: `ACTION`, CONDITIONS, and UNIT.

```lua
{ACTION, CONDITIONS, UNIT/FAKEUNIT}
```

Here's a breakdown of each component:

-   **ACTION**: This is the command or operation you want to execute. It could be the name of a spell, a function call, a macro, an item number, or even a reference to a library.

-   **CONDITIONS**: These are the criteria that must be met for the action to take place. Conditions ensure that the action is executed under specific circumstances.

-   **UNIT/FAKEUNIT**: This specifies the target unit for the action. It could be `player`, `target` or any other valid [unit identifier](https://wowpedia.fandom.com/wiki/UnitId) or FakeUnit.

## DLS Examples

```lua
{ACTION, "inmelee && player.buff(Taste for Blood).stack < 3 && spell(Slam).usable", UNIT}
```

This example represents a conditional spell casting action. Replace the text within the quotation marks with the name of the desired conditions. Define your specific [ACTION](../actions/index.md) and `UNIT` accordingly.

```lua
{ACTION, "player.buff(Bloodlust).any", UNIT}
```

```lua
{ACTION, "player.buff(Bloodlust).any || player.buff(Heroism).any", UNIT}
```

```lua
{ACTION, "inmelee && rage > 80", UNIT}
```
