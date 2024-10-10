# KEYBINDS
---


> ## mouse

- This condition checks if a specified mouse button is currently held down.

#### Parameters
- `button`: The mouse button name or index (e.g., "LeftButton", "Button4", 2).

#### Returns `BOOL`
- `true` if the specified mouse button is held down, `false` otherwise.

    | index |name          |
    | :---: | ------------ |
    |1      | LeftButton   |
    |2      | RightButton  |
    |3      | MiddleButton |
    |4      | Button4      |
    |5      | Button5      |


#### *Example:*
```lua
-- DSL Mode
{ACTION, "mouse(3)"}, -- MiddleButton

-- in Lua code
_A.DSL:Get("mouse")(_, "Button4") -- 4

-- Lua Mode
PLAYER:Mouse(2) -- RightButton
```

***


> ## keybind

- This condition checks if a specified keybind is pressed.

#### Parameters
- `key`: The keybind to check (e.g., "SHIFT-1", "ALT-Q", "F3", "R").

#### Returns `BOOL`
- `true` if the specified keybind is pressed, `false` otherwise.

    | modifiers |
    | --------- |
    | SHIFT     |
    | LSHIFT    |
    | RSHIFT    |
    | CONTROL   |
    | LCONTROL  |
    | RCONTROL  |
    | ALT       |
    | LALT      |
    | RALT      |


#### *Example:*
```lua
-- DSL Mode
{ACTION, "keybind(alt)"},

-- in Lua code
_A.DSL:Get("keybind")(_, "alt")

-- Lua Mode
PLAYER:Keybind("alt")
```
