# KEYBINDS

---

> ## mouse

-   This condition checks if a specified mouse button is currently held down. The game must be in the foreground and no keyboard element should be focused for this to return true.

#### Parameters

-   `button`: The mouse button name (e.g., "LBUTTON", "BUTTON4") or index (e.g., 1, 4).

#### Returns `BOOL`

-   `true` if the specified mouse button is held down, `false` otherwise.

    | index | name         | VirtualKeyCode String |
    | :---: | ------------ | --------------------- |
    |   1   | LeftButton   | "LBUTTON", "BUTTON1"   |
    |   2   | RightButton  | "RBUTTON", "BUTTON2"  |
    |   3   | MiddleButton | "MBUTTON", "BUTTON3"  |
    |   4   | Button4      | "XBUTTON1", "BUTTON4" |
    |   5   | Button5      | "XBUTTON2", "BUTTON5" |

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "mouse(3)"}, -- (1)!
    ```

    1.  MiddleButton (pressed by index)

=== "DSL"

    ```lua
    {ACTION, "mouse(BUTTON4)"}, -- (1)!
    ```

    1.  Button4 (pressed by name)

=== "Lua Code"

    ```lua
    _A.DSL:Get("mouse")(_, "Button4") -- (1)!
    ```

    1.  Checks if "BUTTON4" is pressed.

=== "Lua Mode"

    ```lua
    PLAYER:Mouse(2) -- (1)!
    ```

    1.  RightButton

---

> ## keybind
>
> _`keybind || keybind.down`_

-   This condition checks if a specified keybind or combination of keybinds is currently pressed. All keys in the comma-separated list must be pressed for this to return true. The game must be in the foreground and no keyboard element should be focused.

#### Parameters

-   `keys`: A comma-separated string of keybinds to check (e.g., "SHIFT", "ALT-Q", "F3", "CONTROL,A").

#### Returns `BOOL`

-   `true` if all specified keybinds are pressed, `false` otherwise.

    | Modifiers       | Description                                |
    | --------------- | ------------------------------------------ |
    | SHIFT, LSHIFT, RSHIFT | Shift key (any, left, or right)         |
    | CONTROL, LCONTROL, RCONTROL, CTRL, LCTRL, RCTRL | Control key (any, left, or right) |
    | ALT, LALT, RALT     | Alt key (any, left, or right)             |

    Other keys can be specified by their names as defined in the `VirtualKeyCodes` table (e.g., "A", "1", "F1", "SPACE", "RETURN", "TAB").

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "keybind(ALT)"}, -- (1)!
    ```
    1.  Checks if Alt key is pressed.

=== "DSL"

    ```lua
    {ACTION, "keybind.down(SHIFT,F)"}, -- (1)!
    ```
    1.  Checks if Shift + F is pressed.

=== "Lua Code"

    ```lua
    _A.DSL:Get("keybind")(_, "alt")
    _A.DSL:Get("keybind.down")(_, "SHIFT,F")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:Keybind("alt")
    PLAYER:Keybind("SHIFT,F")
    ```

---

> ## keybind.up

-   This condition checks if a specified keybind or combination of keybinds was just released. It uses a short timer to detect the release event. The game must be in the foreground and no keyboard element should be focused.

#### Parameters

-   `keys`: A comma-separated string of keybinds to check for release (e.g., "SHIFT", "ALT-Q", "F3", "CONTROL,A").

#### Returns `BOOL`

-   `true` if all specified keybinds were released within a short time frame, `false` otherwise.

    | Modifiers       | Description                                |
    | --------------- | ------------------------------------------ |
    | SHIFT, LSHIFT, RSHIFT | Shift key (any, left, or right)         |
    | CONTROL, LCONTROL, RCONTROL, CTRL, LCTRL, RCTRL | Control key (any, left, or right) |
    | ALT, LALT, RALT     | Alt key (any, left, or right)             |

    Other keys can be specified by their names as defined in the `VirtualKeyCodes` table (e.g., "A", "1", "F1", "SPACE", "RETURN", "TAB").

#### _Example:_

=== "DSL"

    ```lua
    {ACTION, "keybind.up(SHIFT)"}, -- (1)!
    ```
    1.  Checks if Shift key was released.

=== "DSL"

    ```lua
    {ACTION, "keybind.up(ALT,A)"}, -- (1)!
    ```
    1.  Checks if Alt + A was released.

=== "Lua Code"

    ```lua
    _A.DSL:Get("keybind.up")(_, "SHIFT")
    _A.DSL:Get("keybind.up")(_, "ALT,A")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:KeybindUp("SHIFT")
    PLAYER:KeybindUp("ALT,A")
