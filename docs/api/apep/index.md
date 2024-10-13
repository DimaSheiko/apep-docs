# APEP API Reference

---

> ## lTrim

-   This function removes leading whitespace characters (spaces, tabs, etc.) from a string.

#### Parameters

-   `str`(string): The input string to be trimmed.

#### Returns `string`

-   The input string with leading whitespace removed.

#### _Example:_

```lua
local trimmedString = _A.lTrim("    Hello, world!") -- (1)!
```

1. Removes leading whitespace characters.

---

> ## rTrim

-   This function removes trailing whitespace characters (spaces, tabs, etc.) from a string.

#### Parameters

-   `str`(string): The input string to be trimmed.

#### Returns `string`

-   The input string with trailing whitespace removed.

#### _Example:_

```lua
local trimmedString = _A.rTrim("Hello, world!    ") -- (1)!
```

1. Removes trailing whitespace characters.

---

> ## Trim

-   This function removes both leading and trailing whitespace characters (spaces, tabs, etc.) from a string.

#### Parameters

-   `str`(string): The input string to be trimmed.

#### Returns `string`

-   The input string with leading and trailing whitespace removed.

#### _Example:_

```lua
local trimmedString = _A.Trim("    Hello, world!    ") -- (1)!
```

1. Removes leading and trailing whitespace characters.

---

> ## print

-   This function prints the specified arguments to the console with colorful output.

#### Parameters

-   `...`(any): The arguments to print.

#### _Example:_

```lua
local mergedTable = _A.print("Hello", "world", "!") -- (1)!
```

1. Prints the provided arguments with colorful output.

---

> ## RandomNumber

-   This function generates a random number within the specified range.

#### Parameters

-   `min`(number): The minimum value of the random number range.
-   `max`(number): The maximum value of the random number range.

#### Returns `number`

-   A random number within the specified range.

#### _Example:_

```lua
local randomValue = _A.RandomNumber(1, 100) -- (1)!
```

1. Generates a random number between 1 and 100.

---

> ## RandomString

-   This function generates a random string of the specified length, containing both lowercase letters and digits.

#### Parameters

-   `length`(number): The length of the random string to generate.

#### Returns `string`

-   A random string of the specified length, containing a mix of lowercase letters and digits.

#### _Example:_

```lua
local randomStr = _A.RandomString(10) -- (1)!
```

1. Generates a random string of length 10.

---

> ## ApepMod

-   This function calculates the remainder of the division of two numbers using the Mod algorithm. The algorithm ensures that the result is always positive and between 0 and b. It calculates the remainder by subtracting the floor division of a by b multiplied by b from a.

#### Parameters

-   `a`(number): The dividend for which the remainder is calculated.
-   `b`(number): The divisor.

#### Returns

-   `remainder`(number): The remainder of the division.

#### _Example:_

```lua
local result = _A.ApepMod(25, 7)
```

---

> ## TableMerge

-   This function merges the contents of two tables.
    If a key in both tables corresponds to a table value, the function recursively merges those nested tables.

#### Parameters

-   `t1`(table): The first table to merge.
-   `t2`(table): The second table to merge.

#### Returns `table`

-   A table containing the merged contents of the two input tables.

#### _Example:_

```lua
local table1 = { a = 1, b = { x = 2, y = 3 } }
local table2 = { b = { y = 4, z = 5 }, c = 6 }
local mergedTable = _A.TableMerge(table1, table2) -- (1)!
```

1. Merges the contents of the two tables.

---

> ## StrExplode

-   This function takes a string and a delimiter character, and returns a table of substrings
    obtained by splitting the input string at occurrences of the delimiter.

#### Parameters

-   `str`(string): The input string to be exploded.

#### Returns `...`

-   Multiple return values representing the substrings obtained after splitting.

#### _Example:_

```lua
local first, second, third = _A.StrExplode("apple,banana,orange", ",") -- (1)!
```

1. Splits the input string into substrings.

---

> ## BagSpace

-   This function calculates the total number of free slots available across all bags.

#### Returns `number`

-   The total number of free slots available across all bags.

#### _Example:_

```lua
-- Get the total number of free slots across all bags
local freeSlots = _A.BagSpace()
print("Total free slots:", freeSlots)
```

---

> ## SlotAlias

| SlotAlias                           | InventorySlotName | SlotNumber |
| ----------------------------------- | ----------------- | ---------- |
| `head` or `helm`                    | HeadSlot          | 1          |
| `neck`                              | NeckSlot          | 2          |
| `shoulder`                          | ShoulderSlot      | 3          |
| `shirt`                             | ShirtSlot         | 4          |
| `chest`                             | ChestSlot         | 5          |
| `belt` or `waist`                   | WaistSlot         | 6          |
| `legs` or `pants`                   | LegsSlot          | 7          |
| `feet` or `boots`                   | FeetSlot          | 8          |
| `wrist` or `bracers`                | WristSlot         | 9          |
| `gloves` or `hands`                 | HandsSlot         | 10         |
| `finger1`                           | Finger0Slot       | 11         |
| `finger2`                           | Finger1Slot       | 12         |
| `trinket1`                          | Trinket0Slot      | 13         |
| `trinket2`                          | Trinket1Slot      | 14         |
| `back` or `cloak`                   | BackSlot          | 15         |
| `mainhand` or `weapon` or `weapon1` | MainHandSlot      | 16         |
| `offhand` or `weapon2`              | SecondaryHandSlot | 17         |
| `ranged`                            | RangedSlot        | 18         |
| `tabard`                            | TabardSlot        | 19         |

---

> ## ItemEquip

-   This function equips an item in the specified slot.

#### Parameters

-   `NameOrID`(string/number): The item name/ID.
-   `NameOrSlot`(string/number): The slot name/number.

#### Returns `nil`

#### _Example:_

```lua
-- Equip an item named "Sickle Axe" to the main hand slot
_A.ItemEquip("Sickle Axe", "MainHand")
-- Equip an item with ID 1602 to the SlotNumber 16 (Main Hand)
_A.ItemEquip(1602, 16)
```

---

> ## ItemUnequip

-   This function unequips an item from a specified slot and places it in the backpack.

#### Parameters

-   `NameOrSlot`(string/number): The slot name/number.

#### Returns `number`

-   `Id`(number): The ID of the unequipped item, or -1 if no item was found in the slot.

#### _Example:_

```lua
-- Unequip the Main Hand weapon
_A.ItemUnequip("MainHand")
-- Unequip the slot 16, where 16 is the SlotNumber for Main Hand
_A.ItemUnequip(16)
```

---

> ## GetObjectCount

-   This function returns the total number of objects currently present in the object manager.

#### Returns

-   `count`(number): The number of objects in the object manager.

!> **DEPRECATED**

#### _Example:_

```lua
local objectCount = _A.GetObjectCount() -- (1)!
```

1. Retrieves the total number of objects in the object manager.

---

> ## GetObjectWithIndex

-   This function takes an index as input and returns the pointer of the object with that index in the object manager.

#### Parameters

-   `index`(number): The index of the object to retrieve the pointer for.

#### Returns

-   `pointer`(string): The pointer of the object with the specified index.

!> **DEPRECATED**

#### _Example:_

```lua
local objectCount = _A.GetObjectCount() -- (1)!

for i=1, objectCount do -- (2)!
  print(_A.GetObjectWithIndex(i))
end
```

1. Retrieves the total number of objects in the object manager.
2. Iterate through each object index and print its pointer.

---

> ## ObjectPointer

#### Parameters

-   `object`(string): The object.

#### Returns `string` or `nil`

-   The pointer as a `hexadecimal string` prefixed by 0x, or `nil` if the object does not exist.

!>**Note:** If the object doesn't exist, for example, ObjectPointer("party1target"), it returns nil. This API is mainly useful to get the object address of unitIDs like "target", "mouseover", etc. ObjectPointer("0xDEADBEEF") simply returns "0xDEADBEEF" and does NOT check if the address exists in the object manager. Avoid using this for arbitrary addresses.

#### _Example:_

```lua
_A.ObjectPointer("raid1")
```

---

> ## ObjectExists

-   Get whether an object exists in the object manager with O(n) performance.

#### Parameters

-   `object`(string): The object.

#### Returns `bool`

-   `true` if object exists in the object manager, `false` otherwise.

#### _Example:_

```lua
_A.ObjectExists("part1target")
```

---

> ## ObjectIsVisible

-   Get whether an object is visible in the object manager with O(1) performance.

#### Parameters

-   `object`(string): The object.

#### Returns `bool`

-   `true` if object is visible, `false` otherwise.

#### _Example:_

```lua
_A.ObjectIsVisible("0x10AE05BD")
```

---

> ## ObjectPosition

-   Get an object's position.

#### Parameters

-   `object`(string): The object.

#### Returns `number`, `number`, `number`

-   The x, y, and z coordinates

!>**Note:** If the object doesn't exist, it returns (nil, nil, nil)

#### _Example:_

```lua
_A.ObjectPosition("mouseover")
```

---

> ## ObjectFacing

-   Get an object's facing.

#### Parameters

-   `object`(string): The object.

#### Returns `number`

-   The facing (angle in xy) in radians

!>**Note:** If the object doesn't exist, it returns nil.

#### _Example:_

```lua
_A.ObjectFacing("player")
```

---

> ## ObjectCreator

-   This function retrieves the GUID of the creator who created the specified fishing bobber object.

#### Parameters

-   `object`(string): The pointer of the object for which to retrieve the creator's pointer.

#### Return `string`

-   The pointer of the unit who created the object, or nil if the object or its creator's pointer is not available.

#### _Example:_

```lua
local objectPointer = "0x01234567"
local unitPointer = _A.ObjectCreator(objectPointer) -- (1)!
```

1. Retrieves the pointer of the creator of the specified object.

---

> ## BobberCreator

-   This function retrieves the GUID of the creator of the fishing bobber object.

#### Parameters

-   `object`(string): The pointer of the fishing bobber object for which to retrieve the creator's GUID.

#### Returns `string`

-   The GUID of the creator who created the fishing bobber object, or nil if the object is not a valid.

#### _Example:_

```lua
local bobberPointer = "0x01234567"
local creatorGUID = _A.BobberCreator(bobberPointer) -- (1)!
```

1. Retrieves the GUID of the creator of the fishing bobber.

---

> ## BobberIsAnimating

-   This function checks whether the specified fishing bobber object is currently animating,
    indicating that it has caught a fish.

#### Parameters

-   `object`(string): The fishing bobber object to check for animation.

#### Returns `bool`

-   `true` if the fishing bobber object is animating, indicating it has caught a fish, `false` otherwise.

#### _Example:_

```lua
local bobberPointer = "0x01234567"
local isAnimating = _A.BobberIsAnimating(bobberPointer) -- (1)!
```

1. Checks if the specified fishing bobber object is animating.

---

> ## UnitTarget

-   This function takes a unit object and returns the target of that unit as its pointer and GUID.

#### Parameters

-   `object`(string): The unit object for which to retrieve the target.

#### Returns `pointer`, `guid`

-   `pointer`(string): The pointer of the unit's target.
-   `guid`(string): The GUID of the unit's target.

#### _Example:_

```lua
local pointer, GUID = _A.UnitTarget("mouseover") -- (1)!
```

1. Retrieves the target of the 'mouseover'.

---

> ## UnitCastID

-   This function takes a unit object as a parameter and returns information about the unit's current cast, including its cast ID, pointer, and GUID.

#### Parameters

-   `object`(string): The unit object for which to retrieve the cast information.

#### Returns `castId`, `pointer`, `guid`

-   `castId`(number): The cast ID of the unit's current cast.
-   `pointer`(string): The pointer of the unit's cast.
-   `guid`(string): The GUID of the unit's cast.

#### _Example:_

```lua
local castId, tarPointer, tarGUID = _A.UnitCastID("target") -- (1)!
if castId==12345 then
    -- (2)!
end
```

1. Retrieves the cast information of the 'target' unit.
2. Do something

---

> ## UnitIsFacing

-   This function checks whether the first unit is facing the second unit within the specified angle range.

#### Parameters

-   `object1`(string): The pointer or unitId of the first unit.
-   `object2`(string): The pointer or unitId of the second unit.
-   `angle`(number): [`optional`] The angle range (in degrees) within which the first unit is considered to be facing the second unit. Default is 180 degrees.

#### Returns

-   `isFacing`(bool): `true` if the first unit is facing the second unit within the specified angle range, `false` otherwise.

#### _Example:_

```lua
local angleThreshold = 90
local isFacingTarget = _A.UnitIsFacing("player", "target", angleThreshold) -- (1)!
```

1. Checks if the player is facing the target within a 90-degree angle.

---

> ## PositionIsFacingPosition

-   This function checks whether a position (defined by coordinates and facing angle) is facing another position within the specified angle range.

#### Parameters

-   `oX`(number): The X-coordinate of the position from which the facing angle originates.
-   `oY`(number): The Y-coordinate of the position from which the facing angle originates.
-   `dX`(number): The X-coordinate of the position to which the facing angle is directed.
-   `dY`(number): The Y-coordinate of the position to which the facing angle is directed.
-   `oFacing`(number): The facing angle (in radians) of the origin position.
-   `angle`(number): [`optional`] The angle range (in degrees) within which the origin position is considered to be facing the target position. Default is 180 degrees.

#### Returns

-   `isFacing`(bool): `true` if the origin position is facing the target position within the specified angle range, `false` otherwise.

#### _Example:_

```lua
local playerX, playerY = _A.ObjectPosition("player")
local playerFacing = _A.ObjectFacing("player")
local targetX, targetY = _A.ObjectPosition("target")
local angleThreshold = 90
local isFacingTarget = _A.PositionIsFacingPosition(playerX, playerY, targetX, targetY, playerFacing, angleThreshold)
```

---

> ## ObjectID
>
> _`ObjectID || ObjectEntry`_

-   This function retrieves the entry ID of an object identified by its pointer.

#### Parameters

-   `object`(string): The pointer or object identifier (e.g., "player", "target", or a pointer value).

#### Returns

-   `entryID`(number): The entry ID of the object, or `nil` if the object pointer is invalid or not found.

#### _Example:_

```lua
local targetEntryID = _A.ObjectID("target")
```

---

> ## ObjectID_GUID

-   This function retrieves the entry ID and GUID of an object identified by its pointer or object identifier.

#### Parameters

-   `object`(string): The pointer or object identifier (e.g., "player", "target", or a pointer value).

#### Returns `entryID`, `guid`

-   `entryID`(number): The entry ID of the object, or `nil` if the object pointer is invalid or not found.
-   `guid`(string): The GUID of the object, or `nil` if the object pointer is invalid or not found.

#### _Example:_

```lua
local targetEntryID, targetGUID = _A.ObjectID_GUID("target")
```

---

> ## ObjectRawType

-   This function retrieves the raw type of an object identified by its pointer or object identifier. The raw type provides information about the object's category, such as player, unit, item, game object, etc.

#### Parameters

-   `object`(string): The pointer or object identifier (e.g., "player", "target", or a pointer value).

#### Returns

-   `objectType`(number): The raw type of the object, or `nil` if the object pointer is invalid or not found.

#### _Example:_

```lua
local targetType = _A.ObjectRawType("target")
```

---

> ## ObjectIsUnit

-   This function checks whether the specified object is of the type "Unit", or any related subtypes such as "Player" or "ActivePlayer".

#### Parameters

-   `object`(string): The pointer or object identifier of the object to check.

#### Returns

-   `isUnit`(bool): `true` if the object is a unit or related subtype, `false` otherwise.

#### _Example:_

```lua
local isUnit = _A.ObjectIsUnit("target")
```

---

> ## ObjectIsPlayer

-   This function checks whether the specified object is of the type "Player" or "ActivePlayer".

#### Parameters

-   `object`(string): The pointer or object identifier of the object to check.

#### Returns

-   `isPlayer`(bool): `true` if the object is a player or active player, `false` otherwise.

#### _Example:_

```lua
local isPlayer = _A.ObjectIsPlayer("target")
```

---

> ## ObjectIsGameObject

-   This function checks whether the specified object is of the type "GameObject".

#### Parameters

-   `object`(string): The pointer or object identifier of the object to check.

#### Returns

-   `isGameObject`(bool): `true` if the object is a game object, `false` otherwise.

#### _Example:_

```lua
local isGameObject = _A.ObjectIsGameObject("0x12345678")
```

---

> ## ObjectIsAreaTrigger

-   This function checks whether the specified object is of the type "AreaTrigger".

#### Parameters

-   `object`(string): The pointer or object identifier of the object to check.

#### Returns

-   `isAreaTrigger`(bool): `true` if the object is an area trigger, `false` otherwise.

#### _Example:_

```lua
local isAreaTrigger = _A.ObjectIsAreaTrigger("0x12345678")
```

---

> ## UnitCombatReach

-   This function retrieves the combat reach (melee attack range) of the specified unit.

#### Parameters

-   `object`(string): The pointer or unit identifier of the unit to get the combat reach for.

#### Returns

-   `combatReach`(number): The combat reach of the unit, in yards.

#### _Example:_

```lua
local targetCombatReach = _A.UnitCombatReach("target")
```

---

> ## UnitHeight

-   This function retrieves the height of the specified unit.

#### Parameters

-   `object`(string): The pointer or unit identifier of the unit to get the height for.

#### Returns

-   `height`(number): The height of the unit, in yards.

#### _Example:_

```lua
local playerHeight = _A.UnitHeight("player")
```

---

> ## UnitBoundingRadius

-   This function retrieves the bounding radius of the specified unit.

#### Parameters

-   `object`(string): The pointer or unit identifier of the unit to get the bounding radius for.

#### Returns

-   `height`(number): The bounding radius of the unit, in yards.

#### _Example:_

```lua
local playerBoundingRadius = _A.UnitBoundingRadius("player")
```

---

> ## GetObjectWithGUID

-   This function retrieves the object's pointer using its globally unique identifier (GUID).

#### Parameters

-   `guid`(string): The GUID of the object.

#### Returns

-   `pointer`(number|nil): The pointer of the object, or `nil` if the object was not found.

#### _Example:_

```lua
local guid = _G.UnitGUID("target")
local targetPointer = _A.GetObjectWithGUID(guid)
```

---

> ## GetDistanceBetweenPositions

-   This function calculates the Euclidean distance between two 3D positions in the game world.

#### Parameters

-   `X1`(number): The X coordinate of the first position.
-   `Y1`(number): The Y coordinate of the first position.
-   `Z1`(number): The Z coordinate of the first position.
-   `X2`(number): The X coordinate of the second position.
-   `Y2`(number): The Y coordinate of the second position.
-   `Z2`(number): The Z coordinate of the second position.

#### Returns

-   `distance`(number): The distance between the two positions.

#### _Example:_

```lua
local distance = _A.GetDistanceBetweenPositions(100, 200, 0, 150, 250, 10)
print("Distance:", distance)
```

---

> ## GetDistanceBetweenObjects

-   This function calculates the distance between two objects.

#### Parameters

-   `object1`(string): The unitId or pointer of the first game object.
-   `object2`(string): The unitId or pointer of the second game object.

#### Returns

-   `distance`(number): The distance between the two objects, or nil if positions couldn't be retrieved.

#### _Example:_

```lua
local distance = _A.GetDistanceBetweenObjects("player", "0x87654321")
print("Distance:", distance)
```

---

> ## GetRangeBetweenObjects

-   This function calculates the range between two objects while taking into account their combat reach.

#### Parameters

-   `object1`(string): The unitId or pointer of the first game object.
-   `object2`(string): The unitId or pointer of the second game object.

#### Returns

-   `range`(number): The effective range between the two objects, considering combat reaches.

#### _Example:_

```lua
local range = _A.GetRangeBetweenObjects("player", "0x87654321")
print("Range:", range)
```

---

> ## GetPositionFromPosition

-   This function calculates a new position in three-dimensional space based on a starting position (X, Y, Z), a specified distance, and two angles (Angle1 and Angle2). It uses trigonometric functions to calculate the new coordinates and returns the calculated X, Y, and Z values.

#### Parameters

-   `X`(number): The X coordinate of the starting position.
-   `Y`(number): The Y coordinate of the starting position.
-   `Z`(number): The Z coordinate of the starting position.
-   `Distance`(number): The distance from the starting position to the new position.
-   `Angle1`(number): The angle (in radians) in the XY plane (horizontal plane) from the positive X-axis.
-   `Angle2`(number): The angle (in radians) between the XY plane and the line connecting the starting position and the new position.

#### Returns `newX`, `newY`, `newZ`

-   `newX`(number): The calculated X coordinate of the new position.
-   `newY`(number): The calculated Y coordinate of the new position.
-   `newZ`(number): The calculated Z coordinate of the new position.

#### _Example:_

```lua
local newX, newY, newZ = _A.GetPositionFromPosition(100, 100, 0, 10, math.rad(45), math.rad(30))
print("Distance:", distance)
```

---

> ## GetAnglesBetweenPositions

-   This function calculates the yaw and pitch angles between two 3D positions.

#### Parameters

-   `X1`(number): The X coordinate of the first position.
-   `Y1`(number): The Y coordinate of the first position.
-   `Z1`(number): The Z coordinate of the first position.
-   `X2`(number): The X coordinate of the second position.
-   `Y2`(number): The Y coordinate of the second position.
-   `Z2`(number): The Z coordinate of the second position.

#### Returns `pitch`, `yaw`

-   `yaw`(number): The yaw angle in radians between the two positions.
-   `pitch`(number): The pitch angle in radians between the two positions.

#### _Example:_

```lua
local yaw, pitch = _A.GetAnglesBetweenPositions(0, 0, 0, 10, 10, 10)
print("Yaw angle:", yaw) -- (1)!
print("Pitch angle:", pitch) -- (2)!
```

1. left-right rotation around the Z axis.
2. up-down rotation around the X axis.

---

> ## GetAnglesBetweenObjects

-   This function calculates the yaw and pitch angles between two objects.

#### Parameters

-   `object1`(string): The unitId or pointer of the first game object.
-   `object2`(string): The unitId or pointer of the second game object.

#### Returns

-   `yaw`(number): The yaw angle in radians between the two objects.
-   `pitch`(number): The pitch angle in radians between the two objects.

#### _Example:_

```lua
local yaw, pitch = _A_.GetAnglesBetweenObjects("player", "target")
print("Yaw angle:", yaw) -- (1)!
print("Pitch angle:", pitch) -- (2)!
```

1. left-right rotation around the Z axis.
2. up-down rotation around the X axis.

---

> ## GetPositionBetweenPositions

-   This function calculates a new position between two given positions based on a specified distance.

#### Parameters

-   `X1`(number): The X coordinate of the first position.
-   `Y1`(number): The Y coordinate of the first position.
-   `Z1`(number): The Z coordinate of the first position.
-   `X2`(number): The X coordinate of the second position.
-   `Y2`(number): The Y coordinate of the second position.
-   `Z2`(number): The Z coordinate of the second position.
-   `distance`(number): The distance from the first position where the new position should be calculated.

#### Returns `newX`, `newY`, `newZ`

-   `newX`(number): The X coordinate of the new position.
-   `newY`(number): The Y coordinate of the new position.
-   `newZ`(number): The Z coordinate of the new position.

#### _Example:_

```lua
local newX, newY, newZ = _A.GetPositionBetweenPositions(100, 200, 0, 150, 250, 0, 10)
print("New position:", newX, newY, newZ)
```

---

> ## GetPositionBetweenObjects

-   This function calculates a new position between the positions of two given objects based on a specified distance from the first object.

#### Parameters

-   `object1`(string): The unitId or pointer identifier of the first object.
-   `object1`(string): The unitId or pointer identifier of the second object.
-   `distance`(number): The distance from the first object where the new position should be calculated.

#### Returns `newX`, `newY`, `newZ`

-   `newX`(number): The X coordinate of the new position.
-   `newY`(number): The Y coordinate of the new position.
-   `newZ`(number): The Z coordinate of the new position.

#### _Example:_

```lua
local newX, newY, newZ = _A.GetPositionBetweenObjects("player", "0x789ABC", 10)
print("New position:", newX, newY, newZ)
```

---

> ## ObjectIsFacing

-   This function checks if the first object is facing the second object.

#### Parameters

-   `object1`(string): The unitId or pointer identifier of the first object.
-   `object1`(string): The unitId or pointer identifier of the second object.

#### Returns

-   `isFacing`(bool): `true` if the first object is facing the second object, otherwise `false`.

#### _Example:_

```lua
if _A.ObjectIsFacing("player", "0x789ABC") then
    print("The player is facing the second object.")
else
    print("The player is not facing the second object.")
end
```

---

> ## ObjectIsBehind

-   This function checks if the first object is behind the second object.

#### Parameters

-   `object1`(string): The unitId or pointer identifier of the first object.
-   `object1`(string): The unitId or pointer identifier of the second object.

#### Returns

-   `isBehind`(bool): `true` if the first object is behind the second object, otherwise `false`.

#### _Example:_

```lua
if _A.ObjectIsBehind("player", "0x789ABC") then
    print("The player is behind the second object.")
else
    print("The player is not behind the second object.")
end
```

---

> ## TraceLine

-   This function traces a line between two points in the game world to determine if there is line of sight between those points. It uses the provided flags to control the behavior of the trace.

#### Parameters

-   `sX`(number): The X-coordinate of the starting point.
-   `sY`(number): The Y-coordinate of the starting point.
-   `sZ`(number): The Z-coordinate of the starting point.
-   `eX`(number): The X-coordinate of the ending point.
-   `eY`(number): The Y-coordinate of the ending point.
-   `eZ`(number): The Z-coordinate of the ending point.
-   `flags`(number): [`optional`] Flags to control the trace behavior. Default is 0x0.

#### Returns `los`, `cX`, `cY`, `cZ`

-   `los`(bool): `true` if there is line of sight between the points, `false` otherwise.
-   `cX`(number): The X-coordinate of the point of collision.
-   `cY`(number): The Y-coordinate of the point of collision.
-   `cZ`(number): The Z-coordinate of the point of collision.

!>**Note:** Flags allow you to control the specific types of objects and conditions that are considered when performing a line of sight check between two points in the game world. You can customize the behavior of the trace based on the nature of the obstacles you want to account for in the line of sight calculation.

|     Flag | Collision             | Note                                                                                                                          |
| -------: | :-------------------- | :---------------------------------------------------------------------------------------------------------------------------- |
|      0x0 | none                  | No special behavior or considerations.                                                                                        |
|      0x1 | doodad                | Take doodad collision into account during collision checks. Doodads are objects like props and decorations in the game world. |
|      0x2 | doodad render         | Doodad rendering during collision checks.                                                                                     |
|     0x10 | wmo                   | World Map Object (WMO) collision during collision checks. WMOs are complex structures like buildings.                         |
|     0x20 | wmo render            | WMO rendering during collision checks.                                                                                        |
|     0x40 | Wmo no cam            | Exclude WMO collision with the camera.                                                                                        |
|    0x100 | terrain               | Include terrain collision in checks.                                                                                          |
|   0x2000 | wmo doodad            | Ignore collision and interaction between WMOs and doodads.                                                                    |
|  0x10000 | liquid water walkable | Consider water as walkable during collision checks.                                                                           |
|  0x20000 | liquid all            | Include all liquid surfaces (water, lava, etc.) in collision checks.                                                          |
|  0x80000 | cull                  | Perform culling behavior to determine what should be rendered or not.                                                         |
| 0x100000 | entity                | Movable objects (objects that can be interacted with or moved) should be considered when performing the line of sight check.  |
| 0x200000 | entity render         | Consider entity rendering during collision checks.                                                                            |

#### _Example:_

```lua
local px, py, pz = _A.ObjectPosition("player")
local tx, ty, tz = _A.ObjectPosition("target")
local flags = bit.bor(0x100000, 0x10000, 0x100, 0x10, 0x1)

local los, cx, cy, cz = _A.TraceLine(px, py, pz, tx, ty, tz, flags)
if los then
  print("There is line of sight between the points.")
else
  print("There is an obstruction between the points.")
end
print("Collision point:", cx, cy, cz)
```

---

> ## MapId

-   This function retrieves the current map ID and additional information about the player's location on the map.

#### Returns `ContinentInstanceId`, `NorthSouth_tile`, `WestEast_tile`, `NorthSouth_subtile`, `WestEast_subtile`, `subZoneStr`

-   `ContinentInstanceId`(number): The ID of the continent instance.
-   `NorthSouth_tile`(number): The North-South tile coordinate.
-   `WestEast_tile`(number): The West-East tile coordinate.
-   `NorthSouth_subtile`(number): The North-South subtile coordinate.
-   `WestEast_subtile`(number): The West-East subtile coordinate.
-   `subZoneStr`(string): The subzone string (not localized).

#### _Example:_

```lua
local ContinentInstanceId, NorthSouth_tile, WestEast_tile, NorthSouth_subtile, WestEast_subtile, subZoneStr = _A.MapId()
print("Continent Instance ID:", ContinentInstanceId)
print("North-South Tile:", NorthSouth_tile)
print("West-East Tile:", WestEast_tile)
print("North-South Subtile:", NorthSouth_subtile)
print("West-East Subtile:", WestEast_subtile)
print("Subzone String:", subZoneStr)
```

!> **Note:** `subZoneStr` isn't localized.

---

> ## WorldToScreen

-   This function takes 3D world coordinates and converts them to screen coordinates. It returns the X and Y screen coordinates along with a flag indicating whether the coordinates are on the screen or not.

#### Parameters

-   `x`(number): The X-coordinate in the 3D world.
-   `y`(number): The Y-coordinate in the 3D world.
-   `z`(number): The Z-coordinate in the 3D world.

#### Returns

-   `sX`(number): The X-screen coordinate.
-   `sY`(number): The Y-screen coordinate.
-   `onScreen`(bool): `true` if the coordinates are on the screen, `false` otherwise.

#### _Example:_

```lua
local tx, ty, tz = _A.ObjectPosition("target")
local screenX, screenY, isOnScreen = _A.WorldToScreen(tx, ty, tz)
if isOnScreen then
    print("The target World coordinates are visible on the screen.")
else
    print("The target World coordinates are not visible on the screen.")
end
```

---

> ## ScreenToWorld

-   This function converts screen coordinates to 3D world coordinates. It returns (X, Y, Z) along with a flag indicating whether the coordinates collided with any object in the game world based on the hit flags.

#### Parameters

-   `x`(number): The screen X-coordinate.
-   `y`(number): The screen Y-coordinate.
-   `hitFlags`(number): [`optional`] Flags specifying the type of collision detection. Defaults to `0x100000 | 0x10000 | 0x100 | 0x10 | 0x1`.

#### Returns

-   `collision`(boolean): Indicates whether the screen coordinates collided with any object in the game world based on the hit flags.
-   `x`(number): The X-coordinate in the 3D world.
-   `y`(number): The Y-coordinate in the 3D world.
-   `z`(number): The Z-coordinate in the 3D world.

!> **Note:** Hit Flags allow you to control the specific types of objects and conditions.

|     Flag | Collision             | Note                                                                                                                          |
| -------: | :-------------------- | :---------------------------------------------------------------------------------------------------------------------------- |
|      0x0 | none                  | No special behavior or considerations.                                                                                        |
|      0x1 | doodad                | Take doodad collision into account during collision checks. Doodads are objects like props and decorations in the game world. |
|      0x2 | doodad render         | Doodad rendering during collision checks.                                                                                     |
|     0x10 | wmo                   | World Map Object (WMO) collision during collision checks. WMOs are complex structures like buildings.                         |
|     0x20 | wmo render            | WMO rendering during collision checks.                                                                                        |
|     0x40 | Wmo no cam            | Exclude WMO collision with the camera.                                                                                        |
|    0x100 | terrain               | Include terrain collision in checks.                                                                                          |
|   0x2000 | wmo doodad            | Ignore collision and interaction between WMOs and doodads.                                                                    |
|  0x10000 | liquid water walkable | Consider water as walkable during collision checks.                                                                           |
|  0x20000 | liquid all            | Include all liquid surfaces (water, lava, etc.) in collision checks.                                                          |
|  0x80000 | cull                  | Perform culling behavior to determine what should be rendered or not.                                                         |
| 0x100000 | entity                | Movable objects (objects that can be interacted with or moved) should be considered when performing the collision check.      |
| 0x200000 | entity render         | Consider entity rendering during collision checks.                                                                            |

#### _Example:_

```lua
do
    local collision, x, y, z
    _A.C_Timer.NewTicker(0.1, function()
        if _A.IsMouseButtonDown(2) then
            local mX, mY = _A.GetCursorPosition()
            collision, x, y, z = _A.ScreenToWorld(mX, mY)
        end
    end)

    local function draw()
        if x and y and z then
            _A.LibDraw:Circle(x, y, z)
        end
    end

    _A.Core:WhenInGame(function()
        _A.LibDraw:Sync(draw)
        _A.LibDraw:Enable(0.01)
    end)
end
```

---

> ## ClickPosition

-   This function simulates a mouse click at the specified 3D world position.

#### Parameters

-   `x`(number): The X-coordinate in the 3D world.
-   `y`(number): The Y-coordinate in the 3D world.
-   `z`(number): The Z-coordinate in the 3D world.

#### _Example:_

```lua
_A.ClickPosition(_A.ObjectPosition("target")) -- (1)!
```

1. Click at the `target` position.

---

> ## ClickToMove

-   This function initiates a click-to-move action, causing the player or controlled entity to move to the specified 3D world position.

#### Parameters

-   `x`(number): The X-coordinate in the 3D world.
-   `y`(number): The Y-coordinate in the 3D world.
-   `z`(number): The Z-coordinate in the 3D world.

#### _Example:_

```lua
-- Move to the "target" position.
_A.ClickToMove(_A.ObjectPosition("target"))
```

---

> ## IsForeground

-   This function determines whether the game window is currently in the foreground (active) state, meaning it has focus and user interaction is being accepted.

#### Returns

-   `isForeground`(bool): `true` if the game window is in the foreground, `false` otherwise.

#### _Example:_

```lua
local gameInForeground = _A.IsForeground()
if gameInForeground then
    print("The game window is in the foreground.")
else
    print("The game window is not in the foreground.")
end
```

---

> ## IsMinimized

-   This function determines whether the game window is currently minimized (Only exists on the Wotlk, Cata, Mop Apep version).

#### Returns

-   `IsMinimized`(bool): `true` if the game window is minimized, `false` otherwise.

#### _Example:_

```lua
local gameMinimized = _A.IsMinimized()
if gameMinimized then
    print("The game window is minimized.")
else
    print("The game window is not minimized.")
end
```

---

> ## GetKeyState

-   This function retrieves the state of a specific key, including whether it is currently pressed and whether it is toggled (such as caps lock).

#### Parameters

-   `Key`(number): The virtual key code of the keyboard key to check.

#### Returns

-   `isDown`(bool): `true` if the key is currently pressed, `false` otherwise.
-   `isToggled`(bool): `true` if the key is toggled (such as caps lock), `false` otherwise.

!>**Note:** Virtual key codes are used to identify keyboard keys in Windows applications. You can obtain these key codes from the official Microsoft documentation.
https://msdn.microsoft.com/en-us/library/windows/desktop/dd375731(v=vs.85).aspx

#### _Example:_

```lua
local pressed, toggled = _A.GetKeyState(65) -- (1)!
if pressed then
    print("The 'A' key is currently pressed.")
end
if toggled then
    print("The 'A' key is toggled (e.g., caps lock is on).")
end
```

1. The key code for the `A` key

---

> ## IsKeyDown

-   This function checks if a specific key is currently being held down (pressed) on the keyboard.

#### Parameters

-   `Key`(string): The name of the key to check, e.g., "A", "F1", "NUMPAD0", "SPACE".

#### Returns

-   `isKeyDown`(bool): `true` if the key is currently being held down, `false` otherwise.

#### _Example:_

```lua
if f.IsKeyDown("F") then
    print("The 'F' key is currently being held down.")
end
```

---

> ## SendKey

-   This function simulates sending a key press event to the application using the provided DirectInput Key Code.

#### Parameters

-   `Key`(number): The DirectInput Key Code corresponding to the key to be simulated.

!>**Note:** For a list of key codes
http://www.flint.jp/misc/?q=dik&lang=en

#### _Example:_

```lua
_A.SendKey(0x41) -- (1)!
```

1. Simulates pressing the 'A' key

---

> ## SetFacing

-   This function sets the facing angle of the player to the specified angle in radians.

#### Parameters

-   `angle`(number): The desired facing angle in radians.

#### _Example:_

```lua
_A.SetFacing(0) -- (1)!
_A.SetFacing(math.pi) -- (2)!
```

1. Sets the player's facing angle to 0 degrees(facing north).
2. Sets the player's facing angle to 180 degrees(facing south).

---

> ## FaceDirection

-   This function set the player's facing direction to a specific angle or towards a specified object.

#### Parameters

-   `angleOrObject`(number or string): The angle in radians or the object to face.
-   `update`(bool): [`optional`] Whether to immediately notify the server

#### _Example:_

```lua
_A.FaceDirection(0, true) -- (1)!
_A.FaceDirection("target", true) -- (2)!
```

1. Sets the player's facing angle to 0 degrees(facing north). And notify the server.
2. Face towards the object and notify the server.

---

> ## FaceTarget

-   This function face the player towards the currently targeted object

#### _Example:_

```lua
_A.FaceTarget() -- (1)!
```

1. Face the player towards the currently targeted object

---

> ## InvertFacing

-   This function invert the player's facing direction

#### _Example:_

```lua
_A.InvertFacing() -- (1)!
```

1. Invert the player's facing direction

---

> ## GetWoWDirectory

-   This function retrieves the directory path where the World of Warcraft game is installed on your system.

#### Returns

-   `dir`(string): The directory path of the World of Warcraft installation.

#### _Example:_

```lua
local wowDirectory = _A.GetWoWDirectory()
print(wowDirectory)
```

---

> ## GetDirectoryFiles

-   This function retrieves the names of the files in the specified directory path.

#### Parameters

-   `path`(string): The path to the directory.
-   `subfolders` (boolean) - If (true) include subfolders

#### Returns

-   `files`(table): A table containing the file names in the directory.

#### _Example:_

```lua
local wowDirectory = _A.GetWoWDirectory()
local files = _A.GetDirectoryFiles(wowDirectory, true)
for _, fileName in ipairs(files) do
    print(fileName)
end
```

---

> ## GetDirectoryFolders

-   This function retrieves the names of the folders in the specified directory path.

#### Parameters

-   `path`(string): The path to the directory.
-   `subfolders` (boolean) - If (true) include subfolders

#### Returns

-   `files`(table): A table containing the folder names in the directory.

#### _Example:_

```lua
local wowDirectory = _A.GetWoWDirectory()
local folders = _A.GetDirectoryFolders(wowDirectory, false)
for _, folderName in ipairs(folders) do
    print(folderName)
end
```

---

> ## GetApepDirectory

-   This function retrieves the directory path where the Apep executable is on your system.

#### Returns

-   `directory`(string): The directory path of the Apep executable.

#### _Example:_

```lua
local apepDirectory = _A.GetApepDirectory()
print(apepDirectory)
```

---

> ## ReadFile

-   This function reads and retrieves the contents of a text file specified by the given file path.

#### Parameters

-   `path`(string): The path to the text file.

#### Returns

-   `content`(string): The contents of the text file.

#### _Example:_

```lua
local wowDirectory = _A.GetWoWDirectory()
local contents = _A.ReadFile(wowDirectory.."\\example.txt")
print(contents)
```

---

> ## WriteFile

-   This function appends the specified text to a file or overwrites the file's content, based on the given options.

#### Parameters

-   `path`(string): The path to the text file.
-   `text`(string): The text to be written or appended.
-   `append`(bool): If `true`, the text will be appended; if `false`, the file content will be overwritten.

#### Returns

-   `success`(bool): `true` if the operation was successful, or an exception if an `error` occurred.

#### _Example:_

```lua
local wowDirectory = _A.GetWoWDirectory()
local success = _A.WriteFile(wowDirectory.."\\hello.txt", "Hello, World!", true)
if success then
    print("Text appended successfully.")
else
    print("Error occurred while writing to the file")
end
```

---

> ## LoadScript

-   This function loads and executes a Lua script located at the specified file path.

#### Parameters

-   `path`(string): The path to the Lua script file.

#### _Example:_

```lua
local wowDirectory = _A.GetWoWDirectory()
_A.LoadScript(wowDirectory.."\\scripts\\start.lua")
```

---

> ## BaseAddress

-   This function returns the base address of the World of Warcraft client, which can be used with other functions like ReadMemory to read specific offsets within the game's memory.

#### Returns

-   `baseAddr`(string): The base address of the World of Warcraft client in hexadecimal format.

#### _Example:_

```lua
local baseAddr = _A.BaseAddress()
print(baseAddr)
```

---

> ## ReadMemory

-   This function reads memory at the specified address and returns the requested type of data.

#### Parameters

-   `type`(string): The type of data to read (e.g., "bool", "byte", "string", "float", etc...).
-   `address`(string or number): The address in hexadecimal format (string) or numeric address.
-   `offset`(string or number): The offset of the address.

#### Returns

-   The requested type of data (e.g., boolean, number, string, etc.).

    | Type          | Return |
    | ------------- | ------ |
    | bool          | bool   |
    | byte          | number |
    | string        | string |
    | float         | number |
    | double        | number |
    | Int16/short   | string |
    | UInt16/ushort | string |
    | Int32/int     | string |
    | UInt32/uint   | string |
    | Int64/long    | string |
    | UInt64/ulong  | string |
    | Int128        | string |
    | GUID          | string |

#### _Example:_

```lua
local result = _A.ReadMemory("int", "0x12345678", 0x10)
```

---

> ## CancelPendingSpell

-   This function cancels the pending queued spell cast, if there is any.

!>**Note:** When you cast a spell in WoW, and you are in the middle of a combat action, the spell is queued up to be cast when that one is done, up to a maximum number of 1 spell. This feature was implemented to help players compensate for high latency. If you cancel your current spell, the queued spell is cancelled as well. This command lets you cancel the queued spell without cancelling your current spell.

#### _Example:_

```lua
_A.CancelPendingSpell()
```

---

> ## subgroup

-   This function retrieves the subgroup of a player within a raid.

#### Parameters

-   `unit`(string): The unit for which to determine the subgroup.

#### Returns `number`

-   The subgroup of the specified player in the raid, or -1 if not found.

#### _Example:_

```lua
local subgroup = _A.subgroup("player")
```

> ## UnitSpec

-   Returns the specialization ID of the specified unit.

#### Parameters

-   `unit`(string): The unit to query the specialization ID for.

#### Returns `number`

-   The specialization ID of the unit.

#### _Example:_

```lua
local specID = _A.UnitSpec("player")
```

!!! warning

    This method is available only in MoP (Mists of Pandaria).

---

> ## UnitIsMovingForward

-   This function checks whether the specified unit is currently moving forward.

#### Parameters

-   `unit`(string): The unit to check.

#### Returns `bool`

-   `true` if the unit is moving forward, `false` otherwise.

#### _Example:_

```lua
local isMovingForward = _A.UnitIsMovingForward("player")
if isMovingForward then
    print("The player is moving forward.")
else
    print("The player is not moving forward.")
end
```

---

> ## UnitIsMovingBackward

-   This function checks whether the specified unit is currently moving backward.

#### Parameters

-   `unit`(string): The unit to check.

#### Returns `bool`

-   `true` if the unit is moving backward, `false` otherwise.

#### _Example:_

```lua
local isMovingBackward = _A.UnitIsMovingBackward("player")
if isMovingBackward then
    print("The player is moving backward.")
else
    print("The player is not moving backward.")
end
```

---

> ## UnitIsStrafeLeft

-   This function checks whether the specified unit is currently strafing left.

#### Parameters

-   `unit`(string): The unit to check.

#### Returns `bool`

-   `true` if the unit is strafing left, `false` otherwise.

#### _Example:_

```lua
local isStrafingLeft = _A.UnitIsStrafeLeft("player")
if isStrafingLeft then
    print("The player is strafing left.")
else
    print("The player is not strafing left.")
end
```

---

> ## UnitIsStrafeRight

-   This function checks whether the specified unit is currently strafing right.

#### Parameters

-   `unit`(string): The unit to check.

#### Returns `bool`

-   `true` if the unit is strafing right, `false` otherwise.

#### _Example:_

```lua
local isStrafingRight = _A.UnitIsStrafeRight("player")
if isStrafingRight then
    print("The player is strafing right.")
else
    print("The player is not strafing right.")
end
```

---

> ## GetCurrentSpeed

-   This function retrieves the current speed of the specified unit.

#### Parameters

-   `unit`(string): The unit to check.

#### Returns `number`

-   The current speed of the unit.

#### _Example:_

```lua
local currentSpeed = _A.GetCurrentSpeed("player")
print("Current speed:", currentSpeed)
```

---

> ## GetWalkSpeed

-   This function retrieves the walking speed of the specified unit.

#### Parameters

-   `unit`(string): The unit to check.

#### Returns `number`

-   The walking speed of the unit.

#### _Example:_

```lua
local walkSpeed = _A.GetWalkSpeed("player")
print("Walking speed:", walkSpeed)
```

---

> ## GetRunSpeed

-   This function retrieves the running speed of the specified unit.

#### Parameters

-   `unit`(string): The unit to check.

#### Returns `number`

-   The running speed of the unit.

#### _Example:_

```lua
local runSpeed = _A.GetRunSpeed("player")
print("Running speed:", runSpeed)
```

---

> ## GetBackwardSpeed

-   This function retrieves the backward speed of the specified unit.

#### Parameters

-   `unit`(string): The unit to check.

#### Returns `number`

-   The backward speed of the unit.

#### _Example:_

```lua
local backwardSpeed = _A.GetBackwardSpeed("player")
print("Backward speed:", backwardSpeed)
```

---

> ## GetSwimimgSpeed

-   This function retrieves the swimming speed of the specified unit.

#### Parameters

-   `unit`(string): The unit to check.

#### Returns `number`

-   The swimming speed of the unit.

#### _Example:_

```lua
local swimmingSpeed = _A.GetSwimimgSpeed("player")
print("Swimming speed:", swimmingSpeed)
```

---

> ## CalculatePath

-   This API computes a path from the player coordinates to another point in the game world.

#### Parameters

-   `x`(number): The x-coordinate of the destination point.
-   `y`(number): The y-coordinate of the destination point.
-   `z`(number): The z-coordinate of the destination point.
-   `straightPath`(boolean, optional): Determines whether to calculate a straight path (`true`) or not (`false`). Default is `false`.

#### Returns `table`

-   A table containing the calculated path points, or an empty table if no path was found.

#### _Example:_

```lua
local path = _A.CalculatePath(1129.7, -4223.4, 22.1, false)

for i, point in ipairs(path) do
    local x, y, z = unpack(point)
    print(string.format("Point %d: (%f, %f, %f)", i, x, y, z))
end
```

!!! info

    In order for this API to work, it is necessary to have the `mmap` files on disk.

    They need to be downloaded from this [link](https://discord.com/channels/551772363465818112/1092897181511463063/1220586784145281064) and extracted into a folder. Then, it is necessary to edit the `Apep.ini` file and add the key mmaps:
    `mmaps=C:\mmaps\545`

    In this example, we are indicating Apep that the mmap files are in the folder `C:\mmaps\545`, referring to the [Mists of Pandaria](https://wowpedia.fandom.com/wiki/World_of_Warcraft:_Mists_of_Pandaria) expansion.

---

> ## GetMissiles

-   This function retrieves information about active missiles in the game world.

#### Returns `table`

-   A table containing information about active missiles, or an empty table if there are no missiles.

The table has the following structure:

```lua
{
    [1] = {
          spellid,       -- (1)!
          spellvisualid, -- (2)!
          x,             -- (3)!
          y,             -- (4)!
          z,             -- (5)!
          caster,        -- (6)!
          fx,            -- (7)!
          fy,            -- (8)!
          fz,            -- (9)!
          target,        -- (10)!
          ix,            -- (11)!
          iy,            -- (12)!
          iz,            -- (13)!
     },
     [n] = {
          -- (14)!
     },
}
```

1. ID of the spell associated with the missile
2. ID of the spell's visual missile effect (NOTE: Non-existent in versions prior Legion.)
3. X-coordinate of the missile's current position
4. Y-coordinate of the missile's current position
5. Z-coordinate of the missile's current position
6. GUID of the caster of the missile
7. X-coordinate of the fired position
8. Y-coordinate of the fired position
9. Z-coordinate of the fired position
10. GUID of the missile's target
11. X-coordinate of the impact position
12. Y-coordinate of the impact position
13. Z-coordinate of the impact position
14. Information about the next missile, if available

#### _Example:_

```lua
local missiles = _A.GetMissiles()
for _, missile in ipairs(missiles) do
     local spellid, x, y, z, caster, fx, fy, fz, target, ix, iy, iz = unpack(missile) -- (1)
     print(spellid, x, y, z, caster, fx, fy, fz, target, ix, iy, iz)
end
```

!!! warning

    This example is for prior Legion

    If you are using Legion or later, you can use:
    ```lua
    local spellid, spellvisualid, x, y, z, caster, fx, fy, fz, target, ix, iy, iz = unpack(missile)
    ```

---

> ## GetItemIcon

-   This function retrieves the icon of the specified item.

#### Parameters

-   `idOrName` (string or number): The ID or name of the item to retrieve the icon for.
-   `width` (number): The desired width of the icon.
-   `height` (number): The desired height of the icon.

#### Returns `string`

-   The icon of the item.

#### _Example:_

```lua
_A.Core:GetItemIcon(idOrName, width, height)
```

---

> ## SetSpeed

-   This function sets the speed of the player to the specified value.

#### Parameters

-   `speed`(number): The desired speed value.

#### _Example:_

```lua
_A.SetSpeed(20)
```

---

## ResetSpeed

-   This function resets the speed of the player to the default value.

#### _Example:_

```lua
_A.ResetSpeed()
```

---

> ## HasAura

-   This function checks if the specified unit has an aura with the specified aura ID.

#### Parameters

-   `unit`(string): The unit to check for the aura.
-   `AuraId`(number): The aura ID to check if the unit has an aura with.

#### Returns `bool`

-   `true` if the unit has an aura with the specified aura ID, otherwise `false`.

#### _Example:_

```lua
local hasAura = _A.HasAura("player", 12345)
```

---

> ## IsLootable

-   This function checks if the specified unit is lootable.

#### Parameters

-   `unit`(string): The unit to check for lootability.

#### Returns `bool`

-   `true` if the unit is lootable, otherwise `false`.

#### _Example:_

```lua
local isLootable = _A.IsLootable("player")
```

---

> ## IsTaggedByOther

-   This function checks if the specified unit is tagged by other players.

#### Parameters

-   `unit`(string): The unit to check for tagging.

#### Returns `bool`

-   `true` if the unit is tagged by other players, otherwise `false`.

#### _Example:_

```lua
local isTaggedByOther = _A.IsTaggedByOther("player")
```

---

> ## IsTaggedByMe

-   This function checks if the specified unit is tagged by the player.

#### Parameters

-   `unit`(string): The unit to check for tagging.

#### Returns `bool`

-   `true` if the unit is tagged by the player, otherwise `false`.

#### _Example:_

```lua
local isTaggedByMe = _A.IsTaggedByMe("player")
```

---

> ## IsDead

-   This function checks if the specified unit is dead.

#### Parameters

-   `unit`(string): The unit to check for death.

#### Returns `bool`

-   `true` if the unit is dead, otherwise `false`.

#### _Example:_

```lua
local isDead = _A.IsDead("player")
```

---

> ## IsTappedByAllThreatList

-   This function checks if the specified unit is tapped by all threat list.

#### Parameters

-   `unit`(string): The unit to check for tapping.

#### Returns `bool`

-   `true` if the unit is tapped by all threat list, otherwise `false`.

#### _Example:_

```lua
local isTappedByAllThreatList = _A.IsTappedByAllThreatList("player")
```

---

> ## IsSitting

-   This function checks if the specified unit is sitting.

#### Parameters

-   `unit`(string): The unit to check for sitting.

#### Returns `bool`

-   `true` if the unit is sitting, otherwise `false`.

#### _Example:_

```lua
local isSitting = _A.IsSitting("player")
```

---

> ## IsInfluenced

-   This function checks if the specified unit is influenced.

#### Parameters

-   `unit`(string): The unit to check for influence.

#### Returns `bool`

-   `true` if the unit is influenced, otherwise `false`.

#### _Example:_

```lua
local isInfluenced = _A.IsInfluenced("player")
```

---

> ## IsPlayerControlled

-   This function checks if the specified unit is controlled by the player.

#### Parameters

-   `unit`(string): The unit to check for player control.

#### Returns `bool`

-   `true` if the unit is controlled by the player, otherwise `false`.

#### _Example:_

```lua
local isPlayerControlled = _A.IsPlayerControlled("player")
```

---

> ## IsTotem

-   This function checks if the specified unit is a totem.

#### Parameters

-   `unit`(string): The unit to check for totem status.

#### Returns `bool`

-   `true` if the unit is a totem, otherwise `false`.

#### _Example:_

```lua
local isTotem = _A.IsTotem("player")
```

---

> ## IsPreparation

-   This function checks if the specified unit is preparing.

#### Parameters

-   `unit`(string): The unit to check for preparation.

#### Returns `bool`

-   `true` if the unit is preparing, otherwise `false`.

#### _Example:_

```lua
local isPreparation = _A.IsPreparation("player")
```

---

> ## IsNotAttackable

-   This function checks if the specified unit is not attackable.

#### Parameters

-   `unit`(string): The unit to check for attackability.

#### Returns `bool`

-   `true` if the unit is not attackable, otherwise `false`.

#### _Example:_

```lua
local isNotAttackable = _A.IsNotAttackable("player")
```

---

> ## IsLooting

-   This function checks if the specified unit is looting.

#### Parameters

-   `unit`(string): The unit to check for looting.

#### Returns `bool`

-   `true` if the unit is looting, otherwise `false`.

#### _Example:_

```lua
local isLooting = _A.IsLooting("player")
```

---

> ## IsPetInCombat

-   This function checks if the specified unit's pet is in combat.

#### Parameters

-   `unit`(string): The unit to check for pet combat.

#### Returns `bool`

-   `true` if the unit's pet is in combat, otherwise `false`.

#### _Example:_

```lua
local isPetInCombat = _A.IsPetInCombat("player")
```

---

> ## IsPvPFlagged

-   This function checks if the specified unit is flagged for PvP.

#### Parameters

-   `unit`(string): The unit to check for PvP flag.

#### Returns `bool`

-   `true` if the unit is flagged for PvP, otherwise `false`.

#### _Example:_

```lua
local isPvPFlagged = _A.IsPvPFlagged("player")
```

---

> ## IsChoked

-   This function checks if the specified unit is choked.

#### Parameters

-   `unit`(string): The unit to check for choke.

#### Returns `bool`

-   `true` if the unit is choked, otherwise `false`.

#### _Example:_

```lua
local isChoked = _A.IsChoked("player")
```

---

> ## IsPacified

-   This function checks if the specified unit is pacified.

#### Parameters

-   `unit`(string): The unit to check for pacification.

#### Returns `bool`

-   `true` if the unit is pacified, otherwise `false`.

#### _Example:_

```lua
local isPacified = _A.IsPacified("player")
```

---

> ## IsStunned

-   This function checks if the specified unit is stunned.

#### Parameters

-   `unit`(string): The unit to check for stun.

#### Returns `bool`

-   `true` if the unit is stunned, otherwise `false`.

#### _Example:_

```lua
local isStunned = _A.IsStunned("player")
```

---

> ## IsInCombat

-   This function checks if the specified unit is in combat.

#### Parameters

-   `unit`(string): The unit to check for combat.

#### Returns `bool`

-   `true` if the unit is in combat, otherwise `false`.

#### _Example:_

```lua
local isInCombat = _A.IsInCombat("player")
```

---

> ## IsTaxiFlight

-   This function checks if the specified unit is on a taxi flight.

#### Parameters

-   `unit`(string): The unit to check for taxi flight.

#### Returns `bool`

-   `true` if the unit is on a taxi flight, otherwise `false`.

#### _Example:_

```lua
local isTaxiFlight = _A.IsTaxiFlight("player")
```

---

> ## IsDisarmed

-   This function checks if the specified unit is disarmed.

#### Parameters

-   `unit`(string): The unit to check for disarm.

#### Returns `bool`

-   `true` if the unit is disarmed, otherwise `false`.

#### _Example:_

```lua
local isDisarmed = _A.IsDisarmed("player")
```

---

> ## IsConfused

-   This function checks if the specified unit is confused.

#### Parameters

-   `unit`(string): The unit to check for confusion.

#### Returns `bool`

-   `true` if the unit is confused, otherwise `false`.

#### _Example:_

```lua
local isConfused = _A.IsConfused("player")
```

---

> ## IsFleeing

-   This function checks if the specified unit is fleeing.

#### Parameters

-   `unit`(string): The unit to check for fleeing.

#### Returns `bool`

-   `true` if the unit is fleeing, otherwise `false`.

#### _Example:_

```lua
local isFleeing = _A.IsFleeing("player")
```

---

> ## IsPossessed

-   This function checks if the specified unit is possessed.

#### Parameters

-   `unit`(string): The unit to check for possession.

#### Returns `bool`

-   `true` if the unit is possessed, otherwise `false`.

#### _Example:_

```lua
local isPossessed = _A.IsPossessed("player")
```

---

> ## IsNotSelectable

-   This function checks if the specified unit is not selectable.

#### Parameters

-   `unit`(string): The unit to check for selectability.

#### Returns `bool`

-   `true` if the unit is not selectable, otherwise `false`.

#### _Example:_

```lua
local isNotSelectable = _A.IsNotSelectable("player")
```

---

> ## IsSkinnable

-   This function checks if the specified unit is skinnable.

#### Parameters

-   `unit`(string): The unit to check for skinnable status.

#### Returns `bool`

-   `true` if the unit is skinnable, otherwise `false`.

#### _Example:_

```lua
local isSkinnable = _A.IsSkinnable("player")
```

---

> ## IsInMount

-   This function checks if the specified unit is in the mount.

#### Parameters

-   `unit`(string): The unit to check for mount status.

#### Returns `bool`

-   `true` if the unit is in the mount, otherwise `false`.

#### _Example:_

```lua
local isInMount = _A.IsInMount("player")
```

---

> ## IsDazed

-   This function checks if the specified unit is dazed.

#### Parameters

-   `unit`(string): The unit to check for daze.

#### Returns `bool`

-   `true` if the unit is dazed, otherwise `false`.

#### _Example:_

```lua
local isDazed = _A.IsDazed("player")
```

---

> ## IsSheathed

-   This function checks if the specified unit is sheathed.

#### Parameters

-   `unit`(string): The unit to check for sheath.

#### Returns `bool`

-   `true` if the unit is sheathed, otherwise `false`.

#### _Example:_

```lua
local isSheathed = _A.IsSheathed("player")
```

---

> ## IsFeignDeath

-   This function checks if the specified unit is feigning death.

#### Parameters

-   `unit`(string): The unit to check for feign death.

#### Returns `bool`

-   `true` if the unit is feigning death, otherwise `false`.

#### _Example:_

```lua
local isFeignDeath = _A.IsFeignDeath("player")
```

---

<!-- New api _A.http:request
- Send an HTTP or HTTPS request.
Method (string)   - GET or POST
URL (string)      - The URL to send to
Data (string)     - The Data to send. (POST, can be JSON string or QUERY string) (GET, only QUERY string)
Callback (body, code, req, res, err) - The function to be called with the response if the request succeeds.
Headers (string)  - Headers that should be added to the request. Split with \r\n.

function _A.http:request ( Method, URL, Data, Callback, Headers )

NOTE: This function doesn't return anything. It's asynchronous. Use the Callback for that.

@usage
local headers = [[
Authentication: c2VjcmV0
X-Secret-Auth-Token: foo
User-Agent: LUA-Script
]]

_A.http:request("POST", "https://httpbin.org/post", "name=John Doe&occupation=gardener",
   function(body, code, req, res, err)
      _G.RunScript(body)   -- contents that were downloaded
      print(code) -- string - HTTP Response Code
      print(req)  -- string - Full HTTP Request
      print(res)  -- string - Full HTTP Response
      print(err)  -- string - Some internal Socket Error
   end,
   headers
)

Example of how to send a message to discord through Apep.
local name = _G.UnitName("player")
local message = "Name: "..name.."\nServer: ".._G.GetRealmName()
local data = {
    embeds = {
        title = "[webhook example]",
        description = message,
        color =  0xFFFF00
    }
}
local json = _A.json:encode(data):gsub(':{', ':[{'):gsub('}}', '}]}')
local url = "https://discord.com/api/webhooks/2163585181114123568/audZXgLO88RBDOUrUiWLXqu9AHya_ZAQD0HT2cQaf0Ijs-aON2peZ6j-Ol6mURqIeC3EC"

_A.http:request("POST", url, json, function() end) -->

> ## http.request

-   This function sends an HTTP or HTTPS request.

#### Parameters

-   `Method`(string): The HTTP method to use (e.g., "GET" or "POST").
-   `URL`(string): The URL to send the request to.
-   `Data`(string): The data to send in the request (e.g., a JSON string or a query string).
-   `Callback`(function): The function to call when the request is complete.
-   `Headers`(string): Additional headers to include in the request.

#### _Example:_

=== "Minimal Example"

    ```lua
    local headers = [[
    Authentication: c2VjcmV0
    X-Secret-Auth-Token: foo
    User-Agent: LUA-Script
    ]]

    _A.http:request("POST", "https://httpbin.org/post", "name=John Doe&occupation=gardener",
        function(body, code, req, res, err)
            _G.RunScript(body) -- (1)!
            print(code) -- (2)!
            print(req) -- (3)!
            print(res) -- (4)!
            print(err) -- (5)!
        end,
        headers
    )
    ```

    1. The contents of the response are passed to the callback function.
    2. The HTTP response code.
    3. The full HTTP request.
    4. The full HTTP response.
    5. An error message if the request fails.

=== "Real world Example"

    Example of how to send a message to discord through Apep:

    ```lua
    local name = _G.UnitName("player")
    local message = "Name: "..name.."\nServer: ".._G.GetRealmName()
    local data = {
        embeds = {
            title = "[webhook example]",
            description = message,
            color =  0xFFFF00
        }
    }
    local json = _A.json:encode(data):gsub(':{', ':[{'):gsub('}}', '}]}')
    local url = "https://discord.com/api/webhooks/2163585181114123568/audZXgLO88RBDOUrUiWLXqu9AHya_ZAQD0HT2cQaf0Ijs-aON2peZ6j-Ol6mURqIeC3EC"

    _A.http:request("POST", url, json, function() end)
    ```

---

> ## json.encode

-   This function encodes an arbitrary Lua object / variable.

#### Parameters

-   `obj`(any): The Lua value (table/string/boolean/number/nil/json.null/json.empty) to be JSON-encoded.

#### _Example:_

```lua
local table = {
    ["test 1"] = {data=0, data1="xxx"},
    ["test 2"] = {data=234, data1="sdfee"}
}
local json = _A.json:encode(table)
print(json) -- (1)!
```

1. Returns `{"test 1":{"data":0,"data1":"xxx"},"test 2":{"data":234,"data1":"sdfee"}}`

---

> ## json.decode

-   This function decodes a JSON string and returns the decoded value as a Lua data structure / value.

#### Parameters

-   `string`(string): The string to scan (or "loader function" for getting next substring).
-   `position`(number, optional): The position inside param `string` to start scan, default = 1.

#### _Example:_

```lua
local LuaObject = _A.json:decode('{"test 1":{"data":0,"data1":"xxx"},"test 2":{"data":234,"data1":"sdfee"}}')
print(LuaObject) -- (1)!
```

1. table: 000005D740CC4AF1
