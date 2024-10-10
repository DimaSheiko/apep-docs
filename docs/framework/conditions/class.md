# CLASS
---


> ## power.regen

- This condition calculates and returns the power regeneration rate of the player.

#### Returns `NUMBER`
- The power regeneration rate of the player.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "power.regen >= 5"},

-- in Lua code
_A.DSL:Get("power.regen")() >= 5

-- Lua Mode
PLAYER:PowerRegen() >= 5
```

***


> ## energy

- This condition returns the current energy amount of the player.

#### Returns `NUMBER`
- The current energy amount of the player.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "energy >= 60"},

-- in Lua code
_A.DSL:Get("energy")() >= 60

-- Lua Mode
PLAYER:Energy() >= 60
```

***


> ## energy.max
  *`energy.max || energyMax`*

- This condition returns the maximum energy amount of the player.

#### Returns `NUMBER`
- The maximum energy amount of the player.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "energy.max >= 100"},

-- in Lua code
_A.DSL:Get("energy.max")() >= 100

-- Lua Mode
PLAYER:EnergyMax() >= 60
```

***


> ## energy.diff
  *`energy.diff || energy.deficit || energydiff`*

- This condition returns the difference between the maximum energy and the current energy of the player.

#### Returns `NUMBER`
- The energy deficit(difference) of the player.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "energy.diff >= 20"},

-- in Lua code
_A.DSL:Get("energy.diff")() >= 20

-- Lua Mode
PLAYER:EnergyDiff() >= 20
```

***


> ## mana.raw

- This condition returns the current player mana.

#### Returns `NUMBER`
- The player mana raw.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "player.mana.raw >= 400"},

-- in Lua code
_A.DSL:Get("mana.raw")("player") >= 400

-- Lua Mode
PLAYER:ManaRaw() >= 400
```

***


> ## mana

- This condition returns the player mana percentage.

#### Returns `NUMBER`
- The player percentage of mana.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "mana >= 80"},

-- in Lua code
_A.DSL:Get("mana")() >= 80

-- Lua Mode
PLAYER:Mana() >= 80
```

***


> ## insanity

- This condition retrieves the current amount of insanity power of the player.

#### Returns `NUMBER`
- The current amount of insanity power of the player.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "insanity >= 80"},

-- in Lua code
_A.DSL:Get("insanity")() >= 80

-- Lua Mode
PLAYER:Insanity() >= 80
```

***


> ## ispet

- This condition checks if the specified unit is a pet.

#### Parameters
- `UNIT`: The unit to check

#### Returns `BOOL`
- `true` if the unit is a pet, `false` otherwise.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.ispet", UNIT},

-- in Lua code
_A.DSL:Get("ispet")("UNIT")

-- Lua Mode
UNIT:Ispet()
```

***


> ## stagger

- This condition returns the amount of staggered damage on the specified unit.

#### Parameters
- `UNIT`: The unit to check (e.g., "player", "target").

#### Returns `NUMBER`
- The amount of staggered damage on the unit.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.stagger >= 500", UNIT},

-- in Lua code
_A.DSL:Get("stagger")("UNIT") >= 500

-- Lua Mode
UNIT:Stagger() >= 500
```

***


> ## focus

- This condition calculates the focus resource of the player or pet, based on the provided target.
If the target is "pet," the function returns the focus of the player's pet; otherwise, it returns the focus of the player.

#### Parameters
- `UNIT`: The target unit ("pet" or "player") to determine whose focus resource to check.

#### Returns `NUMBER`
- The focus resource of the specified target unit, or the player's focus if no target is provided.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "UNIT.focus >= 40", UNIT},

-- in Lua code
_A.DSL:Get("focus")("UNIT") >= 40

-- Lua Mode
UNIT:Focus() >= 40
```

***


> ## focus.max
  *`focus.max || focusMax`*

- This condition retrieve the maximum focus resource of the player.

#### Returns `NUMBER`
- The maximum focus resource of the player.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "focus.max > 100"},

-- in Lua code
_A.DSL:Get("focus.max")() > 100

-- Lua Mode
PLAYER:FocusMax() > 100
```

***


> ## runic.power
  *`runic.power || runicpower`*

- This condition calculates the runic power resource of the player.

#### Returns `NUMBER`
- The runic power resource of the player.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "runic.power > 20"},

-- in Lua code
_A.DSL:Get("runic.power")() > 20

-- Lua Mode
PLAYER:RunicPower() > 100
```

***


> ## runes

- This condition calculates the number of available rune resources for the player.

#### Returns `NUMBER`
- The number of available rune resources for the player.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "runes > 4"},

-- in Lua code
_A.DSL:Get("runes")() > 20

-- Lua Mode
PLAYER:Runes() > 100
```

***


> ## maelstrom

- This condition returns the amount of Maelstrom power on the player.

#### Returns `NUMBER`
- The amount of Maelstrom power on the player.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "maelstrom > 20"},

-- in Lua code
_A.DSL:Get("maelstrom")() > 20

-- Lua Mode
PLAYER:Maelstrom() > 20
```

***


> ## totem

- This condition checks if a specific totem is currently active for the player.

#### Parameters
- `totem`(string): The spell ID or name of the totem to check for.

#### Returns `BOOL`
- `true` if the specified totem is currently active, `false` otherwise.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "totem(Flametongue Totem IV)"},

-- in Lua code
_A.DSL:Get("totem")(_ , "Flametongue Totem IV")

-- Lua Mode
PLAYER:Totem("Flametongue Totem IV")
```

***


> ## totem.duration

- This condition calculates the remaining duration (in seconds) of a specific totem.

#### Parameters
- `totem`(string): The spell ID or name of the totem to check the duration for.

#### Returns `NUMBER`
- The remaining duration of the specified totem in seconds, or 0 if the totem is not found.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "totem(Mana Spring Totem IV).duration < 0.5"},

-- in Lua code
_A.DSL:Get("totem.duration")(_ , "Mana Spring Totem IV") < 0.5

-- Lua Mode
PLAYER:TotemDuration("Mana Spring Totem IV") < 0.5
```

***


> ## totem.time

- This condition returns the maximum duration (in seconds) of a specific totem.

#### Parameters
- `totem`(string): The spell ID or name of the totem to retrieve the maximum duration for.

#### Returns `NUMBER`
- The maximum duration of the specified totem in seconds, or 0 if the totem is not found.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "totem(Mana Spring Totem IV).time == 60"},

-- in Lua code
_A.DSL:Get("totem.time")(_ , "Mana Spring Totem IV") == 60

-- Lua Mode
PLAYER:TotemTime("Mana Spring Totem IV") == 60
```

***


> ## soulshards

- This condition returns the current number of Soul Shards a player has.

#### Returns `NUMBER`
- The current number of Soul Shards.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "soulshards >= 3"},

-- in Lua code
_A.DSL:Get("soulshards")() >= 3

-- Lua Mode
PLAYER:Soulshards() >= 3
```

***


> ## chi

- This condition returns the current Chi a player has.

#### Returns `NUMBER`
- The current number of chi.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "chi >= 3"},

-- in Lua code
_A.DSL:Get("chi")() >= 3

-- Lua Mode
PLAYER:Chi() >= 3
```

***


> ## chi.max
  *`chi.max || chiMax`*

- This condition returns the maximum number of Chi a player can have.

#### Returns `NUMBER`
- The maximum number of Chi a player can have.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "chi.max = 5"},

-- in Lua code
_A.DSL:Get("chi.max")() = 5

-- Lua Mode
PLAYER:ChiMax() = 5
```

***


> ## chi.diff
  *`chi.diff || chi.deficit || chidiff`*

- This condition calculates the deficit of Chi.

#### Returns `NUMBER`
- The deficit of Chi (maximum Chi - current Chi).

#### *Example:*
```lua
-- DSL Mode
{ACTION, "chi.diff > 2"},

-- in Lua code
_A.DSL:Get("chi.diff")() > 2

-- Lua Mode
PLAYER:ChiDiff() > 2
```

***


> ## form

- This condition retrieves the current shapeshift form index that the player is in.

#### Returns `NUMBER`
- The shapeshift form index or 0 if the player is not in any form.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "form == 3"},

-- in Lua code
_A.DSL:Get("form")() == 3

-- Lua Mode
PLAYER:Form() == 3
```

***


> ## lunar.power
  *`lunar.power || lunarpower || astralpower`*

- This condition retrieve the current amount of lunar power (astral power) that the player has.

#### Returns `NUMBER`
- The amount of lunar power (astral power) that the player has.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "lunar.power >= 60"},

-- in Lua code
_A.DSL:Get("lunar.power")() >= 60

-- Lua Mode
PLAYER:LunarPower() >= 60
```

***


> ## mushrooms

- This condition counts the number of Wild Mushroom totems currently active.

#### Returns `NUMBER`
- The number of Wild Mushroom totems currently active.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "mushrooms > 0"},

-- in Lua code
_A.DSL:Get("mushrooms")() > 0

-- Lua Mode
PLAYER:Mushrooms() > 0
```

***


> ## holy.power
  *`holy.power || holypower`*

- This condition retrieves the current amount of Holy Power that the player has.

#### Returns `NUMBER`
- The amount of Holy Power that the player currently has.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "holy.power >= 60"},

-- in Lua code
_A.DSL:Get("holy.power")() >= 60

-- Lua Mode
PLAYER:HolyPower() >= 60
```

***


> ## rage

- This condition retrieves the current amount of Rage that the player has.

#### Returns `NUMBER`
- The amount of Rage that the player currently has.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "rage >= 50"},

-- in Lua code
_A.DSL:Get("rage")() >= 50

-- Lua Mode
PLAYER:Rage() >= 50
```

***


> ## rage.diff
  *`rage.diff || rage.deficit || ragediff`*

- This condition calculates the deficit of Rage the player has.

#### Returns `NUMBER`
- The deficit of Rage that the player currently has.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "rage.diff >= 15"},

-- in Lua code
_A.DSL:Get("rage.diff")() >= 15

-- Lua Mode
PLAYER:RageDiff() >= 15
```

***


> ## stance

- This condition retrieves the index of the stance that the player is in.

#### Returns `NUMBER`
- The index of the current stance.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "stance == 2"},

-- in Lua code
_A.DSL:Get("stance")() == 2

-- Lua Mode
PLAYER:Stance() == 2
```

***


> ## fury.diff
  *`fury.diff || fury.deficit || furydiff`*

- This condition retrieves the deficit of fury (resource) that the player has.

#### Returns `NUMBER`
- The deficit of fury.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "fury.diff >= 15"},

-- in Lua code
_A.DSL:Get("fury.diff")() >= 15

-- Lua Mode
PLAYER:FuryDiff() >= 15
```

***


> ## pain

- This condition retrieves the current amount of pain (resource) that the player has.

#### Returns `NUMBER`
- The current amount of pain.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "pain >= 30"},

-- in Lua code
_A.DSL:Get("pain")() >= 30

-- Lua Mode
PLAYER:Pain() >= 30
```

***


> ## arcane.charges
  *`arcane.charges || arcanecharges`*

- This condition retrieves the current number of Arcane Charges that the player has.

#### Returns `NUMBER`
- The current number of Arcane Charges.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "arcane.charges >= 15"},

-- in Lua code
_A.DSL:Get("arcane.charges")() >= 15

-- Lua Mode
PLAYER:ArcaneCharges() >= 15
```

***


> ## combo
  *`combo || combo.points || combopoints`*

- This condition retrieves the current number of Combo Points that the player has.

#### Returns `NUMBER`
- The current number of Combo Points.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "combo >= 4"},

-- in Lua code
_A.DSL:Get("combo")() >= 4

-- Lua Mode
PLAYER:Combo() >= 4
```

***


> ## combo.max
  *`combo.max || combomax`*

- This condition returns the maximum number of Combo Points a player can have.

#### Returns `NUMBER`
- The maximum number of Combo Points.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "combo.max > 5"},

-- in Lua code
_A.DSL:Get("combo.max")() > 5

-- Lua Mode
PLAYER:ComboMax() > 5
```

***


> ## combo.diff
  *`combo.diff || combo.deficit || combodiff || combopoints.diff || combopoints.deficit || combopointsdiff`*

- This condition calculates the deficit of Combo Points the player has until reaching the maximum amount.

#### Returns `NUMBER`
- The deficit of Combo Points.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "combo.diff > 2"},

-- in Lua code
_A.DSL:Get("combo.diff")() > 2

-- Lua Mode
PLAYER:ComboDiff() > 2
```

***


> ## time.to.max
  *`time.to.max || timetomax`*

- This condition calculates the estimated time in seconds for a player's resource to reach its maximum value.

#### Returns `NUMBER`
- The estimated time in seconds to reach maximum resource.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "time.to.max < 1"},

-- in Lua code
_A.DSL:Get("time.to.max")() < 1

-- Lua Mode
PLAYER:TimeToMax() < 1
```

***


> ## warlock.minions

- This condition returns the number of Warlock's minions.

#### Returns `NUMBER`
- The number of Warlock's minions.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "warlock.minions > 2"},

-- in Lua code
_A.DSL:Get("warlock.minions")() > 2

-- Lua Mode
PLAYER:WarlockMinions() > 2
```

***


> ## warlock.minions.type

- This condition returns the number of Warlock's minions of a specific type.

#### Parameters
- `type`: The type of minion (e.g., "Imp", "Voidwalker", etc.)

#### Returns `NUMBER`
- The number of Warlock's minions of the specified type.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "warlock.minions(Voidwalker).type > 0"},

-- in Lua code
_A.DSL:Get("warlock.minions.type")(_, "Voidwalker") > 0

-- Lua Mode
PLAYER:WarlockMinionsType("Voidwalker") > 0
```

***


> ## warlock.empower

- This condition returns the number of empowered Warlock's minions.

#### Returns `NUMBER`
- The number of empowered Warlock's minions.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "warlock.empower > 3"},

-- in Lua code
_A.DSL:Get("warlock.empower")() > 3

-- Lua Mode
PLAYER:WarlockEmpower() > 3
```

***


> ## warlock.empower.missing

- This condition returns the number of Warlock's minions that are not currently empowered.

#### Returns `NUMBER`
- The number of unempowered Warlock's minions.

#### *Example:*
```lua
-- DSL Mode
{ACTION, "warlock.empower.missing > 2"},

-- in Lua code
_A.DSL:Get("warlock.empower.missing")() > 2

-- Lua Mode
PLAYER:WarlockEmpowerMissing() > 2
```
