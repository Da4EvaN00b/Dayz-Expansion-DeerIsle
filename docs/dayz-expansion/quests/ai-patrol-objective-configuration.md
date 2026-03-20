[Return to the quest objectives](https://github.com/salutesh/DayZ-Expansion-Scripts/wiki/%5BServer-Hosting%5D-Quest-Objectives-Configuration)

Example Configuration:

```
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
        "Waypoints": [
            [
                6914.7001953125,
                403.0270080566406,
                11381.7001953125
            ],
            [
                6931.27001953125,
                399.8599853515625,
                11456.7001953125
            ],
            [
                6891.919921875,
                397.4549865722656,
                11496.099609375
            ],
            [
                6850.8798828125,
                399.1470031738281,
                11468.099609375
            ],
            [
                6883.97998046875,
                403.1919860839844,
                11380.7998046875
            ]
        ],
        "Behaviour": 0,
        "Formation": "RANDOM",
        "Loadout": "BanditLoadout",
        "Faction": "West",
        "Speed": 1.0,
        "ThreatSpeed": 3.0,
        "MinAccuracy": 0.0,
        "MaxAccuracy": 0.0,
        "CanBeLooted": 1,
        "UnlimitedReload": 1,
        "ThreatDistanceLimit": 150.0,
        "DamageMultiplier": 1.0,
        "DamageReceivedMultiplier": 1.0,
        "ClassNames": [
            "eAI_SurvivorF_Eva",
            "eAI_SurvivorF_Frida",
            "eAI_SurvivorF_Gabi",
            "eAI_SurvivorF_Helga",
            "eAI_SurvivorF_Irena",
            "eAI_SurvivorF_Judy",
            "eAI_SurvivorF_Keiko",
            "eAI_SurvivorF_Linda",
            "eAI_SurvivorF_Maria",
            "eAI_SurvivorF_Naomi",
            "eAI_SurvivorF_Baty",
            "eAI_SurvivorM_Boris",
            "eAI_SurvivorM_Cyril",
            "eAI_SurvivorM_Denis",
            "eAI_SurvivorM_Elias",
            "eAI_SurvivorM_Francis",
            "eAI_SurvivorM_Guo",
            "eAI_SurvivorM_Hassan",
            "eAI_SurvivorM_Indar",
            "eAI_SurvivorM_Jose",
            "eAI_SurvivorM_Kaito",
            "eAI_SurvivorM_Lewis",
            "eAI_SurvivorM_Manua",
            "eAI_SurvivorM_Mirek",
            "eAI_SurvivorM_Niki",
            "eAI_SurvivorM_Oliver",
            "eAI_SurvivorM_Peter",
            "eAI_SurvivorM_Quinn",
            "eAI_SurvivorM_Rolf",
            "eAI_SurvivorM_Seth",
            "eAI_SurvivorM_Taiki"
        ],
        "SniperProneDistanceThreshold": 300.0,
        "RespawnTime": 1.0,
        "DespawnTime": 1.0,
        "MinDistanceRadius": 50.0,
        "MaxDistanceRadius": 150.0,
        "DespawnRadius": 880.0
    },
    "MaxDistance": -1.0,
    "MinDistance": -1.0,
    "AllowedWeapons": [],
    "AllowedDamageZones": []
}
```

### `"NumberOfAI"`

Integer.

Amount of spawned AI units for this patrol group.

### `"NPCName"`

String.

Name of the AI units that will be displayed in all name tags and tooltips for the spawned AI unit.

### `"Waypoints"`

array.

Waypoints that will be used for the spawned AI patrol to follow. The first entry should always be the initial spawn position.

### `"Behaviour"`

[eAIWaypointBehavior](https://github.com/salutesh/DayZ-Expansion-Scripts/blob/a57d77e0acc3ed4ddf144e5ee3d5972a256156d9/DayZExpansion/AI/Scripts/3_Game/DayZExpansion_AI/Enums/AIenums.c#L1).

Waypoint behavior that will be used for the spawned AI patrol.

* 0 = HALT
* 1 = LOOP
* 2 = ALTERNATE,
* 3 = HALT\_OR\_LOOP
* 4 = HALT\_OR\_ALTERNATE

### `"Formation"`

[eAuFormation](https://github.com/salutesh/DayZ-Expansion-Scripts/tree/release/DayZExpansion/AI/Scripts/4_World/DayZExpansion_AI/Classes/Formations).

The eAIFormation used for the spawned AI patrol.

### `"Faction"`

String.

Faction used for the spawned AI patrol.

### `"Loadout"`

String.

AI unit loadout file used from the AI loaded folder. Same as for AI patrol settings.

### `"Faction"`

String.

[eAIFaction](https://github.com/salutesh/DayZ-Expansion-Scripts/tree/release/DayZExpansion/AI/Scripts/3_Game/DayZExpansion_AI/Factions) type used for the spawned AI unit.

### `"Speed"`

String.

Min. speed of the spawned AI patrol.

### `"ThreatSpeed"`

Float.

Max. speed of spawned AI patrol when in threat mode.

### `"MinAccuracy"`

Float.

Min. weapon accuracy of the spawned AI patrol.

### `"MaxAccuracy"`

Float.

Max. weapon accuracy of the spawned AI patrol.

### `"CanBeLooted"`

Boolean.

Enable/disable if the spawned AI patrol can be looted or not.

### `"UnlimitedReload"`

Boolean.

Enable/disable if the spawned AI patrol has unlimited reloads with weapons.

### `"ThreatDistanceLimit"`

Float.

Max. distance from the AI patrol`s spawn position the AI unit can be away from before it loses its current threat target.

### `"DamageMultiplier"`

Float.

Damage multiplier the AI units will have for all its damage dealt on hit targets. Can also be a negative value to reduce the damage dealt on target.

### `"DamageReceivedMultiplier"`

Float.

Damage multiplier the AI units will have for all its damage received. Can also be a negative value to reduce incoming damage.

### `"ClassNames"`

Array[String].

Class names that will be used to spawn the AI patrol units, have to be a valid eAIBase entity type.

### `"SniperProneDistanceThreshold"`

Float.

Distance to a current target the AI patrol units can have within the units will use the prone stance to increase there accuracy.

### `"RespawnTime"`

Float.

Respawn time of the AI units when no player is within the defined proximity range defined by the `"MinDistanceRadius"` and `"MaxDistanceRadius"` parameters.

### `"DespawnTime"`

Float.

Despawn time of the AI units when no player is within the defined proximity range defined by the `"MinDistanceRadius"` and `"MaxDistanceRadius"` parameters.

### `"MinDistanceRadius"`

Float.

### `"MaxDistanceRadius"`

Float.

Spawns AI patrol units when a player is not within the defined proximity range defined by the `"MinDistanceRadius"` and `"MaxDistanceRadius"` parameters from the AI unit spawn position.

### `"DespawnRadius"`

Float.

Despawns AI patrol units when a player is outside the defined proximity range from the AI unit's spawn position.

---

### `"MaxDistance"`

Float.

Min. distance a player can have to an executed AI unit to count the kill for the objective.

### `"MinDistance"`

Float.

Max. distance a player can have to an executed AI unit to count the kill for the objective.

### `"AllowedWeapons"`

Array[String].

If not empty then this array controls the allowed weapons the quest players can and need to use to kill certain objective targets. Leave empty to disable this check.

### `"AllowedDamageZones"`

Array[String].

If not empty then you can define valid hit zones where the player needs to hit to execute an AI unit to count the kill for the objective.

Valid AI/Players and infected damage zones:

* Head
* Brain
* LeftArm
* RightArm
* LeftLeg
* RightLeg
* LeftFoot
* RightFoot
* Torso

For all other entities check the certain RV CfgVehicles configuration class (config.cpp) of the entity and look up the children of the DamageZones class of that type. The children's class names are the damage zone names used for this parameter.

Copyright© 2020-2026 DayZ Expansion Mod Team. We do not authorize any entity to publish this DayZ Standalone modification without licensing from the DayZ Expansion Mod Team.
