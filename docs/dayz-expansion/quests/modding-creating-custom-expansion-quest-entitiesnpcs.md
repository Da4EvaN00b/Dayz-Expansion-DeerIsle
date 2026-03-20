[Return to the summary](https://github.com/salutesh/DayZ-Expansion-Scripts/wiki/%5BServer-Hosting%5D-Expansion-Quests)

---

If you plan to add your custom quest entities for the Expansion Quest system you can find some examples for the needed
object configuration as well as the needed script classes for NPCs here.

Example **config.cpp**:

```
class CfgPatches
{
    class MyMod_Quests_NPCEntities
    {
        units[]={};
        weapons[]={};
        requiredVersion=0.1;
        requiredAddons[]=
        {
            "DayZExpansion_Quests_Dta_Core"
        };
    };
};

class CfgVehicles
{
    class SurvivorM_Mirek; //! Normal NPC
    class eAI_SurvivorM_Mirek: SurvivorM_Mirek {}; //! AI NPC

    //! Normal NPC
    class ExpansionQuestNPCMirek: SurvivorM_Mirek
    {
	displayName = "Mirek";
	vehicleClass = "Expansion_Trader";
    };

    //! AI NPC
    class ExpansionQuestNPCAIMirek: eAI_SurvivorM_Mirek
    {
	displayName = "Mirek";
	vehicleClass = "Expansion_Trader";
    };

   //! Static object
   class ExpansionQuestObjectLocker: HouseNoDestruct
   {
	scope = 1;
	model="\DZ\structures\furniture\cases\locker\locker_closed_blue_v1.p3d";
	forceFarBubble="true";
   };
};
```

Script class example for a normal quest NPC in the `4_World` script module of your mod:

```
class ExpansionQuestNPCMirek: ExpansionQuestNPCBase {};
```

Script class example for an Enfusion AI quest NPC in the `4_World` script module of your mod:

```
class ExpansionQuestNPCAIMirek: ExpansionQuestNPCAIBase {};
```

Script class example for an static object in the `4_World` script module of your mod:

```
class ExpansionQuestObjectLocker: ExpansionQuestStaticObject {};
```

Copyright© 2020-2026 DayZ Expansion Mod Team. We do not authorize any entity to publish this DayZ Standalone modification without licensing from the DayZ Expansion Mod Team.
