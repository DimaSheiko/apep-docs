# STATES
---


> ## state

- This condition checks if the specified unit has any of the specified states applied to it.

#### Parameters
- `UNIT`: The unit to check for states.
- `ARGS`: A string containing state names separated by `'||'`.

#### Returns `BOOL`
- `true` if the unit has any of the specified states, `false` otherwise.

    | state      | types                                                                                                                |
    | ---------- | -------------------------------------------------------------------------------------------------------------------- |
    |charm       | {'^charmed'}                                                                                                         |
    |disarm      | {'disarmed'}                                                                                                         |
    |disorient   | {'^disoriented'}                                                                                                     |
    |dot         | {'damage every.*sec', 'damage per.*sec'}                                                                             |
    |fear        | {'^horrified', '^fleeing', '^feared', '^intimidated', '^cowering in fear', '^running in fear', '^compelled to flee'} |
    |incapacitate| {'^incapacitated', '^sapped'}                                                                                        |
    |misc        | {'unable to act', '^bound', '^frozen.$', '^cannot attack or cast spells', '^shackled.$'}                             |
    |root        | {'^rooted', '^immobil', '^webbed', 'frozen in place', '^paralyzed', '^locked in place', '^pinned in place'}          |
    |stun        | {'^stunned', '^webbed'}                                                                                              |
    |silence     | {'^silenced'}                                                                                                        |
    |sleep       | {'^asleep'}                                                                                                          |
    |snare       | {'^movement.*slowed', 'movement speed reduced', '^slowed by', '^dazed', '^reduces movement speed'}                   |

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.state(fear || sleep)", UNIT},

-- in Lua code
_A.DSL:Get("state")("UNIT", "fear || sleep")

-- Lua Mode
UNIT:State("fear || sleep")
```

***


> ## immune

- This condition checks if the specified unit is immune to any of the specified immunity types.

#### Parameters
- `UNIT`: The unit to check for immunities.
- `ARGS`: A string containing immunity types separated by '||'.

#### Returns `BOOL`
- `true` if the unit is immune to any of the specified immunity types, `false` otherwise.

    | immune     | types                                                                                                                                                |
    | ---------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
    |all         | {'dematerialize', 'deterrence', 'divine shield', 'ice block'}                                                                                        |
    |charm       | {'bladestorm', 'desecrated ground', 'grounding totem effect', 'lichborne'}                                                                           |
    |disorient   | {'bladestorm', 'desecrated ground'}                                                                                                                  |
    |fear        | {'berserker rage', 'bladestorm', 'desecrated ground', 'grounding totem','lichborne', 'nimble brew'}                                                  |
    |incapacitate| {'bladestorm', 'desecrated ground'}                                                                                                                  |
    |melee       | {'dispersion', 'evasion', 'hand of protection', 'ring of peace', 'touch of karma'}                                                                   |
    |misc        | {'bladestorm', 'desecrated ground'}                                                                                                                  |
    |silence     | {'devotion aura', 'inner focus', 'unending resolve'}                                                                                                 |
    |polly       | {'immune to polymorph'}                                                                                                                              |
    |sleep       | {'bladestorm', 'desecrated ground', 'lichborne'}                                                                                                     |
    |snare       | {'bestial wrath', 'bladestorm', 'death\'s advance', 'desecrated ground','dispersion', 'hand of freedom', 'master\'s call', 'windwalk totem'}         |
    |spell       | {'anti-magic shell', 'cloak of shadows', 'diffuse magic', 'dispersion','massspell reflection', 'ring of peace', 'spell reflection', 'touch of karma'}|
    |stun        | {'bestial wrath', 'bladestorm', 'desecrated ground', 'icebound fortitude','grounding totem', 'nimble brew'}                                          |

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.immune(fear || charm)", UNIT},

-- in Lua code
_A.DSL:Get("immune")("UNIT", "fear || charm")

-- Lua Mode
UNIT:Immune("fear || charm")
```

***


> ## state.purge

- This condition checks if the specified target's debuff can be dispelled using the specified spell.

#### Parameters
- `UNIT`: The unit  to check for dispellable debuffs.
- `spell`: The spell id or name used to determine if the debuff can be dispelled.

#### Returns `BOOL`
- `true` if the unit's debuff can be dispelled using the specified spell, `false` otherwise.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.state(Fear).purge", UNIT},

-- in Lua code
_A.DSL:Get("state.purge")("UNIT", "Fear")

-- Lua Mode
UNIT:StatePurge("Fear")
```
