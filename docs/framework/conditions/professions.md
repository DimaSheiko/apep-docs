# PROFESSIONS

---

> ## prof.Skill
>
> _`prof.Skill || profession.Skill`_

-   This DSL returns the player's current skill rank for the given profession.

#### Parameters

-   `PROF`: The name or ID of the profession.

#### Returns `NUMBER`

-   The skill rank of the specified profession, or `-1` if the profession is invalid.

#### Profession IDs

| Profession Name | Profession ID |
| --------------- | ------------- |
| Alchemy         | 171           |
| Blacksmithing   | 164           |
| Enchanting      | 333           |
| Engineering     | 202           |
| Herbalism       | 182           |
| Inscription     | 773           |
| Jewelcrafting   | 755           |
| Leatherworking  | 165           |
| Mining          | 186           |
| Skinning        | 393           |
| Tailoring       | 197           |
| Archaeology     | 794           |
| Fishing         | 356           |
| Cooking         | 185           |
| First Aid       | 129           |

#### _Examples:_

=== "DSL"

    ```lua
    {ACTION, "prof(Mining).Skill >= 300"},
    {ACTION, "profession(186).Skill >= 300"}, -- (1)!
    ```

    1. Using the profession ID instead of name

=== "Lua Code"

    ```lua
    _A.DSL:Get("prof.Skill")(_, "Mining") >= 300
    _A.DSL:Get("profession.Skill")(_, 186) >= 300
    ```

=== "Lua Mode"

    ```lua
    PLAYER:ProfSkill("Mining") >= 300
    PLAYER:ProfessionSkill(186) >= 300
    ```

