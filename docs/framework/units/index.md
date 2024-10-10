---
title: Units/FakeUnits
nextjs:
  metadata:
    title: Apep | Units FakeUnits
    description: Units/FakeUnits
---

## Units

- A unit is an object that has a name and a guid. The name can be `player`, `pet`, `target`, `mouseover`, `pettarget`, `focus`, `party1`, etc.. You can read more about units in the [wowwiki](https://wowpedia.fandom.com/wiki/UnitId).

### arenaN

- Opposing arena member with index N (1,2,3,4 or 5).

### bossN

- The active bosses of the current encounter if available N (1,2,3...,8).

### focus

- The current player's focus target as selected by the /focus command.

### mouseover

- The unit which the mouse is currently (or was most recently) hovering over.

### none

- A valid unit token that always refers to no unit. UnitName will return "Unknown, nil" for this UnitID. Use to force a macro to not auto self-cast (/cast [target=none] Healing Wave).

### partyN

- The Nth party member excluding the player (1,2,3 or 4).

### partypetN

- The pet of the Nth party member (N is 1,2,3, or 4).

### pet

- The current player's pet.

### player

- The current player.

### raidN

- The raid member with raidIndex N (1,2,3,...,40).

### raidpetN

- The pet of the raid member with raidIndex N (1,2,3,...,40)

### target

- The currently targeted unit. May be overridden in macros by unit specified as a value of respective Secure Button attribute.

### vehicle

- The current player's vehicle.

### nameplateN

- The Nth nameplate (1,2,3,...,40). Cannot be targeted by spells or commands such as /target nameplate1 or /cast [target=nameplate1] Healing Wave.

### spectated<T><N>

- The Nth spectated unit (1,2,3,...,15) for either Team "a" or "b", such as "spectatedb2" for the second unit on team B. Only present in commentator mode.

### spectatedpet<T><N>

- The pet of the Nth spectated unit (1,2,3,...,15) for either Team "a" or "b", such as "spectatedpetb2" for the second units' pet on team B. Only present in commentator mode.

---

## Fakeunits

- A fakeunit is a pointer to an ObjectManager object. In wotlk we use a guid because a guid in wotlk is a hex number but in legion a guid is different its somethink like `Creature-0-1465-0-2105-448-000043F59F` then we use the pointer(key) of the object and we can cast spells on pointers.

---

### enemies

- Represents all the enemies.

---

### combatEnemies | cbEnemies

- Represents the enemies that are in combat.

---

### friends

- Represents all friendly units, including NPCs and party/raid members.

---

### roster

- Represents all the players in your party or raid.

---

### dead

- Represents all the dead units.

---

### lowest

- Represents the player in your party or raid with the lowest health.

---

### lowestpredicted | lowestp

- Represents the player in your party or raid with the lowest predicted health.

---

### lowestbuff | lbuff

- Represents the player in your party or raid with the lowest health that has a certain buff.

---

### lowestnotbuff | lnbuff

- Represents the player in your party or raid with the lowest health that does not have a certain buff.

---

### lowestdebuff | ldebuff

- Represents the player in your party or raid with the lowest health that has a certain debuff.

---

### lowestnotdebuff | lndebuff

- Represents the player in your party or raid with the lowest health that does not have a certain debuff.

---

### tank

- Represents the tank in your party or raid.

---

### healer

- Represents the healer in your party or raid.

---

### damager

- Represents the damager in your party or raid.

---

### lowestenemy | loweste | le

- Represents the lowest health enemy.

---

### enemybuff | ebuff

- Represents the enemy that have a certain buff.

---

### enemynbuff | enbuff

- Represents the enemy that do not have a certain buff.

---

### enemydebuff | edebuff

- Represents the enemy that have a certain debuff.

---

### enemyndebuff | endebuff

- Represents the enemy that do not have a certain debuff.

---

### adds

- Represents all the adds in the encounter.

---

### boss

- Represents the boss in the encounter.
