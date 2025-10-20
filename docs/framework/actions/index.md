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

## Action Modifiers

Action modifiers are special prefixes that alter the behavior of how actions are executed. These modifiers provide fine-grained control over spell casting, queueing, and interruption.

### Clip Action (!)

```lua
{"!Pyroblast", CONDITIONS, UNIT}
```

Forces the action to interrupt the current cast if one exists. Useful for prioritizing high-priority spells over lower-priority ongoing casts.

**Example:**

```lua
{"!Pyroblast", "buff(Hot Streak)", "target"}
```

This will interrupt any current cast to immediately execute Pyroblast when Hot Streak is active.

### Cast While Casting (*)

```lua
{"*Fire Blast", CONDITIONS, UNIT}
```

Allows the spell to be cast while casting other spells. Typically used for instant-cast spells that can be weaved during other casts.

**Example:**

```lua
{"*Fire Blast", "spell.ready && target.distance<=40", "target"}
```

### No GCD Spell (&)

```lua
{"&Blood Fury", CONDITIONS, UNIT}
```

Marks the action as not triggering the Global Cooldown (GCD). Used for abilities and items that can be used without waiting for or triggering the GCD.

**Example:**

```lua
{"&#trinket1", "buff(Bloodlust)", "player"}
```

Uses trinket 1 without triggering the GCD, allowing it to be used between other abilities.

### Queue Spell (>)

```lua
{">Frostbolt", CONDITIONS, UNIT}
```

Queues the spell to be cast next. Useful for ensuring smooth spell queueing and preventing casting delays.

**Example:**

```lua
{">Frostbolt", "!player.moving", "target"}
```

### User Macro (/)

```lua
{"/cast SpellName", CONDITIONS, UNIT}
{"/use ItemName", CONDITIONS, UNIT}
```

Executes a WoW macro command. Any valid slash command can be used.

**Examples:**

```lua
{"/cast Charge", CONDITIONS, UNIT}
{"/use 13", CONDITIONS, UNIT}
{"/startattack", "target.exists && target.enemy", "target"}
{"/stopattack", CONDITIONS, UNIT}
{"/stopcasting", "player.moving", nil}
```

Use `/startattack` to begin auto-attacking and `/stopattack` to halt it.

### User Library (@)

```lua
{"@LibraryName.FunctionName(arguments)", CONDITIONS, UNIT}
```

Executes a registered user library function. Libraries provide reusable functionality across rotations and must be registered using `_A.Library:Add()` before use.

**Examples:**

```lua
{"@Prot.Use(Health Stones)", "health<50", "player"}
{"@Prot.PickupHS(unit)", CONDITIONS, "objectID(193169)"}
{"@Utils.InterruptTarget()", "target.casting", "target"}
```

### Item Usage (#)

```lua
{"#12345", CONDITIONS, UNIT}
{"#trinket1", CONDITIONS, UNIT}
```

Uses an item by ID or equipment slot name. Available slots include: `trinket1`, `trinket2`, `neck`, `waist`, `hands`, and other valid equipment slots.

**Examples:**

```lua
{"#trinket1", "cooldown(trinket1)==0", "player"}
{"#110560", nil, "player"}
{"#waist", CONDITIONS, "target.ground"}
```

For items that require ground targeting (like engineering belt), use `.ground` suffix on the UNIT parameter.

### Special Commands (%)

Executes special rotation control commands using the `%` prefix.

#### Pause Rotation

```lua
{"%pause", nil}
```

Temporarily pauses the rotation execution. Useful when specific conditions require stopping all actions.

#### Target Management

```lua
{"%target", CONDITIONS, UNIT}
```

Changes the current target to the specified UNIT.

**Example:**

```lua
{"%target", "ui(autotarget)==1", "focustarget"}
```

#### Cancel Buffs

```lua
{"%cancelbuff(Buff Name)", CONDITIONS, UNIT}
```

Removes a specific buff from the target. Commonly used to cancel absorb shields or other buffs that may interfere with mechanics.

**Examples:**

```lua
{"%cancelbuff(Power Word: Shield)", CONDITIONS, "player"}
{"%cancelbuff(Divine Shield)", "debuff(Forbearance)", "player"}
```

### Combining Modifiers

Multiple modifiers can be combined to create sophisticated action behaviors:

```lua
{"!*Fire Blast", CONDITIONS, UNIT}
```

This action will both interrupt current casts and can be cast while casting other spells.

```lua
{"!&#trinket1", "buff(Bloodlust)", "player"}
```

This will clip the current cast and use trinket 1 without triggering the GCD.

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
