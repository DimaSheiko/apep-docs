# STATES

---

> ## state

-   This condition checks if the specified unit has any of the specified states applied to it.

#### Parameters

-   `UNIT`: The unit to check for states.
-   `ARGS`: A string containing state names separated by `'||'`.

#### Returns `BOOL`

-   `true` if the unit has any of the specified states, `false` otherwise.

    | state        | types                                                                                                                |
    | ------------ | -------------------------------------------------------------------------------------------------------------------- |
    | charm        | {'^charmed'}                                                                                                         |
    | disarm       | {'disarmed'}                                                                                                         |
    | disorient    | {'^disoriented'}                                                                                                     |
    | dot          | {'damage every.*sec', 'damage per.*sec'}                                                                             |
    | fear         | {'^horrified', '^fleeing', '^feared', '^intimidated', '^cowering in fear', '^running in fear', '^compelled to flee'} |
    | incapacitate | {'^incapacitated', '^sapped'}                                                                                        |
    | misc         | {'unable to act', '^bound', '^frozen.$', '^cannot attack or cast spells', '^shackled.$'}                             |
    | root         | {'^rooted', '^immobil', '^webbed', 'frozen in place', '^paralyzed', '^locked in place', '^pinned in place'}          |
    | stun         | {'^stunned', '^webbed'}                                                                                              |
    | silence      | {'^silenced'}                                                                                                        |
    | sleep        | {'^asleep'}                                                                                                          |
    | snare        | {'^movement.\*slowed', 'movement speed reduced', '^slowed by', '^dazed', '^reduces movement speed'}                  |

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.state(fear || sleep)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("state")("UNIT", "fear || sleep")
    ```

=== "Lua Mode"

    ```lua
    UNIT:State("fear || sleep")
    ```

---

> ## immune

-   This condition checks if the specified unit is immune to any of the specified immunity types.

#### Parameters

-   `UNIT`: The unit to check for immunities.
-   `ARGS`: A string containing immunity types separated by '||'.

#### Returns `BOOL`

-   `true` if the unit is immune to any of the specified immunity types, `false` otherwise.

    | immune       | types                                                                                                                                                 |
    | ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
    | all          | {'dematerialize', 'deterrence', 'divine shield', 'ice block', 'desoriented and invulnerable', 'cyclone'} |
    | charm        | {'bladestorm', 'desecrated ground', 'grounding totem effect', 'lichborne'}                                                                            |
    | disorient    | {'bladestorm', 'desecrated ground'}                                                                                                                   |
    | fear         | {'berserker rage', 'bladestorm', 'desecrated ground', 'grounding totem','lichborne', 'nimble brew'}                                                   |
    | incapacitate | {'bladestorm', 'desecrated ground'}                                                                                                                   |
    | melee        | {'dispersion', 'evasion', 'hand of protection', 'ring of peace', 'touch of karma'}                                                                    |
    | misc         | {'bladestorm', 'desecrated ground'}                                                                                                                   |
    | silence      | {'devotion aura', 'inner focus', 'unending resolve'}                                                                                                  |
    | polly        | {'immune to polymorph'}                                                                                                                               |
    | sleep        | {'bladestorm', 'desecrated ground', 'lichborne'}                                                                                                      |
    | snare        | {'bestial wrath', 'bladestorm', 'death\'s advance', 'desecrated ground','dispersion', 'hand of freedom', 'master\'s call', 'windwalk totem'}          |
    | spell        | {'anti-magic shell', 'cloak of shadows', 'diffuse magic', 'dispersion','massspell reflection', 'ring of peace', 'spell reflection', 'touch of karma'} |
    | stun         | {'bestial wrath', 'bladestorm', 'desecrated ground', 'icebound fortitude','grounding totem', 'nimble brew'}                                           |

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.immune(fear || charm)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("immune")("UNIT", "fear || charm")
    ```

=== "Lua Mode"

    ```lua
    UNIT:Immune("fear || charm")
    ```

---

> ## state.purge

-   This condition checks if a debuff on the specified target can be dispelled by the specified spell.

#### Parameters

-   `UNIT`: The target unit to check for dispellable debuffs.
-   `SPELL`: The name or ID of the dispelling spell (e.g., Purify, Cleanse Spirit).

#### Returns `BOOL`

-   `true` if a debuff on the target unit can be dispelled by the specified spell, `false` otherwise.

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "UNIT.state.purge(Purify)", UNIT},
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("state.purge")("UNIT", "Purify")
    ```

=== "Lua Mode"

    ```lua
    UNIT:StatePurge("Purify")
    ```
