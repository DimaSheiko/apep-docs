# Vector API Reference

The Vector API provides comprehensive tools for creating and manipulating 2D and 3D vectors. These APIs are essential for geometric calculations, physics simulations, and spatial transformations.

---

## Vector2D

A 2D vector represents a point or direction in two-dimensional space with X and Y coordinates.

---

> ## Create

Creates a new 2D vector instance.

#### Parameters

-   `x` (number): The X coordinate.
-   `y` (number): The Y coordinate.

#### Returns `Vector2D`

-   A new Vector2D object.

#### _Example:_

```lua
local v = _A.Vector2D:Create(3, 4) -- (1)!
```

1. Creates a vector at position (3, 4).

---

> ## IsEqualTo

Checks if this vector is equal to another vector.

#### Parameters

-   `otherVector` (Vector2D): Another vector to compare.

#### Returns `boolean`

-   True if both X and Y components are equal.

#### _Example:_

```lua
local a = _A.Vector2D:Create(1, 2)
local b = _A.Vector2D:Create(1, 2)
print(a:IsEqualTo(b)) -- (1)!
```

1. Prints `true` since both vectors have identical coordinates.

---

> ## GetXY

Returns the X and Y coordinates of the vector.

#### Returns `number, number`

-   The X and Y components.

#### _Example:_

```lua
local v = _A.Vector2D:Create(3, 4)
local x, y = v:GetXY() -- (1)!
```

1. Returns x=3, y=4.

---

> ## SetXY

Sets the X and Y coordinates of the vector.

#### Parameters

-   `x` (number): The new X coordinate.
-   `y` (number): The new Y coordinate.

#### _Example:_

```lua
local v = _A.Vector2D:Create(0, 0)
v:SetXY(5, 6) -- (1)!
```

1. Updates the vector to position (5, 6).

---

> ## ScaleBy

Scales the vector by a given factor, modifying it in place.

#### Parameters

-   `scalar` (number): The multiplier.

#### _Example:_

```lua
local v = _A.Vector2D:Create(2, 3)
v:ScaleBy(2) -- (1)!
```

1. Doubles the vector components: v.x=4, v.y=6.

---

> ## DivideBy

Divides the vector by a given factor, modifying it in place.

#### Parameters

-   `scalar` (number): The divisor.

#### _Example:_

```lua
local v = _A.Vector2D:Create(4, 6)
v:DivideBy(2) -- (1)!
```

1. Halves the vector components: v.x=2, v.y=3.

---

> ## Add

Adds another vector to this vector, modifying it in place.

#### Parameters

-   `other` (Vector2D): The vector to add.

#### _Example:_

```lua
local a = _A.Vector2D:Create(1, 2)
local b = _A.Vector2D:Create(3, 4)
a:Add(b) -- (1)!
```

1. Vector `a` now contains (4, 6).

---

> ## Subtract

Subtracts another vector from this vector, modifying it in place.

#### Parameters

-   `other` (Vector2D): The vector to subtract.

#### _Example:_

```lua
local a = _A.Vector2D:Create(5, 6)
local b = _A.Vector2D:Create(2, 3)
a:Subtract(b) -- (1)!
```

1. Vector `a` now contains (3, 3).

---

> ## Cross

Computes the 2D cross product (scalar) with another vector.

#### Parameters

-   `other` (Vector2D): Another vector.

#### Returns `number`

-   The scalar cross product (x₁y₂ - y₁x₂).

#### _Example:_

```lua
local a = _A.Vector2D:Create(1, 0)
local b = _A.Vector2D:Create(0, 1)
print(a:Cross(b)) -- (1)!
```

1. Prints `1`, indicating perpendicular vectors.

---

> ## Dot

Computes the dot product with another vector.

#### Parameters

-   `other` (Vector2D): Another vector.

#### Returns `number`

-   The dot product.

#### _Example:_

```lua
local a = _A.Vector2D:Create(1, 2)
local b = _A.Vector2D:Create(3, 4)
print(a:Dot(b)) -- (1)!
```

1. Prints `11` (1×3 + 2×4).

---

> ## IsZero

Checks if the vector is zero (0, 0).

#### Returns `boolean`

-   True if both X and Y are 0.

#### _Example:_

```lua
local v = _A.Vector2D:Create(0, 0)
print(v:IsZero()) -- (1)!
```

1. Prints `true`.

---

> ## GetLengthSquared

Returns the squared length of the vector. More efficient than GetLength when comparing distances.

#### Returns `number`

-   Squared magnitude (x² + y²).

#### _Example:_

```lua
local v = _A.Vector2D:Create(3, 4)
print(v:GetLengthSquared()) -- (1)!
```

1. Prints `25` (3² + 4²).

---

> ## GetLength

Returns the length (magnitude) of the vector.

#### Returns `number`

-   Magnitude √(x² + y²).

#### _Example:_

```lua
local v = _A.Vector2D:Create(3, 4)
print(v:GetLength()) -- (1)!
```

1. Prints `5`.

---

> ## Normalize

Normalizes the vector to unit length (length = 1), modifying it in place.

#### _Example:_

```lua
local v = _A.Vector2D:Create(3, 4)
v:Normalize() -- (1)!
```

1. Vector `v` now has length 1: v.x=0.6, v.y=0.8.

---

> ## AngleBetween

Returns the angle (in radians) between this vector and another.

#### Parameters

-   `other` (Vector2D): Another vector.

#### Returns `number`

-   Angle in radians.

#### _Example:_

```lua
local a = _A.Vector2D:Create(1, 0)
local b = _A.Vector2D:Create(0, 1)
print(a:AngleBetween(b)) -- (1)!
```

1. Prints approximately `1.5708` (π/2 radians or 90 degrees).

---

> ## RotateDirection

Rotates the vector by a given angle in radians, modifying it in place.

#### Parameters

-   `rotationRadians` (number): The rotation angle in radians.

#### _Example:_

```lua
local v = _A.Vector2D:Create(1, 0)
v:RotateDirection(math.pi/2) -- (1)!
```

1. Rotates the vector 90 degrees: v.x≈0, v.y≈1.

---

> ## Clone

Returns a clone of the vector.

#### Returns `Vector2D`

-   A new vector with the same X and Y values.

#### _Example:_

```lua
local v1 = _A.Vector2D:Create(3, 4)
local v2 = v1:Clone() -- (1)!
```

1. Creates an independent copy of the vector.

---

## Vector2D Operators

Vector2D supports standard arithmetic operators for convenient mathematical operations.

---

> ## tostring

Converts the vector to a string representation.

#### _Example:_

```lua
local v = _A.Vector2D:Create(3, 4)
print(v) -- (1)!
```

1. Prints `Vector2D(3.000, 4.000)`.

---

> ## Addition (+)

Returns a new vector representing the sum of two vectors.

#### _Example:_

```lua
local a = _A.Vector2D:Create(1, 2)
local b = _A.Vector2D:Create(3, 4)
local c = a + b -- (1)!
print(c) -- (2)!
```

1. Creates a new vector without modifying `a` or `b`.
2. Prints `Vector2D(4.000, 6.000)`.

---

> ## Subtraction (-)

Returns a new vector representing the difference of two vectors.

#### _Example:_

```lua
local a = _A.Vector2D:Create(5, 6)
local b = _A.Vector2D:Create(2, 3)
local c = a - b -- (1)!
print(c) -- (2)!
```

1. Creates a new vector: c = (3, 3).
2. Prints `Vector2D(3.000, 3.000)`.

---

> ## Multiplication (*)

Returns a new vector scaled by a scalar value.

#### _Example:_

```lua
local v = _A.Vector2D:Create(2, 3)
local w = v * 2 -- (1)!
print(w) -- (2)!
```

1. Doubles the vector components.
2. Prints `Vector2D(4.000, 6.000)`.

---

> ## Division (/)

Returns a new vector divided by a scalar value.

#### _Example:_

```lua
local v = _A.Vector2D:Create(4, 6)
local w = v / 2 -- (1)!
print(w) -- (2)!
```

1. Halves the vector components.
2. Prints `Vector2D(2.000, 3.000)`.

---

> ## Equality (==)

Compares two vectors for equality.

#### _Example:_

```lua
local a = _A.Vector2D:Create(1, 2)
local b = _A.Vector2D:Create(1, 2)
print(a == b) -- (1)!
```

1. Prints `true` since coordinates match.

---

## Vector3D

A 3D vector represents a point or direction in three-dimensional space with X, Y, and Z coordinates.

---

> ## Create

Creates a new 3D vector instance.

#### Parameters

-   `x` (number): The X coordinate.
-   `y` (number): The Y coordinate.
-   `z` (number): The Z coordinate.

#### Returns `Vector3D`

-   A new Vector3D object.

#### _Example:_

```lua
local v = _A.Vector3D:Create(1, 2, 3) -- (1)!
```

1. Creates a vector at position (1, 2, 3).

---

> ## IsEqualTo

Checks if this vector is equal to another vector.

#### Parameters

-   `otherVector` (Vector3D): Another vector to compare.

#### Returns `boolean`

-   True if X, Y, and Z components are equal.

#### _Example:_

```lua
local a = _A.Vector3D:Create(1, 2, 3)
local b = _A.Vector3D:Create(1, 2, 3)
print(a:IsEqualTo(b)) -- (1)!
```

1. Prints `true` since all coordinates match.

---

> ## GetXYZ

Returns the X, Y, and Z coordinates of the vector.

#### Returns `number, number, number`

-   The X, Y, and Z components.

#### _Example:_

```lua
local v = _A.Vector3D:Create(3, 4, 5)
local x, y, z = v:GetXYZ() -- (1)!
```

1. Returns x=3, y=4, z=5.

---

> ## SetXYZ

Sets the X, Y, and Z coordinates of the vector.

#### Parameters

-   `x` (number): The new X coordinate.
-   `y` (number): The new Y coordinate.
-   `z` (number): The new Z coordinate.

#### _Example:_

```lua
local v = _A.Vector3D:Create(0, 0, 0)
v:SetXYZ(1, 2, 3) -- (1)!
```

1. Updates the vector to position (1, 2, 3).

---

> ## ScaleBy

Scales the vector by a given factor, modifying it in place.

#### Parameters

-   `scalar` (number): The multiplier.

#### _Example:_

```lua
local v = _A.Vector3D:Create(1, 2, 3)
v:ScaleBy(2) -- (1)!
```

1. Doubles all components: v.x=2, v.y=4, v.z=6.

---

> ## DivideBy

Divides the vector by a given factor, modifying it in place.

#### Parameters

-   `scalar` (number): The divisor.

#### _Example:_

```lua
local v = _A.Vector3D:Create(2, 4, 6)
v:DivideBy(2) -- (1)!
```

1. Halves all components: v.x=1, v.y=2, v.z=3.

---

> ## Add

Adds another vector to this vector, modifying it in place.

#### Parameters

-   `other` (Vector3D): The vector to add.

#### _Example:_

```lua
local a = _A.Vector3D:Create(1, 2, 3)
local b = _A.Vector3D:Create(4, 5, 6)
a:Add(b) -- (1)!
```

1. Vector `a` now contains (5, 7, 9).

---

> ## Subtract

Subtracts another vector from this vector, modifying it in place.

#### Parameters

-   `other` (Vector3D): The vector to subtract.

#### _Example:_

```lua
local a = _A.Vector3D:Create(5, 7, 9)
local b = _A.Vector3D:Create(1, 2, 3)
a:Subtract(b) -- (1)!
```

1. Vector `a` now contains (4, 5, 6).

---

> ## Cross

Computes the 3D cross product with another vector, modifying this vector in place.

#### Parameters

-   `other` (Vector3D): Another vector.

#### _Example:_

```lua
local a = _A.Vector3D:Create(1, 0, 0)
local b = _A.Vector3D:Create(0, 1, 0)
a:Cross(b) -- (1)!
```

1. Vector `a` now contains (0, 0, 1), perpendicular to both original vectors.

---

> ## Dot

Computes the dot product with another vector.

#### Parameters

-   `other` (Vector3D): Another vector.

#### Returns `number`

-   The dot product.

#### _Example:_

```lua
local a = _A.Vector3D:Create(1, 2, 3)
local b = _A.Vector3D:Create(4, 5, 6)
print(a:Dot(b)) -- (1)!
```

1. Prints `32` (1×4 + 2×5 + 3×6).

---

> ## GetLengthSquared

Returns the squared length of the vector. More efficient than GetLength when comparing distances.

#### Returns `number`

-   Squared magnitude (x² + y² + z²).

#### _Example:_

```lua
local v = _A.Vector3D:Create(1, 2, 2)
print(v:GetLengthSquared()) -- (1)!
```

1. Prints `9` (1² + 2² + 2²).

---

> ## GetLength

Returns the length (magnitude) of the vector.

#### Returns `number`

-   Magnitude √(x² + y² + z²).

#### _Example:_

```lua
local v = _A.Vector3D:Create(1, 2, 2)
print(v:GetLength()) -- (1)!
```

1. Prints `3`.

---

> ## Normalize

Normalizes the vector to unit length (length = 1), modifying it in place.

#### _Example:_

```lua
local v = _A.Vector3D:Create(1, 2, 2)
v:Normalize() -- (1)!
```

1. Vector `v` now has length 1: v.x≈0.333, v.y≈0.667, v.z≈0.667.

---

> ## Clone

Returns a clone of the vector.

#### Returns `Vector3D`

-   A new vector with the same X, Y, and Z values.

#### _Example:_

```lua
local v1 = _A.Vector3D:Create(1, 2, 3)
local v2 = v1:Clone() -- (1)!
```

1. Creates an independent copy of the vector.

---

> ## AddVector

Adds two vectors and returns a new Vector3D without modifying the originals.

#### Parameters

-   `other` (Vector3D): The vector to add.

#### Returns `Vector3D`

-   A new vector representing the sum.

#### _Example:_

```lua
local a = _A.Vector3D:Create(1, 1, 1)
local b = _A.Vector3D:Create(2, 2, 2)
local c = a:AddVector(b) -- (1)!
print(c:GetXYZ()) -- (2)!
```

1. Creates a new vector without modifying `a` or `b`.
2. Prints `3, 3, 3`.

---

> ## SubtractVector

Subtracts two vectors and returns a new Vector3D without modifying the originals.

#### Parameters

-   `other` (Vector3D): The vector to subtract.

#### Returns `Vector3D`

-   A new vector representing the difference.

#### _Example:_

```lua
local a = _A.Vector3D:Create(3, 3, 3)
local b = _A.Vector3D:Create(1, 1, 1)
local c = a:SubtractVector(b) -- (1)!
print(c:GetXYZ()) -- (2)!
```

1. Creates a new vector: c = a - b.
2. Prints `2, 2, 2`.

---

> ## NormalizeVector

Normalizes the vector and returns a new Vector3D without modifying the original.

#### Returns `Vector3D`

-   A new normalized vector with length 1.

#### _Example:_

```lua
local v = _A.Vector3D:Create(1, 2, 2)
local n = v:NormalizeVector() -- (1)!
print(n:GetLength()) -- (2)!
```

1. Original vector `v` remains unchanged.
2. Prints `1`.

---

> ## ScaleVector

Scales the vector and returns a new Vector3D without modifying the original.

#### Parameters

-   `scalar` (number): The multiplier.

#### Returns `Vector3D`

-   A new scaled vector.

#### _Example:_

```lua
local v = _A.Vector3D:Create(1, 2, 3)
local s = v:ScaleVector(2) -- (1)!
print(s:GetXYZ()) -- (2)!
```

1. Original vector `v` remains unchanged.
2. Prints `2, 4, 6`.

---

> ## NormalFromYawPitch

Returns a normal vector's coordinates from yaw and pitch angles.

#### Parameters

-   `yaw` (number): Rotation around the Z axis in radians.
-   `pitch` (number): Rotation around the Y axis in radians.

#### Returns `number, number, number`

-   The X, Y, Z coordinates of the normal vector.

#### _Example:_

```lua
local x, y, z = _A.Vector3D:NormalFromYawPitch(math.pi/2, 0) -- (1)!
```

1. Computes the normal vector pointing in the specified direction.

---

> ## NormalVectorFromYawPitch

Returns a Vector3D object from yaw and pitch angles.

#### Parameters

-   `yaw` (number): Rotation around the Z axis in radians.
-   `pitch` (number): Rotation around the Y axis in radians.

#### Returns `Vector3D`

-   A new normalized vector pointing in the specified direction.

#### _Example:_

```lua
local v = _A.Vector3D:NormalVectorFromYawPitch(math.pi/2, 0) -- (1)!
print(v:GetXYZ())
```

1. Creates a unit vector from angular coordinates.

---

> ## YawPitchFromNormal

Computes yaw and pitch angles from X, Y, Z coordinates.

#### Parameters

-   `x` (number): The X coordinate.
-   `y` (number): The Y coordinate.
-   `z` (number): The Z coordinate.

#### Returns `number, number`

-   The yaw and pitch in radians.

#### _Example:_

```lua
local yaw, pitch = _A.Vector3D:YawPitchFromNormal(1, 0, 0) -- (1)!
```

1. Converts Cartesian coordinates to angular representation.

---

> ## YawPitchFromVector

Computes yaw and pitch angles from the vector itself.

#### Returns `number, number`

-   The yaw and pitch in radians.

#### _Example:_

```lua
local v = _A.Vector3D:Create(1, 0, 0)
local yaw, pitch = v:YawPitchFromVector() -- (1)!
```

1. Extracts angular information from the vector's direction.

---

## Common Use Cases

### Distance Calculation

```lua
local pos1 = _A.Vector2D:Create(0, 0)
local pos2 = _A.Vector2D:Create(3, 4)
local diff = pos2 - pos1
local distance = diff:GetLength()
print(distance) -- (1)!
```

1. Prints `5`, the distance between the two points.

### Direction Vector

```lua
local from = _A.Vector3D:Create(0, 0, 0)
local to = _A.Vector3D:Create(10, 0, 0)
local direction = to:SubtractVector(from)
direction:Normalize() -- (1)!
```

1. Creates a unit vector pointing from `from` to `to`.

### Vector Projection

```lua
local a = _A.Vector2D:Create(3, 4)
local b = _A.Vector2D:Create(1, 0)
local projection = (a:Dot(b) / b:GetLengthSquared()) * b -- (1)!
```

1. Projects vector `a` onto vector `b`.

### Perpendicular Vector (2D)

```lua
local v = _A.Vector2D:Create(1, 0)
v:RotateDirection(math.pi/2) -- (1)!
print(v:GetXY()) -- (2)!
```

1. Rotates 90 degrees to get perpendicular vector.
2. Prints approximately `0, 1`.

---

## Performance Tips

-   Use `GetLengthSquared()` instead of `GetLength()` when comparing distances to avoid expensive square root calculations.
-   Use in-place methods (`Add`, `Subtract`, `Normalize`) when you don't need to preserve the original vector.
-   Use immutable methods (`AddVector`, `SubtractVector`, `ScaleVector`) when you need to keep the original vector unchanged.
-   Cache frequently used vectors instead of recreating them every frame.

