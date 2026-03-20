# Expansion Quests Documentation

## Quest Configuration Files

Quest config files can be named anything, as long as they have the `.json` extension and are placed in the quest configurations folder. All files in that folder are loaded by the quest system.

---

## Quest Parameters

**`ConfigVersion`** — Integer

Current config file version. Do not change.

---

**`ID`** — Integer

Unique quest ID. Must be different for every quest.

---

**`Type`** — Integer

Quest type. Use type `1` for all standard quests.

- `NORMAL = 1`

---

**`Title`** — String

Quest title displayed to players.

---

**`Descriptions`** — Array (max 3 entries)

| Index | When Shown |
|-------|-----------|
| `0` | When the player receives the quest |
| `1` | While the quest is active (only at quest NPCs) |
| `2` | When turning in the quest (only at the turn-in NPC) |

---

**`ObjectiveText`** — String

Short objective description shown in the HUD.

---

**`FollowUpQuest`** — Integer

Quest ID of a follow-up quest. Automatically shared with the player when this quest is completed.

---

**`Repeatable`** — Boolean

Quest can be completed more than once.

---

**`IsDailyQuest`** — Boolean

Quest resets on the server's daily reset time.

---

**`IsWeeklyQuest`** — Boolean

Quest resets on the server's weekly reset day/time.

---

**`CancelQuestOnPlayerDeath`** — Boolean

Quest is canceled if the quest player (or a group member) dies.

---

**`Autocomplete`** — Boolean

Quest completes automatically when all objectives are done.

---

**`IsGroupQuest`** — Boolean

Quest is a group quest.

---

**`ObjectSetFileName`** — String

Name of a `.map` file (without extension) to spawn a set of objects when the quest starts. File must be located at:

```
MISSION.MAPNAME/expansion/quests/objects/
```

---

**`QuestItems`** — Array\<ExpansionQuestItemConfig\>

Items given to the player when starting the quest. Deleted on cancel/completion or relog (re-added on reconnect if quest is still active).

```json
{
    "ClassName": "SledgeHammer",
    "Amount": 1
}
```

---

**`Rewards`** — Array\<ExpansionQuestRewardConfig\>

Items the player receives on quest turn-in.

```json
{
    "ClassName": "TaloonBag_Blue",
    "Amount": 1,
    "Attachments": [],
    "DamagePercent": 0,
    "QuestID": -1,
    "Chance": 1.0
}
```

| Field | Description |
|-------|-------------|
| `ClassName` | Class name of the reward item |
| `Amount` | How many of the item to give |
| `Attachments` | Attachments applied to the reward item |
| `DamagePercent` | Damage percent of the item (applied to attachments too) |
| `QuestID` | If set, makes the reward item a quest giver for that quest ID |
| `Chance` | Used when `RandomReward` is enabled |

---

**`NeedToSelectReward`** — Boolean

If enabled and multiple rewards exist, the player must select one reward on turn-in.

---

**`RandomReward`** — Boolean

If enabled, rewards are selected randomly based on their `Chance` values.

---

**`RandomRewardAmount`** — Integer

Number of randomly selected reward items each player receives when `RandomReward` is enabled.

---

**`RewardsForGroupOwnerOnly`** — Boolean

If enabled on a group quest, only the group owner receives the rewards.

---

**`QuestGiverIDs`** — Array

Unique NPC IDs (from the quest NPC configuration) of NPCs that hand out this quest.

---

**`QuestTurnInIDs`** — Array

Unique NPC IDs of NPCs that accept the completed quest.

---

**`IsAchivement`** — Boolean

Quest is an achievement quest; added to new players automatically on first join.

---

**`Objectives`** — Array\<ExpansionQuestObjectiveConfigBase\>

Quest objectives the player must complete.

```json
{
    "ConfigVersion": 21,
    "ID": 3,
    "ObjectiveType": 3
}
```

### Objective Types

| Value | Name | Description |
|-------|------|-------------|
| `2` | TARGET | Kill a certain number of mobs/players (optionally with a specific weapon) |
| `3` | TRAVEL | Travel to a location |
| `4` | COLLECT | Collect/find a certain number of items |
| `5` | DELIVERY | Deliver items to a position/NPC |
| `6` | TREASUREHUNT | Find a location containing a stashed treasure |
| `7` | AIPATROL | Clear an AI patrol (optionally with a specific weapon) |
| `8` | AICAMP | Clear an AI camp (optionally with a specific weapon) |
| `9` | AIVIP | Protect and escort an AI to a location |
| `10` | ACTION | Execute a certain in-game action |
| `11` | CRAFTING | Craft certain items |

---

**`QuestColor`** — Integer

Main color for the quest in menus and HUD.

---

**`ReputationReward`** — Integer *(Hardline only)*

Reputation reward on quest completion.

---

**`ReputationRequirement`** — Integer *(Hardline only)*

Reputation points required to see and accept the quest.

---

**`PreQuestIDs`** — Array

Quest IDs that must be completed before this quest becomes available.

---

**`RequiredFaction`** — String *(AI mod only)*

Name of the Expansion-AI faction the player must be in to see/accept/complete this quest.

---

**`FactionReward`** — String *(AI mod only)*

Name of the Expansion-AI faction the player joins as a reward for completing this quest.

---

**`PlayerNeedQuestItems`** — Boolean

If enabled, the quest is canceled if the player is missing quest items on reconnect.

---

**`DeleteQuestItems`** — Boolean

If enabled, quest items are deleted on quest completion. (Quest items are always deleted on cancel.)

---

**`SequentialObjectives`** — Boolean

If enabled, quest objectives must be completed in order.

---

**`FactionReputationRequirements`** — Map\<String, Integer\>

Reputation points required per faction to see and start the quest.

```json
"FactionReputationRequirements": {
    "Survivors": 500
}
```

---

**`FactionReputationRewards`** — Map\<String, Integer\>

Reputation points awarded per faction on quest completion.

```json
"FactionReputationRewards": {
    "Survivors": 500
}
```

---

**`SuppressQuestLogOnCompetion`** — Boolean

Suppresses the quest log display on completion when the quest has no `QuestGiverIDs` set.

---

**`Active`** — Boolean

Enable/disable this config file from being loaded by the quest system.

---

## Example Quest Configuration

```json
{
    "ConfigVersion": 21,
    "ID": 2,
    "Type": 1,
    "Title": "A favor for Steve...",
    "Descriptions": [
        "So, Peter sends you, hmm? Well I have what he wants... Let's say if you do me a favor, too, I'll give you what Peter wants and even more. Clean up the village with this sledgehammer.",
        "You are not done yet? How hard can it be to smash some heads with that hammer... Come back when the job is done!",
        "Oh there you are! I thought the Infected got your ass... Well, here is your reward."
    ],
    "ObjectiveText": "Kill 10 civilian Infected with Steve's sledgehammer.",
    "FollowUpQuest": 3,
    "Repeatable": 0,
    "IsDailyQuest": 0,
    "IsWeeklyQuest": 0,
    "CancelQuestOnPlayerDeath": 0,
    "Autocomplete": 0,
    "IsGroupQuest": 0,
    "ObjectSetFileName": "",
    "QuestItems": [{ "ClassName": "SledgeHammer", "Amount": 1 }],
    "Rewards": [
        { "ClassName": "WaterBottle", "Amount": 1, "Attachments": [], "DamagePercent": 0, "QuestID": -1, "Chance": 1.0 },
        { "ClassName": "TunaCan", "Amount": 1, "Attachments": [], "DamagePercent": 0, "QuestID": -1, "Chance": 1.0 }
    ],
    "NeedToSelectReward": 0,
    "RandomReward": 0,
    "RandomRewardAmount": 0,
    "RewardsForGroupOwnerOnly": 1,
    "QuestGiverIDs": [2],
    "QuestTurnInIDs": [2],
    "IsAchievement": 0,
    "Objectives": [
        { "ConfigVersion": 26, "ID": 2, "ObjectiveType": 3 },
        { "ConfigVersion": 26, "ID": 1, "ObjectiveType": 2 }
    ],
    "QuestColor": 0,
    "ReputationReward": 0,
    "ReputationRequirement": -1,
    "PreQuestIDs": [1],
    "RequiredFaction": "",
    "FactionReward": "",
    "PlayerNeedQuestItems": 1,
    "DeleteQuestItems": 1,
    "SequentialObjectives": 1,
    "FactionReputationRequirements": {},
    "FactionReputationRewards": {},
    "SuppressQuestLogOnCompetion": 0,
    "Active": 1
}
```

---

## Special Quest Configurations

### Auto-Start Quest

Added to the player on first server connection. Required settings:

```json
"QuestGiverIDs": [],   // No quest giver NPCs
"IsAchivement": 0,     // Not an achievement
"IsGroupQuest": 0,     // Not a group quest
"PreQuestIDs": []      // No prerequisites
```

### Achievement Quest

Added automatically on first join; player is only notified upon completion. Required settings:

```json
"QuestGiverIDs": [],   // No quest giver NPCs
"IsAchivement": 1,     // Must be flagged as achievement
"Autocomplete": 1,     // Must autocomplete
"IsGroupQuest": 0,     // Not a group quest
"PreQuestIDs": []      // No prerequisites
```

### Daily Quest

Completable once per day; resets at the server's configured daily reset time.

```json
"Repeatable": 1,
"IsDailyQuest": 1,
"IsWeeklyQuest": 0
```

### Weekly Quest

Completable once per week; resets at the server's configured weekly reset day/time.

```json
"Repeatable": 1,
"IsDailyQuest": 0,
"IsWeeklyQuest": 1
```

---

## Objective Files and Configuration

Objective config files can be named anything with a `.json` extension and must be placed in the appropriate objective category folder.

### Common Objective Parameters

**`ConfigVersion`** — Integer. Do not change.

**`ID`** — Integer. Unique within the same objective category. The same ID can be reused in a different category.

**`ObjectiveType`** — Integer. Must match the category folder the file is in (see [Objective Types](#objective-types) above).

**`ObjectiveText`** — String. Displayed in the quest log and HUD when the objective is active.

**`TimeLimit`** — Integer. Time limit in seconds to complete this objective. `-1` means no limit.

**`Active`** — Boolean. Enable/disable this objective config from being loaded.

---

## Objective Type Details

### Action Objective (Type 10)

Players must execute a specific in-game action.

```json
{
    "ConfigVersion": 26,
    "ID": 1,
    "ObjectiveType": 10,
    "ObjectiveText": "Lockpick a vehicle",
    "TimeLimit": -1,
    "Active": 1,
    "ActionNames": [
        "ExpansionVehicleActionPickLock",
        "ExpansionActionPickVehicleLockBase"
    ],
    "AllowedClassNames": [],
    "ExcludedClassNames": [],
    "ExecutionAmount": 1
}
```

| Field | Description |
|-------|-------------|
| `ActionNames` | Class names of actions that trigger this objective |
| `AllowedClassNames` | Items/entities allowed for the action (empty = any) |
| `ExcludedClassNames` | Items/entities excluded from the action |
| `ExecutionAmount` | How many times the action must be performed |

---

### AI Camp Objective (Type 8)

Players must clear an AI camp (kill all AI units at specified positions).

Key fields beyond common parameters:

| Field | Type | Description |
|-------|------|-------------|
| `InfectedDeletionRadius` | Float | Radius to delete infected in the objective area; `0` disables |
| `AISpawns` | Array | Array of individual AI spawn entries (one unit per entry) |
| `MaxDistance` / `MinDistance` | Float | Distance range from the AI unit's position for kills to count |
| `AllowedWeapons` | Array[String] | Required weapons for kills to count (empty = any) |
| `AllowedDamageZones` | Array[String] | Required hit zones for kills to count (empty = any) |

**AISpawn entry fields:**

| Field | Type | Description |
|-------|------|-------------|
| `NumberOfAI` | Integer | Should always be `1` for camp objectives |
| `NPCName` | String | Display name in name tags/tooltips |
| `Waypoints` | Array | Spawn position (first entry) and optional patrol points |
| `Behaviour` | Integer | `0`=HALT, `1`=LOOP, `2`=ALTERNATE, `3`=HALT_OR_LOOP, `4`=HALT_OR_ALTERNATE |
| `Formation` | String | Use `"RANDOM"` for individual units |
| `Loadout` | String | Loadout file name (from AI Loadouts folder) |
| `Faction` | String | eAI faction |
| `Speed` | Float | Minimum movement speed |
| `ThreatSpeed` | Float | Speed when in threat mode |
| `MinAccuracy` / `MaxAccuracy` | Float | Weapon accuracy range |
| `CanBeLooted` | Boolean | Whether the AI can be looted |
| `UnlimitedReload` | Boolean | Whether the AI has unlimited ammo reloads |
| `ThreatDistanceLimit` | Float | Max distance from spawn before losing threat target |
| `DamageMultiplier` | Float | Damage output multiplier |
| `DamageReceivedMultiplier` | Float | Damage received multiplier |
| `ClassNames` | Array[String] | Valid eAIBase entity class names to spawn |
| `SniperProneDistanceThreshold` | Float | Distance at which AI goes prone |
| `RespawnTime` | Float | Time to respawn when no player in proximity |
| `DespawnTime` | Float | Time to despawn when no player in proximity |
| `MinDistanceRadius` / `MaxDistanceRadius` | Float | Player proximity range for spawn/despawn |
| `DespawnRadius` | Float | Despawn range from spawn position |

**Valid damage zones:**
`Head`, `Brain`, `LeftArm`, `RightArm`, `LeftLeg`, `RightLeg`, `LeftFoot`, `RightFoot`, `Torso`

---

### AI Patrol Objective (Type 7)

Players must clear an AI patrol group.

Same fields as AI Camp but uses a single `AISpawn` object (not an array) with `NumberOfAI` > 1 for the whole group sharing waypoints.

```json
{
    "ConfigVersion": 26,
    "ID": 1,
    "ObjectiveType": 7,
    "ObjectiveText": "Kill all 4 units of the bandit patrol at the marked location",
    "TimeLimit": -1,
    "Active": 1,
    "AISpawn": {
        "NumberOfAI": 4,
        "NPCName": "Quest Target",
        "Waypoints": [ [...], [...], [...] ],
        "Behaviour": 0,
        "Formation": "RANDOM",
        "Loadout": "BanditLoadout",
        "Faction": "West",
        ...
    },
    "MaxDistance": -1.0,
    "MinDistance": -1.0,
    "AllowedWeapons": [],
    "AllowedDamageZones": []
}
```

---

### AI VIP Objective (Type 9)

Players must escort an AI unit to a destination.

```json
{
    "ConfigVersion": 26,
    "ID": 1,
    "ObjectiveType": 9,
    "ObjectiveText": "Bring the VIP to the marked location.",
    "TimeLimit": 180,
    "Active": 1,
    "Position": [3193.59, 296.71, 6090.57],
    "MaxDistance": 20.0,
    "MarkerName": "Escort VIP",
    "ShowDistance": 1,
    "CanLootAI": 0,
    "NPCLoadoutFile": "BanditLoadout",
    "NPCClassName": "",
    "NPCName": "Survivor"
}
```

| Field | Description |
|-------|-------------|
| `Position` | Destination position the VIP must be escorted to |
| `MaxDistance` | Range from destination to trigger completion |
| `MarkerName` | Objective marker text (empty = no marker) |
| `ShowDistance` | Show distance to objective in HUD |
| `CanLootAI` | Whether the spawned AI VIP can be looted |
| `NPCLoadoutFile` | Loadout file for the VIP NPC |
| `NPCClassName` | eAI entity class name (empty = random) |
| `NPCName` | Display name for the VIP |

---

### Collection Objective (Type 4)

Players must collect/find a certain number of items.

```json
{
    "ConfigVersion": 26,
    "ID": 1,
    "ObjectiveType": 4,
    "ObjectiveText": "Collect 5 apples",
    "TimeLimit": -1,
    "Active": 1,
    "Collections": [
        { "Amount": 5, "ClassName": "Apple", "QuantityPercent": -1, "MinQuantityPercent": 0 }
    ],
    "ShowDistance": 1,
    "AddItemsToNearbyMarketZone": 0,
    "NeedAnyCollection": 0
}
```

| Field | Description |
|-------|-------------|
| `Collections` | Items to collect; `QuantityPercent` = max stack %, `MinQuantityPercent` = min stack % |
| `ShowDistance` | Show distance to objective in HUD |
| `AddItemsToNearbyMarketZone` | Add collected items to nearby market zone stock on completion |
| `NeedAnyCollection` | If enabled, player only needs one of the listed items (player selects which) |

---

### Crafting Objective (Type 11)

Players must craft specific items.

```json
{
    "ConfigVersion": 26,
    "ID": 1,
    "ObjectiveType": 11,
    "ObjectiveText": "Craft an improvised fishing rod",
    "TimeLimit": -1,
    "Active": 1,
    "ItemNames": ["ImprovisedFishingRod"],
    "ExecutionAmount": 1
}
```

| Field | Description |
|-------|-------------|
| `ItemNames` | Class names of craftable items that complete the objective |
| `ExecutionAmount` | How many times the crafting action must be performed |

---

### Delivery Objective (Type 5)

Players must deliver items to a specific position/NPC.

```json
{
    "ConfigVersion": 26,
    "ID": 1,
    "ObjectiveType": 5,
    "ObjectiveText": "Deliver the note to Steve",
    "TimeLimit": -1,
    "Active": 1,
    "Collections": [
        { "Amount": 1, "ClassName": "ExpansionQuestItemPaper", "QuantityPercent": -1, "MinQuantityPercent": 0 }
    ],
    "ShowDistance": 1,
    "AddItemsToNearbyMarketZone": 0,
    "MaxDistance": 10.0,
    "MarkerName": "Deliver Items"
}
```

Items in `Collections` are spawned on the quest player when the quest starts. Use `QuantityPercent: 10` for stackable items (ammo, pills) to match the needed amount.

| Field | Description |
|-------|-------------|
| `MaxDistance` | Distance to the turn-in NPC to complete the objective |
| `MarkerName` | Objective marker text (requires Expansion-Navigation mod) |

---

### Target Objective (Type 2)

Players must kill a certain number of specified entities.

```json
{
    "ConfigVersion": 26,
    "ID": 1,
    "ObjectiveType": 2,
    "ObjectiveText": "Kill 10 Infected with a sledgehammer",
    "TimeLimit": -1,
    "Active": 1,
    "Position": [2596.7, 306.1, 6378.47],
    "MaxDistance": 150.0,
    "MinDistance": -1.0,
    "Amount": 10,
    "ClassNames": ["ZmbM_CitizenASkinny_Base", "..."],
    "CountSelfKill": 0,
    "AllowedWeapons": ["SledgeHammer"],
    "ExcludedClassNames": [],
    "CountAIPlayers": 0,
    "AllowedTargetFactions": [],
    "AllowedDamageZones": []
}
```

| Field | Description |
|-------|-------------|
| `Position` | Area where targets must be eliminated (empty/zero = anywhere) |
| `MaxDistance` | Max range from position for kills to count |
| `MinDistance` | Min range from position for kills to count |
| `Amount` | Number of kills required |
| `ClassNames` | Valid target entity class names |
| `CountSelfKill` | Count player suicides/friendly kills toward objective |
| `AllowedWeapons` | Required weapons (empty = any) |
| `ExcludedClassNames` | Entities that don't count toward the objective |
| `CountAIPlayers` | Count Expansion AI units toward objective |
| `AllowedTargetFactions` | Required faction for player/AI targets |
| `AllowedDamageZones` | Required hit zones for kills to count |

---

### Travel Objective (Type 3)

Players must travel to a specific location.

```json
{
    "ConfigVersion": 26,
    "ID": 1,
    "ObjectiveType": 3,
    "ObjectiveText": "Get to the Village",
    "TimeLimit": -1,
    "Active": 1,
    "Position": [4333.37, 311.78, 6299.88],
    "MaxDistance": 20.0,
    "MarkerName": "Get to the Village",
    "ShowDistance": 1,
    "TriggerOnEnter": 1,
    "TriggerOnExit": 0
}
```

| Field | Description |
|-------|-------------|
| `Position` | Destination position |
| `MaxDistance` | Range at which the objective triggers as complete |
| `MarkerName` | Objective marker text (empty = no marker) |
| `ShowDistance` | Show distance to objective in HUD |
| `TriggerOnEnter` | Complete objective when entering the area (should always be `1`) |
| `TriggerOnExit` | Set objective incomplete when leaving the area |

---

### Treasure Hunt Objective (Type 6)

Players must find a location containing a hidden stash.

```json
{
    "ConfigVersion": 26,
    "ID": 1,
    "ObjectiveType": 6,
    "ObjectiveText": "Find the location of the treasure",
    "TimeLimit": -1,
    "Active": 1,
    "ShowDistance": 1,
    "ContainerName": "ExpansionQuestSeaChest",
    "DigInStash": 1,
    "MarkerName": "???",
    "MarkerVisibility": 4,
    "Positions": [
        [2936.48, 350.61, 6369.39],
        [3143.35, 365.78, 6942.04],
        [5233.51, 290.88, 6246.37]
    ],
    "Loot": [
        { "Name": "AKM", "Attachments": ["AK_WoodBttstck", "AK_WoodHndgrd", "Mag_AKM_30Rnd"], "Chance": 1.0, "QuantityPercent": -2, "Max": 1, "Min": 0, "Variants": [] },
        { "Name": "Mag_AKM_30Rnd", "Attachments": [], "Chance": 1.0, "QuantityPercent": -2, "Max": 2, "Min": 2, "Variants": [] }
    ],
    "LootItemsAmount": 3,
    "MaxDistance": 10.0
}
```

| Field | Description |
|-------|-------------|
| `ContainerName` | Entity class name for the stash (must inherit `ExpansionQuestContainerBase`) |
| `DigInStash` | Bury the container in an underground stash |
| `MarkerName` | Objective marker text |
| `MarkerVisibility` | `4`=map only, `2`=world only, `6`=map and world |
| `Positions` | Array of possible stash positions; one is chosen randomly when quest starts |
| `Loot` | Loot items spawned into the stash (uses ExpansionLoot format) |
| `LootItemsAmount` | Max number of loot items selected from the `Loot` array |
| `MaxDistance` | Range at which the stash is created and spawned |
