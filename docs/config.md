# Configuration

As you see in the example of the [introduction](my-first-rotation.md), the config file is a Lua table that contains the information for the rotation, like the name, the in combat rotations, the wow version, the apep version and many more. Here is an example of a real world rotation.

```lua
{
    name = "Protection Warrior (DSL mode)",
    ic = inCombat,
    ooc = outCombat,
    use_lua_engine = false,
    gui = GUI,
    gui_st = {
        title = "CR Settings",
        color = "87CEFA",
        width = "315",
        height = "370"
    },
    wow_ver = "10.1.7",
    apep_ver = "1.1",
    ids = spellIds_Loc,
    blacklist = blacklist,
    pooling = false,
    load = exeOnLoad,
    unload = exeOnUnload
}
```

> ### name

The name of the rotation, it's used to identify the rotation in the UI.

> ### ic

The in combat rotations, it's a table or function that contains the rotations to be executed in combat.

> ### ooc

The out of combat rotations, it's a table or function that contains the rotations to be executed out of combat.

> ### use_lua_engine

If the rotation should use the Lua engine or not.

> ### gui

The GUI, it's a table that contains the GUI settings.

> ### gui_st

The GUI settings, it's a table that contains the GUI settings.

#### Example

```lua
{
    gui_st: {
        title = "Warrior Protection",
        color = "87CEFA",
        width = "315",
        height = "370"
    }
}
```

> ### wow_ver

The World of Warcraft version, it's used to check if the rotation is compatible with the current version of the game and to display the rotation in the UI only if it's compatible.

> ### apep_ver

For the version of apep for which this rotation was created.

> ### ids

The `ids` table contains spell IDs, which are essential for supporting multiple languages. By using spell IDs, your rotation can recognize spells regardless of the client's language settings. This ensures that the rotation functions correctly even if the game language changes. If you do not use spell IDs, the rotation may fail to identify spells correctly.

```lua
local spellIds_Loc = {
    -- Buffs
    ["Juggernaut"] = 65156,
    ["Sudden Death"] = 52437,
    ["Taste for Blood"] = 60503,
    ["Power Word: Shield"] = 48066,
    ["Protection of Ancient Kings"] = 64413,
    ["Sacred Shield"] = 58597,
    ["Divine Aegis"] = 47753,
    ["Blessing of Might"] = 48932,
    ["Greater Blessing of Might"] = 47488,

    -- Debuffs
    ["Expose Armor"] = 8647,

    -- Talents
    ["Improved Slam"] = GetSpellInfo(12330),
    ["Armored to the Teeth"] = _A.GetSpellInfo(61222), -- Alliance
}

_A.CR:Add(
    73,
    {
        ...
        ids = spellIds_Loc,
        ...
    }
)
```

> ### blacklist

The blacklist, it's a table that contains the spell ids to be blacklisted.

> ### pooling

If the rotation should use pooling or not.

> ### load

The load function, it's a function that is executed when the rotation is loaded.

> ### unload

The unload function, it's a function that is executed when the rotation is unloaded.
