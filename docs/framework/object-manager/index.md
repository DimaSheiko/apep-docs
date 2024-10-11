---
title: Object Manager
icon: material/book-open-page-variant-outline
---

The Object Manager is a table that contains all the players, units, and objects currently in the game world that are visible to the player.
You can access the Object Manager using the `_A.OM` global variable.
There are several sub-tables within the Object Manager that contain units of a specific type.

```lua
_A.OM = {
    All = {},
    Enemy = {},
    EnemyCombat = {},
    Friendly = {},
    Roster = {},
    Dead = {},
    Critters = {},
    Object = {},
    GameObject = {},
    DynamicObject = {},
}
```

---

## Object Manager Tables

The Object Manager contains the following tables:

---

### All

-   Contains all the units currently in the game world that are visible to the player.

---

### Enemy

-   Contains all the enemy units currently in the game world that are visible to the player.

---

### EnemyCombat

-   Contains all the enemy units currently in combat that are visible to the player.

---

### Friendly

-   Contains all the friendly units currently in the game world that are visible to the player.

---

### Roster

-   Contains all the members of the player's group.

---

### Dead

-   Contains all the dead units currently in the game world that are visible to the player.

---

### Critters

-   Contains all the critters currently in the game world that are visible to the player.

---

### Object

-   Contains all the game objects currently in the game world that are visible to the player.

---

### GameObject

-   Contains all the game objects currently in the game world that are visible to the player.

---

### DynamicObject

-   Contains all the dynamic objects currently in the game world that are visible to the player.

---

And for example if you want to iterate the `Roster` table:

```lua
local roster = _A.OM:Get('Roster')

for _,Obj in pairs(roster) do
    print( Obj.key )
    print( Obj.guid )
    print( Obj.name )
    print( Obj:distance() )
    print( Obj:healthRaw() )
    print( Obj:healthMax() )
    print( Obj:health() )
end
```

---

## Object Manager Methods

The Object Manager contains the following methods:

### **Get**

-   Returns a table of units that match the provided condition. For example if you do

```lua
local playerObject = _A.OM:Get("Roster")[UnitGUID("player")]
```

or

```lua
local playerObject = _A.OM["Roster"][UnitGUID("player")]
```

The table containing the `player` object is assigned to the playerObject variable that way you dont need to iterate to get the player object
