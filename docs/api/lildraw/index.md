# LIBDRAW

---

> ## SetColorHex

-   Set the color for drawing operations in LibDraw.

#### Parameters

-   `hex`(string): The hexadecimal color code (e.g., "#RRGGBB" or "#AARRGGBB").

!>**Note:** If an alpha component is not provided, it defaults to fully opaque.

#### _Example:_

```lua
_A.LibDraw:SetColorHex("#7F00FF00") -- (1)
```

1. Sets the drawing color to green with 50% transparency.

---

> ## SetColor

-   Set the color for drawing operations in LibDraw.

#### Parameters

-   `r`: The red component of the color (0-255).
-   `g`: The green component of the color (0-255).
-   `b`: The blue component of the color (0-255).
-   `a`: [optional] - The alpha (transparency) component of the color (0-255).

!>**Note:** If an alpha component is not provided, it defaults to fully opaque.

#### _Example:_

```lua
_A.LibDraw:SetColor(0, 255, 0, 127) -- (1)
```

1. Green with 50% transparency.

---

> ## SetColorRaw

-   Set the color for drawing operations in LibDraw without normalizing values.

#### Parameters

-   `r`: The red component of the color. (0-255 or other range)
-   `g`: The green component of the color. (0-255 or other range)
-   `b`: The blue component of the color. (0-255 or other range)
-   `a`: [optional] - The alpha (transparency) component of the color. (0-255 or other range)

!>**Note:** If an alpha component is not provided, it defaults to 1 fully opaque.
Unlike `SetColor`, this function does not normalize the provided color values, allowing direct use of raw color components.

#### _Example:_

```lua
_A.LibDraw:SetColorRaw(0, 1, 0, 0.5) -- (1)
```

1. Green with 50% transparency.

---

> ## SetWidth

-   Set the pen width for drawing operations in LibDraw.

#### Parameters

-   `penWidth`: The width value of the pen for drawing operations.

#### _Example:_

```lua
_A.LibDraw:SetWidth(2) -- (1)
```

1. Sets the pen drawing width to 2 units.

---

> ## Line

-   Draw a 2D line using world coordinates, converted to screen space.

#### Parameters

-   `sx`: The starting X-coordinate of the line in world space.
-   `sy`: The starting Y-coordinate of the line in world space.
-   `sz`: The starting Z-coordinate of the line in world space.
-   `ex`: The ending X-coordinate of the line in world space.
-   `ey`: The ending Y-coordinate of the line in world space.
-   `ez`: The ending Z-coordinate of the line in world space.

#### _Example:_

```lua
_A.LibDraw:Line(0, 0, 0, 100, 100, 0) -- (1)
```

1. Draws a line from world coordinates (0, 0, 0) to (100, 100, 0) on the screen.

---

> ## rotateX

-   Rotate a point around the X-axis using a specified center and angle.

#### Parameters

-   `cx`: The X-coordinate of the rotation center.
-   `cy`: The Y-coordinate of the rotation center.
-   `cz`: The Z-coordinate of the rotation center.
-   `px`: The X-coordinate of the point to be rotated.
-   `py`: The Y-coordinate of the point to be rotated.
-   `pz`: The Z-coordinate of the point to be rotated.
-   `angle`: The angle of rotation in radians.

#### Returns `number`, `number`, `number`

-   The rotated coordinates of the point.

#### _Example:_

```lua
local newX, newY, newZ = _A.LibDraw:rotateX(0, 0, 0, 10, 0, 0, math.rad(45)) -- (1)
```

1. Perform a rotation operation around the X-axis in three-dimensional space. The function takes the center of rotation, coordinates of the point to be rotated, and the rotation angle in radians.

---

> ## rotateY

-   Rotate a point around the Y-axis using a specified center and angle.

#### Parameters

-   `cx`: The X-coordinate of the rotation center.
-   `cy`: The Y-coordinate of the rotation center.
-   `cz`: The Z-coordinate of the rotation center.
-   `px`: The X-coordinate of the point to be rotated.
-   `py`: The Y-coordinate of the point to be rotated.
-   `pz`: The Z-coordinate of the point to be rotated.
-   `angle`: The angle of rotation in radians.

#### Returns `number`, `number`, `number`

-   The rotated coordinates of the point.

#### _Example:_

```lua
local newX, newY, newZ = _A.LibDraw:rotateY(0, 0, 0, 10, 0, 0, math.rad(45)) -- (1)
```

1. Perform a rotation operation around the Y-axis in three-dimensional space. The function takes the center of rotation, coordinates of the point to be rotated, and the rotation angle in radians.

---

> ## rotateZ

-   Rotate a point around the Z-axis using a specified center and angle.

#### Parameters

-   `cx`: The X-coordinate of the rotation center.
-   `cy`: The Y-coordinate of the rotation center.
-   `cz`: The Z-coordinate of the rotation center.
-   `px`: The X-coordinate of the point to be rotated.
-   `py`: The Y-coordinate of the point to be rotated.
-   `pz`: The Z-coordinate of the point to be rotated.
-   `angle`: The angle of rotation in radians.

#### Returns `number`, `number`, `number`

-   The rotated coordinates of the point.

#### _Example:_

```lua
local newX, newY, newZ = _A.LibDraw:rotateZ(0, 0, 0, 10, 0, 0, math.rad(45)) -- (1)
```

1. Perform a rotation operation around the Z-axis in three-dimensional space. The function takes the center of rotation, coordinates of the point to be rotated, and the rotation angle in radians.

---

> ## ObjectDirection

-   Draw a line indicating the direction of an object in screen space.
    The function calculates the object's position and facing angle, then draws a line from the object's position to a point in the direction it is facing.

#### Parameters

-   `obj`(string): The object identifier.
-   `length`(number): [optional] The length of the direction indicator line. Defaults to 5 units.

#### _Example:_

```lua
local _A.LibDraw:ObjectDirection("target", 10) -- (1)
```

1. Draws a line from the 'target' object's position indicating its facing direction with a length of 10 units.

---

> ## Array

-   This function draws an array of lines on the screen.
    The lines are defined by pairs of coordinates in the `vectors` array.
    The function supports optional rotations around the X, Y, and Z axes.

#### Parameters

-   `vectors`(table): An array of coordinate pairs, each representing the start and end points of a line segment.
-   `x`: The X-coordinate of the reference point.
-   `y`: The Y-coordinate of the reference point.
-   `z`: The Z-coordinate of the reference point.
-   `rotationX`: [optional] - Rotation angle around the X-axis in radians.
-   `rotationY`: [optional] - Rotation angle around the Y-axis in radians.
-   `rotationZ`: [optional] - Rotation angle around the Z-axis in radians.

#### _Example:_

```lua
_A.LibDraw:Array({{0,0,0,10,0,0}, {0,0,0,0,10,0}, {0,0,0,0,0,10}}, 100, 100, 0, math.rad(45)) -- (1)
```

1. This example demonstrates how to use the \_A.LibDraw:Array function to draw an array of lines on the screen. Each line is defined by a pair of coordinate vectors in the input array. The function supports optional rotations around the X, Y, and Z axes.

---

> ## Box

-   This function draws a rotated box on the screen at the specified position `(x, y, z)`
    with the given width and rotation.

#### Parameters

-   `x`: The X-coordinate of the box's center.
-   `y`: The Y-coordinate of the box's center.
-   `z`: The Z-coordinate of the box's center.
-   `width`(number): The width of the box.
-   `widrotationth`(number): The rotation angle in radians for the box.
-   `offset_x`(number): [optional] - The X-axis offset of the box.
-   `offset_y`(number): [optional] - The Y-axis offset of the box.

#### _Example:_

```lua
_A.LibDraw:Box(100, 100, 0, 10, math.rad(45), 2, 2) -- (1)
```

1. Draws a rotated box centered at (100, 100, 0), with a width of 10, rotated by 45 degrees, and offset by 2 units along the X and Y.

---

> ## Cube

-   This function draws a cube on the screen at the specified position.
    The cube's shape is defined by a set of pre-defined coordinate vectors.
    The function automatically scales and positions the cube based on the provided coordinates.

#### Parameters

-   `x`: The X-coordinate of the cube's center.
-   `y`: The Y-coordinate of the cube's center.
-   `z`: The Z-coordinate of the cube's center.

#### _Example:_

```lua
_A.LibDraw:Cube(100, 100, 0) -- (1)
```

1. Draws a cube centered at (100, 100, 0).

---

> ## Circle

-   This function draws a circle on the screen at the specified position `(x, y, z)`.
    The circle's size can be adjusted using the `radius` parameter.
    If `ground` is set to `true`, the circle is projected onto the ground using a ray trace.

#### Parameters

-   `x`: The X-coordinate of the circle's center.
-   `y`: The Y-coordinate of the circle's center.
-   `z`: The Z-coordinate of the circle's center.
-   `radius`(number): [optional] - The size of the circle. Defaults to 1.
-   `ground`(bool): [optional] - If `true`, the circle is projected onto the ground using ray tracing.

#### _Example:_

```lua
_A.LibDraw:Circle(100, 100, 0, 2, true) -- (1)
```

1. Draws a circle with a radius of 2 at (100, 100, 0) projected onto the ground using ray tracing.

---

> ## Angle

-   This function draws an angle indicator on the screen at the specified position `(x, y, z)`.
    The angle is represented by two lines that originate from the center point and form an arc.

#### Parameters

-   `x`: The X-coordinate of the circle's center.
-   `y`: The Y-coordinate of the circle's center.
-   `z`: The Z-coordinate of the circle's center.
-   `size`(number): - The size of the angle indicator lines.
-   `arc`(number): - The angle in radians that the indicator lines form.
-   `angle`(number): - The angle in radians for the whole angle indicator.

#### _Example:_

```lua
_A.LibDraw:Angle(100, 100, 0, 15, math.rad(90), math.rad(45)) -- (1)
```

1. The indicator is centered at (100, 100, 0), has a size of 15 yards, forms a 90-degree angle, and is rotated by 45 degrees.

---

> ## Arc

-   This function draws an arc on the screen at the specified position `(x, y, z)`.
    The arc is defined by its size, arc angle, and rotation.
    Additional angle lines can be drawn if specified.

#### Parameters

-   `x`: The X-coordinate of the circle's center.
-   `y`: The Y-coordinate of the circle's center.
-   `z`: The Z-coordinate of the circle's center.
-   `size`(number): - The size of the arc.
-   `arc`(number): - The angle in radians that the arc spans.
-   `angle`(number): - The angle in radians for the whole arc.
-   `drawAngleLines`(bool): - If `true`, angle lines are drawn from the center point to the arc's endpoints.

#### _Example:_

```lua
_A.LibDraw:Arc(100, 100, 0, 20, math.rad(90), math.rad(45), true) -- (1)
```

1. Draws an arc centered at (100, 100, 0), with a size of 20 yards, spanning 90 degrees, rotated by 45 degrees, and angle lines are drawn.

---

> ## ObjectDirectionArc

-   This function draws an arc on the screen to indicate the direction of an object.
    The arc is centered at the object's position and extends in the direction the object is facing.

#### Parameters

-   `obj`(string): The object identifier.
-   `size`(number): - The size of the arc.
-   `arc`(number): - The angle in radians that the arc spans.
-   `angle`(number): - The angle in radians for the whole arc.

#### _Example:_

```lua
_A.LibDraw:ObjectDirectionArc('target', 10, math.rad(90)) -- (1)
```

1. Draws an arc centered at the 'target' object's position, extending 10 yards, spanning 90 degrees.

---

> ## Texture

-   This function draws a textured rectangle on the screen at the specified position `(x, y, z)`
    with the given texture configuration.
    The texture's appearance can be customized using various parameters in the `config` table.

#### Parameters

-   `config`(table): A table containing texture configuration parameters.
-   `x`: The X-coordinate of the texture's center.
-   `y`: The Y-coordinate of the texture's center.
-   `z`: The Z-coordinate of the texture's center.
-   `alpha`(number): - An [optional] alpha value to set the texture's transparency.

#### _Example:_

```lua
local textureConfig = {
    texture = "Interface\\Icons\\Spell_Nature_HealingWaveGreater", -- (1)
    width = 32, -- (2)
    height = 32, -- (3)
    left = 0, -- (4)
    right = 1, -- (5)
    top = 0, -- (6)
    bottom = 1, -- (7)
    scale = 1.0, -- (8)
    alpha = 0.8, -- (9)
}

_A.LibDraw:Texture(textureConfig, 100, 100, 0, 0.8) -- (10)
```

1. Specifies the texture path.
2. Sets the texture width.
3. Sets the texture height.
4. Defines the left texture coordinate.
5. Defines the right texture coordinate.
6. Defines the top texture coordinate.
7. Defines the bottom texture coordinate.
8. Sets the texture scale factor.
9. Optional transparency value.
10. Draws a textured rectangle with the provided configuration at (100, 100, 0).

---

> ## Text

-   This function displays text on the screen at the specified position `(x, y, z)`
    using a given font style.

#### Parameters

-   `text`(string): The text to be displayed.
-   `font`(FontObject): The font style to use for displaying the text.
-   `x`: The X-coordinate of the text's center.
-   `y`: The Y-coordinate of the text's center.
-   `z`: The Z-coordinate of the text's center.

#### _Example:_

```lua
local myFont = GameFontNormal -- (1)!

_A.LibDraw:Text("Hello, World!", myFont, 100, 100, 0) -- (2)!
```

1. Replace with your desired font object.
2. Displays "Hello, World!" using the specified font at (100, 100, 0).

---

> ## DrawHelper

-   This function draws coordinate axis helpers on the screen to indicate the X, Y, and Z directions.
    It includes arrows pointing along the corresponding axes, as well as text labels.

#### _Example:_

```lua
_A.LibDraw:DrawHelper() -- (1)
```

1. Draws coordinate axis helpers at the player's position.

---

> ## Distance

-   This function calculates the 3D distance between two points in space defined
    by their coordinates `(ax, ay, az)` and `(bx, by, bz)`.

#### Parameters

-   `ax`: The X-coordinate of the first point.
-   `ay`: The Y-coordinate of the first point.
-   `az`: The Z-coordinate of the first point.
-   `bx`: The X-coordinate of the second point.
-   `by`: The Y-coordinate of the second point.
-   `bz`: The Z-coordinate of the second point.

#### Return

-   `number`: The calculated 3D distance between the two points.

#### _Example:_

```lua
local distance = _A.LibDraw:Distance(0, 0, 0, 10, 10, 10) -- (1)
```

1. Calculates the distance between two points: (0, 0, 0) and (10, 10, 10).

---

> ## Camera

-   This function calculates the camera's position `(sX, sY, sZ)`
    and orientation angles in radians relative to the player's position `(fX, fY, fZ)`.

#### Return `sX`, `sY`, `sZ`, `yaw`, `pitch`

-   `sX`(number): The X-coordinate of the camera's position.
-   `sY`(number): The Y-coordinate of the camera's position.
-   `sZ`(number): The Z-coordinate of the camera's position.
-   `yaw`(number): The yaw angle (horizontal rotation) of the camera in radians.
-   `pitch`(number): The pitch angle (vertical rotation) of the camera in radians.

#### _Example:_

```lua
local camX, camY, camZ, camYaw, camPitch = _A.LibDraw:Camera() -- (1)
```

1. Gets the camera's position and orientation relative to the player.

---

> ## clearCanvas

-   This function hides all previously drawn textures, font strings,
    and lines on the drawing canvas. It clears the canvas for new drawings.

#### _Example:_

```lua
_A.LibDraw:clearCanvas() -- (1)
```

1. Hides all drawn elements on the canvas.

---

> ## Sync

-   This function allows you to register a callback function to be executed during the synchronization process.
    The callback function will be executed after all drawing operations have been performed,
    ensuring synchronization of the drawing sequence.

#### Parameters

-   `callback`(function): The callback function to be executed during synchronization.

#### _Example:_

```lua
local function myCallback()
    -- (1)
end
_A.LibDraw:Sync(myCallback) -- (2)
```

1. Perform drawing operations or actions here
2. Registers the callback function for synchronization.

---

> ## Enable

-   This function enables continuous drawing updates by creating a timer that calls
    the `OnUpdate` function at a fixed interval.
    The timer ensures that the drawing operations are updated periodically.

#### _Example:_

```lua
_A.LibDraw:Enable() -- (1)
```

1. Enables continuous drawing updates.

---

> ## Disable

-   This function disables continuous drawing updates by canceling the timer
    and clears the canvas of all drawn elements.

#### _Example:_

```lua
_A.LibDraw:Disable() -- (1)
```

1. Disables continuous drawing updates and clears the canvas.
