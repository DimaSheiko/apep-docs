# FAKEUNITS

A fakeunit is a pointer to an ObjectManager object. In World of Warcraft: Wrath of the Lich King (wotlk), we utilize a [GUID (globally unique identifier)](https://wowpedia.fandom.com/wiki/GUID) because in wotlk, a GUID is represented as a hex number. However, in expansions like Legion, a GUID resembles a format such as `Creature-0-1465-0-2105-448-000043F59F`. Instead of using GUIDs directly, we use the pointer (key) of the object as the identifier, which allows us to perform actions directly on these pointers.

## What we can do with fakeunits

One of the notable capabilities while using fakeunits is the ability to cast spells. For instance, you could use a format similar to:

=== "DSL"

    ```lua
    {"%target", "!is(target)", "nearEnemyCb"}
    ```

=== "Lua Code"

    ```lua
    _A.DSL:Get("%target", "!is(target)", "nearEnemyCb")
    ```

=== "Lua Mode"

    ```lua
    PLAYER:CastSpell("%target", "!is(target)", "nearEnemyCb")
    ```

Here, the unit `nearEnemyCb` is used to target the near enemy in combat. This signifies that the fakeunit identifies a target object, and the specified action (target the unit, applying a buff, cast a spell etc.) can be executed on it. This flexibility with fakeunits means you can perform various custom actions programmatically on any target represented by these pointers.

---

> ## enemies

-   Represents all the enemies.

---

> ## combatEnemies | cbEnemies

-   Represents the enemies that are in combat.

---

> ## friends

-   Represents all friendly units, including NPCs and party/raid members.

---

> ## roster

-   Represents all the players in your party or raid.

---

> ## dead

-   Represents all the dead units.

---

> ## lowest

-   Represents the player in your party or raid with the lowest health.

---

> ## lowestpredicted | lowestp

-   Represents the player in your party or raid with the lowest predicted health.

---

> ## lowestbuff | lbuff

-   Represents the player in your party or raid with the lowest health that has a certain buff.

---

> ## lowestnotbuff | lnbuff

-   Represents the player in your party or raid with the lowest health that does not have a certain buff.

---

> ## lowestdebuff | ldebuff

-   Represents the player in your party or raid with the lowest health that has a certain debuff.

---

> ## lowestnotdebuff | lndebuff

-   Represents the player in your party or raid with the lowest health that does not have a certain debuff.

---

> ## tank

-   Represents the tank in your party or raid.

---

> ## healer

-   Represents the healer in your party or raid.

---

> ## damager

-   Represents the damager in your party or raid.

---

> ## lowestenemy | loweste | le

-   Represents the lowest health enemy.

---

> ## enemybuff | ebuff

-   Represents the enemy that have a certain buff.

---

> ## enemynbuff | enbuff

-   Represents the enemy that do not have a certain buff.

---

> ## enemydebuff | edebuff

-   Represents the enemy that have a certain debuff.

---

> ## enemyndebuff | endebuff

-   Represents the enemy that do not have a certain debuff.

---

> ## adds

-   Represents all the adds in the encounter.

---

> ## boss

-   Represents the boss in the encounter.
