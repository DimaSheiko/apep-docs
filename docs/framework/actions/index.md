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

Executes a spell cast. Replace `Charge` with the desired spell name. The spell will be cast on the specified UNIT when CONDITIONS are met.

### Items

#### Equipment Slots

```lua
{"#trinket1", CONDITIONS, UNIT}
{"#trinket2", CONDITIONS, UNIT}
{"#neck", CONDITIONS, UNIT}
{"#waist", CONDITIONS, UNIT}
{"#hands", CONDITIONS, UNIT}
```

Uses equipped items from specific slots. The `#` prefix indicates an equipment slot. Available slots include: `trinket1`, `trinket2`, `neck`, `waist`, `hands`, and other valid equipment slots.

#### Ground Targeting

```lua
{"#waist", CONDITIONS, "target.ground"}
```

For items that require ground targeting (like engineering belt), use `.ground` suffix on the UNIT parameter.

### Library Calls

```lua
{"@LibraryName.FunctionName(arguments)", CONDITIONS, UNIT}
```

Calls registered library functions using the `@` prefix. Libraries must be registered using `_A.Library:Add()` before use.

**Example:**

```lua
{"@Prot.Use(Health Stones)", CONDITIONS, "player"}
{"@Prot.PickupHS(unit)", CONDITIONS, "objectID(193169)"}
```

### Macros

#### Basic Macros

```lua
{"/cast xxxxxxx", CONDITIONS, UNIT}
```

Casts a spell using macro syntax. Replace "xxxxxxx" with the spell name.

```lua
{"/use xxxxxxx", CONDITIONS, UNIT}
```

Uses an item by name or item ID.

#### Combat Control

```lua
{"/startattack", CONDITIONS, UNIT}
{"/stopattack", CONDITIONS, UNIT}
```

Controls auto-attack behavior. Use `/startattack` to begin auto-attacking and `/stopattack` to halt it.

### Special Commands

Commands using the `%` prefix provide special functionality:

#### Target Management

```lua
{"%target", CONDITIONS, UNIT}
```

Changes the current target to the specified UNIT.

#### Pause Rotation

```lua
{"%pause", nil}
```

Temporarily pauses the rotation execution. Useful when specific conditions require stopping all actions.

#### Cancel Buffs

```lua
{"%cancelbuff(Buff Name)", CONDITIONS, "player"}
{"%cancelbuff(Power Word: Shield)", CONDITIONS, "player"}
```

Removes a specific buff from the target. Commonly used to cancel absorb shields or other buffs that may interfere with mechanics.

### Function Call

```lua
{function()
  _A.CastSpellByName("Mangle", "target")
end, CONDITIONS, UNIT}
```

For complex actions, use Lua functions. This allows custom logic and multiple operations within a single action.

**Example:**

```lua
{function()
  if UnitHealth("player") < 50 then
    _A.CastSpellByName("Shield Wall", "player")
  end
end, "spell.ready", "player"}
```

## Advanced Patterns

### Nested Actions

Actions can be nested to create complex conditional structures:

```lua
{{
  {"Execute", "health<=20", "target"},
  {"Mortal Strike", "spell.ready", "target"}
}, "player.incombat && target.WarriorMelee"}
```

The outer condition must be met, then each inner action is evaluated with its own conditions.

### Multiple Actions with Shared Conditions

```lua
{{
  {"Battle Shout", "!buff(Battle Shout).any", "player"},
  {"Commanding Shout", "!buff(Commanding Shout).any", "player"}
}, "ui(shoutslist)>0"}
```

All actions in the group share the outer condition, reducing redundancy.

## Conclusion

The `ACTION` component is the backbone of your scripts, providing diverse execution methods from simple spell casting to complex library calls and special commands. Use this documentation as your guide to crafting powerful and efficient scripts for your projects.
