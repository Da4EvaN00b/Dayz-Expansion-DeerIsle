[Return to the quest objectives](https://github.com/salutesh/DayZ-Expansion-Scripts/wiki/%5BServer-Hosting%5D-Quest-Objectives-Configuration)

Example Configuration:

```
{
    "ConfigVersion": 26,
    "ID": 1,
    "ObjectiveType": 4,
    "ObjectiveText": "Collect 5 apples",
    "TimeLimit": -1,
    "Active": 1,
    "Collections": [
        {
            "Amount": 5,
            "ClassName": "Apple",
            "QuantityPercent": -1,
            "MinQuantityPercent": 0
        }
    ],
    "ShowDistance": 1,
    "AddItemsToNearbyMarketZone": 0,
    "NeedAnyCollection": 0
}
```

### `"Collections"`

Array[ExpansionQuestObjectiveDelivery].

Items the quest players need to/can collect for this objective.

### `"Amount"`

Integer.

Amount needed for the objective item.

### `"ClassName"`

String.

Class name of the item needed.

### `"QuantityPercent"`

Integer.

Max. quantity percentage of the item so it gets counted by the objective.

### `"MinQuantityPercent"`

Integer.

Min. quantity percentage of the item so it gets counted by the objective.

### `"ShowDistance"`

Boolean.

Controls whether the distance to the objective position will be displayed in the quest HUD.

### `"AddItemsToNearbyMarketZone"`

Boolean.

Only used when the market mod is loaded and the quest turn-in NPC is within a market zone.
Controls if the objective items get added to the nearby market zone after the quest with this objective has been completed.
The stock and items given in the "Collections" array will then be added to the related market zone on the next server restart.

### `"NeedAnyCollection"`

Boolean.

Controls if the quest players need to collect all the items defined in the "Collections" array or only one.
If this parameter is enabled and players still have more than one objective item then they will need to select the item they want to use to complete this quest when turning the quest in.

Copyright© 2020-2026 DayZ Expansion Mod Team. We do not authorize any entity to publish this DayZ Standalone modification without licensing from the DayZ Expansion Mod Team.
