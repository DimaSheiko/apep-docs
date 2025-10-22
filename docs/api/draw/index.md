# DRAW API Reference

The Draw system provides two types of methods: **Static** and **Dynamic**.

-   **Static** drawings remain fixed at a certain position on the screen or in the world and do not need to be called in cycles.
-   **Dynamic** drawings move on the screen or in the world and need to be called within a cycle named `DrawTick:Render`.

---

## Layer System

The rendering layer defines the depth at which objects are drawn relative to others:

| Layer | Description                                  |
| ----- | -------------------------------------------- |
| `-1`  | The object is drawn behind other objects     |
| `0`   | The object is drawn behind the UI            |
| `1`   | The object is drawn above the UI (default)   |

---

## Glyph Sets

When loading fonts, you can specify which character set to load:

-   `"Latin"` - Standard Latin characters (default)
-   `"Greek"` - Greek alphabet
-   `"Korean"` - Korean characters
-   `"Japanese"` - Japanese characters
-   `"Chinese"` - Chinese characters (subset)
-   `"ChineseFull"` - Full Chinese character set
-   `"Cyrillic"` - Cyrillic alphabet
-   `"Thai"` - Thai characters
-   `"Vietnamese"` - Vietnamese characters

You can also provide a custom table of glyphs to load.

---

# Static Methods

Static drawings are persistent and do not require continuous updates.

---

> ## LoadTexture

Loads a texture from the specified file path. Supports PNG, BLP, and textures from MPQ archives.

#### Parameters

-   `filePath`(string): The path to the texture file to be loaded.

#### Returns `object`

-   A texture object if successfully loaded, or `nil` if the loading failed.

#### _Example:_

```lua
local myTexture = Draw:LoadTexture("Interface\\Icons\\INV_Misc_QuestionMark")
if myTexture then
    print("Texture loaded successfully")
end
```

---

> ## LoadFont

Loads a TrueType font from the specified file path and size.

#### Parameters

-   `filePath`(string): The path to the font file to be loaded.
-   `size`(number): The size of the font. Defaults to `13` if not provided.
-   `glyph`(string or table): The type of glyph set to use. Defaults to `"Latin"` if not provided.

#### Returns `object`

-   A font object if successfully loaded, or `nil` if the loading failed.

#### _Example:_

```lua
local myFont = Draw:LoadFont("Fonts\\FRIZQT__.TTF", 16, "Latin")
if myFont then
    print("Font loaded successfully")
end
```

---

> ## Image2D

Creates a 2D image at the specified screen coordinates.

#### Parameters

-   `left`(number): The x-coordinate of the left edge.
-   `top`(number): The y-coordinate of the top edge.
-   `right`(number): The x-coordinate of the right edge.
-   `bottom`(number): The y-coordinate of the bottom edge.
-   `color`(number): The color in ARGB format. Defaults to `0xFF000000` (black).
-   `layer`(number): The rendering layer. Defaults to `1`.

#### Returns `object`

-   An image object if successfully created, or `nil` if the creation failed.

#### _Example:_

```lua
local img = Draw:Image2D(100, 100, 200, 200, 0xFFFF0000, 1)
if img then
    print("Image created")
end
```

---

> ## Text2D

Draws 2D text at the specified position.

#### Parameters

-   `text`(string): The text to display.
-   `left`(number): The x-coordinate of the text position.
-   `top`(number): The y-coordinate of the text position.
-   `size`(number): The font size of the text.
-   `color`(number): The color in ARGB format. Defaults to `0xFF000000` (black).
-   `stroke`(boolean): Whether to enable text stroke (outline).
-   `layer`(number): The rendering layer. Defaults to `1`.

#### Returns `object`

-   A text object if successfully created, or `nil` if the creation failed.

#### _Example:_

```lua
local text = Draw:Text2D("Hello World", 100, 100, 14, 0xFFFFFFFF, true, 1)
```

---

> ## Line2D

Draws a 2D line on the screen.

#### Parameters

-   `left`(number): The x-coordinate of the starting point.
-   `top`(number): The y-coordinate of the starting point.
-   `right`(number): The x-coordinate of the ending point.
-   `bottom`(number): The y-coordinate of the ending point.
-   `color`(number): The color in ARGB format. Defaults to `0xFF000000` (black).
-   `thickness`(number): The thickness of the line. Defaults to `1.0`.
-   `layer`(number): The rendering layer. Defaults to `1`.

#### Returns `object`

-   A line object if successfully created, or `nil` if the creation failed.

#### _Example:_

```lua
local line = Draw:Line2D(100, 100, 200, 200, 0xFFFF0000, 2, 1)
```

---

> ## Line3D

Draws a 3D line between two points in world space.

#### Parameters

-   `coord1`(table): A table containing `{x, y, z}` coordinates of the starting point.
-   `coord2`(table): A table containing `{x, y, z}` coordinates of the ending point.
-   `color`(number): The color in ARGB format. Defaults to `0xFF000000` (black).
-   `thickness`(number): The thickness of the line. Defaults to `1.0`.
-   `layer`(number): The rendering layer. Defaults to `1`.

#### Returns `object`

-   A line object if successfully created, or `nil` if the creation failed.

#### _Example:_

```lua
local px, py, pz = _A.ObjectPosition("player")
local tx, ty, tz = _A.ObjectPosition("target")
local line = Draw:Line3D({px, py, pz}, {tx, ty, tz}, 0xFF00FF00, 2, 1)
```

---

> ## Rect2D

Draws a 2D rectangle on the screen.

#### Parameters

-   `left`(number): The x-coordinate of the top-left corner.
-   `top`(number): The y-coordinate of the top-left corner.
-   `right`(number): The x-coordinate of the bottom-right corner.
-   `bottom`(number): The y-coordinate of the bottom-right corner.
-   `color`(number): The color in ARGB format. Defaults to `0xFF000000` (black).
-   `thickness`(number): The border thickness. Defaults to `1.0`.
-   `rounding`(number): The corner rounding radius. Defaults to `0.0` (no rounding).
-   `filled`(boolean): If `true`, the rectangle will be filled. If `false`, only the border will be drawn.
-   `gradientSize`(number): The size of the gradient effect. Defaults to `0.0` (no gradient).
-   `layer`(number): The rendering layer. Defaults to `1`.

#### Returns `object`

-   A rectangle object if successfully created, or `nil` if the creation failed.

#### _Example:_

```lua
local rect = Draw:Rect2D(100, 100, 300, 200, 0xFF00FF00, 2, 5, true, 0, 1)
```

---

> ## Rect3D

Draws a 3D rectangle in world space.

#### Parameters

-   `center`(table): A table containing `{x, y, z}` coordinates of the center position.
-   `width`(number): The width of the rectangle.
-   `height`(number): The height of the rectangle.
-   `color`(number): The color in ARGB format. Defaults to `0xFF000000` (black).
-   `thickness`(number): The border thickness. Defaults to `1.0`.
-   `rounding`(number): The corner rounding radius. Defaults to `0.0` (no rounding).
-   `filled`(boolean): If `true`, the rectangle will be filled. If `false`, only the border will be drawn.
-   `gradientSize`(number): The size of the gradient effect. Defaults to `0.0` (no gradient).
-   `rotation`(table): A table `{rx, ry, rz}` defining rotation angles in degrees. Defaults to `{0.0, 0.0, 0.0}`.
-   `layer`(number): The rendering layer. Defaults to `1`.

#### Returns `object`

-   A rectangle object if successfully created, or `nil` if the creation failed.

#### _Example:_

```lua
local px, py, pz = _A.ObjectPosition("player")
local rect = Draw:Rect3D({px, py, pz}, 5, 5, 0xFFFF0000, 2, 0, false, 0, {0, 0, 0}, 1)
```

---

> ## Circle2D

Draws a 2D circle on the screen.

#### Parameters

-   `x`(number): The x-coordinate of the circle's center.
-   `y`(number): The y-coordinate of the circle's center.
-   `radius`(number): The radius of the circle.
-   `color`(number): The color in ARGB format. Defaults to `0xFF000000` (black).
-   `thickness`(number): The border thickness. Defaults to `1.0`.
-   `segments`(number): The number of line segments used to approximate the circle. Defaults to `0.0` (auto-calculated).
-   `filled`(boolean): If `true`, the circle will be filled. If `false`, only the border will be drawn.
-   `gradientSize`(number): The size of the gradient effect. Defaults to `0.0` (no gradient).
-   `layer`(number): The rendering layer. Defaults to `1`.

#### Returns `object`

-   A circle object if successfully created, or `nil` if the creation failed.

#### _Example:_

```lua
local circle = Draw:Circle2D(400, 300, 50, 0xFFFFFF00, 2, 32, false, 0, 1)
```

---

> ## Circle3D

Draws a 3D circle at the specified world position.

#### Parameters

-   `center`(table): A table containing `{x, y, z}` coordinates of the circle's center.
-   `radius`(number): The radius of the circle.
-   `color`(number): The color in ARGB format. Defaults to `0xFF000000` (black).
-   `thickness`(number): The border thickness. Defaults to `1.0`.
-   `segments`(number): The number of line segments used to approximate the circle. Defaults to `0.0` (auto-calculated).
-   `filled`(boolean): If `true`, the circle will be filled. If `false`, only the border will be drawn.
-   `gradientSize`(number): The size of the gradient effect. Defaults to `0.0` (no gradient).
-   `rotation`(table): A table `{rx, ry, rz}` specifying rotation in degrees. Defaults to `{0.0, 0.0, 0.0}`.
-   `layer`(number): The rendering layer. Defaults to `1`.

#### Returns `object`

-   A circle object if successfully created, or `nil` if the creation failed.

#### _Example:_

```lua
local px, py, pz = _A.ObjectPosition("player")
local circle = Draw:Circle3D({px, py, pz}, 10, 0xFF0000FF, 2, 64, false, 0, {0, 0, 0}, 1)
```

---

> ## Image3D

Renders a 3D image at a specified position with rotation and size.

#### Parameters

-   `center`(table): A table containing `{x, y, z}` coordinates for the image's center position.
-   `size`(table): A table containing `{width, height}` dimensions for the image's size.
-   `color`(number): The color in ARGB format. Defaults to `0xFF000000` (black).
-   `billboard`(boolean): If `true`, the image will always face the camera. Defaults to `false`.
-   `rotation`(table): A table containing `{rx, ry, rz}` rotation angles in degrees. Defaults to `{0.0, 0.0, 0.0}`.
-   `layer`(number): The rendering layer. Defaults to `1`.

#### Returns `object`

-   An image object if successfully created, or `nil` if the creation failed.

!>**Note:** You must load a texture first using `Draw:LoadTexture()` and call this method on the texture object.

#### _Example:_

```lua
local texture = Draw:LoadTexture("Interface\\Icons\\INV_Misc_QuestionMark")
local px, py, pz = _A.ObjectPosition("player")
local img = texture:Image3D({px, py + 5, pz}, {2, 2}, 0xFFFFFFFF, true, {0, 0, 0}, 1)
```

---

> ## Text3D

Renders 3D text at a specified coordinate.

#### Parameters

-   `text`(string): The text to be displayed.
-   `coord`(table): A table containing `{x, y, z}` coordinates for text positioning.
-   `fontSize`(number): The font size. Defaults to `13.0`.
-   `color`(number): The color in ARGB format. Defaults to `0xFF000000` (black).
-   `stroke`(boolean): Whether the text has an outline. Defaults to `false`.
-   `layer`(number): The rendering layer. Defaults to `1`.

#### Returns `object`

-   A text object if successfully created, or `nil` if the creation failed.

!>**Note:** You must load a font first using `Draw:LoadFont()` and call this method on the font object.

#### _Example:_

```lua
local font = Draw:LoadFont("Fonts\\FRIZQT__.TTF", 14, "Latin")
local px, py, pz = _A.ObjectPosition("player")
local text = font:Text3D("Player Position", {px, py, pz + 3}, 14, 0xFFFFFFFF, true, 1)
```

---

> ## Show

Shows a previously hidden draw object.

#### Returns `boolean`

-   `true` if the object was successfully shown, `false` otherwise.

#### _Example:_

```lua
local circle = Draw:Circle2D(400, 300, 50, 0xFFFFFF00, 2, 32, false, 0, 1)
circle:Hide()
-- Later...
circle:Show()
```

---

> ## Hide

Hides a draw object without removing it.

#### Returns `boolean`

-   `true` if the object was successfully hidden, `false` otherwise.

#### _Example:_

```lua
local circle = Draw:Circle2D(400, 300, 50, 0xFFFFFF00, 2, 32, false, 0, 1)
circle:Hide()
```

---

> ## TimeOut

Sets a timeout for a drawable object to be automatically removed.

#### Parameters

-   `timeoutMs`(number): The timeout duration in milliseconds.

#### Returns `boolean`

-   `true` if the timeout was set successfully, `false` otherwise.

#### _Example:_

```lua
local text = Draw:Text2D("Temporary Message", 400, 300, 14, 0xFFFFFFFF, true, 1)
text:TimeOut(3000) -- Remove after 3 seconds
```

---

> ## GetType

Retrieves the type of the drawing object.

#### Returns `string`

-   The type of the drawing object, or `nil` if not available.

#### _Example:_

```lua
local circle = Draw:Circle2D(400, 300, 50, 0xFFFFFF00, 2, 32, false, 0, 1)
print(circle:GetType()) -- "Circle2D"
```

---

> ## GetID

Retrieves the unique ID of the drawing object.

#### Returns `number`

-   The unique ID of the drawing object, or `-1` if not available.

#### _Example:_

```lua
local circle = Draw:Circle2D(400, 300, 50, 0xFFFFFF00, 2, 32, false, 0, 1)
print(circle:GetID())
```

---

> ## GetName

Retrieves the name or path of the drawing object.

#### Returns `string`

-   The name or path of the drawing object, or `nil` if not available.

#### _Example:_

```lua
local texture = Draw:LoadTexture("Interface\\Icons\\INV_Misc_QuestionMark")
print(texture:GetName())
```

---

> ## GetSize

Retrieves the width and height of the drawing object.

#### Returns `number`, `number`

-   The width and height of the drawing object, or `nil` if not available.

#### _Example:_

```lua
local texture = Draw:LoadTexture("Interface\\Icons\\INV_Misc_QuestionMark")
local w, h = texture:GetSize()
print("Width:", w, "Height:", h)
```

---

> ## GetWidth

Retrieves the width of the drawing object.

#### Returns `number`

-   The width of the drawing object, or `nil` if not available.

#### _Example:_

```lua
local texture = Draw:LoadTexture("Interface\\Icons\\INV_Misc_QuestionMark")
print("Width:", texture:GetWidth())
```

---

> ## GetHeight

Retrieves the height of the drawing object.

#### Returns `number`

-   The height of the drawing object, or `nil` if not available.

#### _Example:_

```lua
local texture = Draw:LoadTexture("Interface\\Icons\\INV_Misc_QuestionMark")
print("Height:", texture:GetHeight())
```

---

# Dynamic Methods

Dynamic drawings update every frame and must be called within a `DrawTick:Render` callback.

---

> ## DrawTick:Render

Registers a render callback to be executed during the rendering phase.

#### Parameters

-   `name`(string): The unique name associated with the render callback.
-   `callback`(function): The function to be executed during the render phase.

!>**Note:** If a render with the same name already exists, a warning will be displayed.

#### _Example:_

```lua
DrawTick:Render("MyDrawing", function()
    local px, py, pz = _A.ObjectPosition("player")
    Draw:Circle3D({px, py, pz}, 5, 0xFF00FF00, 2, 32, false, 0, {0, 0, 0}, 1)
end)
```

---

> ## DrawTick:UnRender

Unregisters a previously registered render callback by name.

#### Parameters

-   `name`(string): The name of the render callback to be removed.

#### _Example:_

```lua
DrawTick:UnRender("MyDrawing")
```

---

> ## Dynamic Drawing Methods

All static drawing methods (Image2D, Text2D, Line2D, Line3D, Rect2D, Rect3D, Circle2D, Circle3D, Image3D, Text3D) can also be used dynamically within a `DrawTick:Render` callback. When used this way, they update every frame automatically.

#### _Example:_

```lua
local font = Draw:LoadFont("Fonts\\FRIZQT__.TTF", 14, "Latin")

DrawTick:Render("PlayerPosition", function()
    local px, py, pz = _A.ObjectPosition("player")
    Draw:Circle3D({px, py, pz}, 5, 0xFF00FF00, 2, 32, false, 0, {0, 0, 0}, 1)
    Draw:Text3D("Player", {px, py, pz + 3}, font, 14, 0xFFFFFFFF, true, 1)
end)
```

---

> ## Array3D

Renders a series of 3D lines based on an array of vector pairs.

#### Parameters

-   `vectors`(table): A table containing pairs of `{start, end}` vectors, each in `{x, y, z}` format.
-   `center`(table): The `{x, y, z}` coordinates representing the origin for transformations.
-   `rotation`(table): A table `{rx, ry, rz}` specifying rotation angles in degrees. Defaults to `{0, 0, 0}`.
-   `scale`(number): A uniform scale factor applied to all vectors. Defaults to `1.0`.
-   `color`(number): The color in ARGB format. Defaults to `0xFF000000` (black).
-   `thickness`(number): The thickness of the lines. Defaults to `1.0`.
-   `layer`(number): The rendering layer. Defaults to `1`.

#### _Example:_

```lua
local vectors = {
    {{0, 0, 0}, {1, 0, 0}},
    {{0, 0, 0}, {0, 1, 0}},
    {{0, 0, 0}, {0, 0, 1}}
}

DrawTick:Render("Axes", function()
    local px, py, pz = _A.ObjectPosition("player")
    Draw:Array3D(vectors, {px, py, pz}, {0, 0, 0}, 2.0, 0xFFFF0000, 2, 1)
end)
```

---

# Common Methods

These methods can be used with both static and dynamic drawing to set global properties.

---

> ## SetColor

Sets the global drawing color for subsequent drawing operations.

#### Parameters

-   `r`(number): The red component (0-255).
-   `g`(number): The green component (0-255).
-   `b`(number): The blue component (0-255).
-   `a`(number): The alpha component (0-100). Defaults to `100` (fully opaque).

#### _Example:_

```lua
Draw:SetColor(255, 0, 0, 50) -- Semi-transparent red
```

---

> ## SetColorRaw

Sets the raw RGBA color values without normalization.

#### Parameters

-   `r`(number): The raw red component.
-   `g`(number): The raw green component.
-   `b`(number): The raw blue component.
-   `a`(number): The raw alpha component.

#### _Example:_

```lua
Draw:SetColorRaw(1.0, 0.0, 0.0, 0.5) -- Semi-transparent red
```

---

> ## SetColorHex

Sets the color using a hexadecimal color code.

#### Parameters

-   `hc`(string or number): The hexadecimal color code (e.g., `0xFF00FF00` for green).

#### _Example:_

```lua
Draw:SetColorHex(0xFFFF0000) -- Red with full opacity
```

---

> ## SetThickness

Sets the thickness for lines and shapes.

#### Parameters

-   `thickness`(number): The line or shape border thickness.

#### _Example:_

```lua
Draw:SetThickness(3)
```

---

> ## SetLayer

Sets the rendering layer for objects.

#### Parameters

-   `layer`(number): The layer level (`-1`, `0`, or `1`).

#### _Example:_

```lua
Draw:SetLayer(0) -- Draw behind UI
```

---

> ## SetStroke

Sets the stroke (outline) visibility for text objects.

#### Parameters

-   `bool`(boolean): Whether the text should have a stroke.

#### _Example:_

```lua
Draw:SetStroke(true)
```

---

> ## SetRounding

Sets the rounding value for corners of shapes.

#### Parameters

-   `rounding`(number): The rounding radius for corners.

#### _Example:_

```lua
Draw:SetRounding(5)
```

---

> ## SetGradientSize

Sets the gradient size for shapes.

#### Parameters

-   `size`(number): The size of the gradient effect.

#### _Example:_

```lua
Draw:SetGradientSize(10)
```

---

> ## SetSegments

Sets the number of segments for circular shapes.

#### Parameters

-   `segments`(number): The number of segments used to draw circles.

#### _Example:_

```lua
Draw:SetSegments(64) -- Smoother circles
```

---

> ## SetFilled

Sets whether shapes should be filled or outlined.

#### Parameters

-   `bool`(boolean): `true` to fill the shape, `false` to outline.

#### _Example:_

```lua
Draw:SetFilled(true)
```

---

> ## SetFontSize

Sets the font size for text rendering.

#### Parameters

-   `size`(number): The font size to be applied.

#### _Example:_

```lua
Draw:SetFontSize(16)
```

---

!!! info "QuickDraw Replacement"

    The Draw system replaces the old QuickDraw module and offers more advantages and enhancements. QuickDraw will be removed in a future version.

