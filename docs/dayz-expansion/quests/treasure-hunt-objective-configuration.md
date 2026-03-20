[Return to the quest objectives](https://github.com/salutesh/DayZ-Expansion-Scripts/wiki/%5BServer-Hosting%5D-Quest-Objectives-Configuration)

Example Configuration:

```
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
        [
            2936.47998046875,
            350.6139831542969,
            6369.39013671875
        ],
        [
            3143.35009765625,
            365.7760009765625,
            6942.0400390625
        ],
        [
            5233.509765625,
            290.8810119628906,
            6246.3701171875
        ]
    ],
    "Loot": [
        {
            "Name": "AKM",
            "Attachments": [
                "AK_WoodBttstck",
                "AK_WoodHndgrd",
                "Mag_AKM_30Rnd"
            ],
            "Chance": 1.0,
            "QuantityPercent": -2,
            "Max": 1,
            "Min": 0,
            "Variants": []
        },
        {
            "Name": "Mag_AKM_30Rnd",
            "Attachments": [],
            "Chance": 1.0,
            "QuantityPercent": -2,
            "Max": 2,
            "Min": 2,
            "Variants": []
        }
    ],
    "LootItemsAmount": 3,
    "MaxDistance": 10.0
}
```

### `"ShowDistance"`

Boolean.

Controls whether the distance to the objective position will be displayed in the quest HUD.

### `"ContainerName"`

String.

Container entity class name that will be used for this objective. The entity class always needs to inherit from "ExpansionQuestContainerBase".

### `"DigInStash"`

Boolean.

Controls if the container will be dug into an underground stash or not.

### `"MarkerName"`

String.

Text for the objective quest marker. Leave empty to create no marker.

### `"MarkerVisibility"`

Integer.

Defines the visibility of the objective quest marker. (4 - visible on map | 2 - visible in world | 6 - visible on map and in world.)

### `"ShowDistance"`

Boolean.

Controls whether the distance to the objective position will be displayed in the quest HUD.

### `"Positions"`

Array[Vector].

A random position from this array will be selected when the quest with this objective is started and set as the stash and objective position.

### `"Loot"`

Array[ExpansionLoot].

Loot reward items that will get spawned/attached into/on the stash.

### `"LootItemsAmount"`

Integer.

Max amount of loot items that will get selected and spawned into the stash from the defined expansion loot configuration.

### `"MaxDistance"`

Float.

If a quest player is within a given range of the objective position the stash will be created and spawned.

Copyright© 2020-2026 DayZ Expansion Mod Team. We do not authorize any entity to publish this DayZ Standalone modification without licensing from the DayZ Expansion Mod Team.
