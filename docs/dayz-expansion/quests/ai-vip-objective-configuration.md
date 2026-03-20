[Return to the quest objectives](https://github.com/salutesh/DayZ-Expansion-Scripts/wiki/%5BServer-Hosting%5D-Quest-Objectives-Configuration)

Example Configuration:

```
{
    "ConfigVersion": 26,
    "ID": 1,
    "ObjectiveType": 9,
    "ObjectiveText": "Bring the VIP to the marked location.",
    "TimeLimit": 180,
    "Active": 1,
    "Position": [
        3193.590087890625,
        296.7070007324219,
        6090.56982421875
    ],
    "MaxDistance": 20.0,
    "MarkerName": "Escort VIP",
    "ShowDistance": 1,
    "CanLootAI": 0,
    "NPCLoadoutFile": "BanditLoadout",
    "NPCClassName": "",
    "NPCName": "Survivor"
}
```

### `"Position"`

Vector.

Objective position to where the VIP AI needs to be escorted.

### `"MaxDistance"`

Float.

If the escorted AI is within the given range from the objective position the objective will be triggered as completed.

### `"MarkerName"`

String.

Text for the objective quest marker. Leave empty to create no marker.

### `"ShowDistance"`

Boolean.

Controls whether the distance to the objective position will be displayed in the quest HUD.

### `"CanLootAI"`

Boolean.

Controls if spawned AI can be looted or not.

### `"NPCLoadoutFile"`

String.

NPC loadout file. Same as for AI patrol settings.

### `"NPCClassName"`

String.

NPC class name of the eAI entity that should be used to spawn in the VIP NPC. Leave the field empty to get a random AI unit.

### `"NPCName"`

String.

Name of the AI units that will be displayed in all name tags and tooltips for the spawned AI unit.

Copyright© 2020-2026 DayZ Expansion Mod Team. We do not authorize any entity to publish this DayZ Standalone modification without licensing from the DayZ Expansion Mod Team.
