[Return to the summary](https://github.com/salutesh/DayZ-Expansion-Scripts/wiki/%5BServer-Hosting%5D-Expansion-Quests)

---

## Setting Parameters:

### `"m_Version"`

Integer.

Current setting file verstion. NEVER CHANGE THIS!

### `"EnableQuests"`

Boolean.

Enable\disable the quest system.

### `"EnableQuestLogTab"`

Boolean.

Only used if the Expansion-Book mod is loaded next to the quest mod.
Enable\disable the book quest log tab.

### `"CreateQuestNPCMarkers"`

Boolean.

Only used if the Expansion-Navigation mod is loaded next to the quest mod.
Set server map markers on the quest NPC spawn locations.
NOT WORKING AT THIS POINT. SUBJECT TO CHANGE!

### `"QuestAcceptedTitle"`

String.

Text that will displayed in the notification title field when a quest is accepted.

### `"QuestAcceptedText"`

String.

Text that will displayed in the notification text field when a quest is accepted.

### `"QuestCompletedTitle"`

String.

Text that will displayed in the notification title field when a quest is completed.

### `"QuestCompletedText"`

String.

Text that will displayed in the notification text field when a quest is completed.

### `"QuestFailedTitle"`

String.

Text that will displayed in the notification title field when a quest is failed.

### `"QuestFailedText"`

String.

Text that will displayed in the notification text field when a quest is failed.

### `"QuestCanceledTitle"`

String.

Text that will displayed in the notification title field when a quest is canceled.

### `"QuestCanceledTitle"`

String.

Text that will displayed in the notification text field when a quest is canceled.

### `"QuestTurnInTitle"`

String.

Text that will displayed in the notification title field when a quest is turned-in.

### `"QuestTurnInText"`

String.

Text that will displayed in the notification text field when a quest is turned-in.

### `"QuestObjectiveCompletedTitle"`

String.

Text that will displayed in the notification title field when a quest objective is completed.

### `"QuestObjectiveCompletedText"`

String.

Text that will displayed in the notification text field when a quest objective is completed.

### `"AchivementCompletedTitle"`

String.

Text that will displayed in the notification title field when a achivement quest is completed.

### `"AchivementCompletedText"`

String.

Text that will displayed in the notification text field when a achivement quest is completed.

### `"WeeklyQuestResetDay"`

String.

Day name in english when the weekly quest reset should happend.

### `"WeeklyQuestResetHour"`

Integer.

Hour at when the quest reset will happend for all weekly quests.

### `"WeeklyQuestResteMinute"`

Integer.

Minute at when the quest reset will happend for all weekly quests.

### `"DailyQuestResetHour"`

Integer.

Hour at when the quest reset will happend for all daily quests.

### `"DailyQuestResetMinute"`

Integer.

Minute at when the quest reset will happend for all daily quests.

### `"UseUTCTime"`

Boolean

Use UTC server time or not for all quest cooldown and reset times.

### `"QuestCooldownTitle"`

String.

Text that will displayed in the notification title field when a quest is on cooldown.

### `"QuestCooldownText"`

String.

Text that will displayed in the notification text field when a quest is on cooldown.

### `"QuestNotInGroupTitle"`

String.

Text that will displayed in the notification title field when a group quest is accepted without beeing in a group.

### `"QuestNotInGroupText"`

String.

Text that will displayed in the notification text field when a group quest is accepted without beeing in a group.

### `"QuestNotGroupOwnerTitle"`

String.

Text that will displayed in the notification title field when a group quest is accepted/turned-in and the player is not the group owner.

### `"QuestNotGroupOwnerText"`

String.

Text that will displayed in the notification text field when a group quest is accepted/turned-in and the player is not the group ownerp.

### `"GroupQuestMode"`

Integer.

0 - Only group owners can accept and turn-in group quests.

1 - Only group owner can turn-in group quest but all group members can accept them.

2 - All group members can accept and turn-in group quests.

---

Example:

```
{
    "m_Version": 10,
    "EnableQuests": 1,
    "EnableQuestLogTab": 1,
    "CreateQuestNPCMarkers": 1,
    "QuestAcceptedTitle": "Quest Accepted",
    "QuestAcceptedText": "The quest %1 has been accepted!",
    "QuestCompletedTitle": "Quest Completed",
    "QuestCompletedText": "All objectives of the quest %1 have been completed",
    "QuestFailedTitle": "Quest Failed",
    "QuestFailedText": "The quest %1 failed!",
    "QuestCanceledTitle": "Quest Canceled",
    "QuestCanceledText": "The quest %1 has been canceled!",
    "QuestTurnInTitle": "Quest Turn-In",
    "QuestTurnInText": "The quest %1 has been completed!",
    "QuestObjectiveCompletedTitle": "Objective Completed",
    "QuestObjectiveCompletedText": "You have completed the objective %1 of the quest %2.",
    "QuestCooldownTitle": "Quest Cooldown",
    "QuestCooldownText": "This quest is still on cooldown! Come back in %1",
    "QuestNotInGroupTitle": "Group Quest",
    "QuestNotInGroupText": "Group quests can only be accepted while in a group!",
    "QuestNotGroupOwnerTitle": "Group Quest",
    "QuestNotGroupOwnerText": "Only a group owner can accept and turn-in a group quest!",
    "GroupQuestMode": 0,
    "AchievementCompletedTitle": "Achievement \"%1\" completed!",
    "AchievementCompletedText": "%1",
    "WeeklyResetDay": "Wednesday",
    "WeeklyResetMinute": 0,
    "WeeklyResetHour": 8,
    "DailyResetHour": 8,
    "DailyResetMinute": 0,
    "UseUTCTime": 0,
    "UseQuestNPCIndicators": 1,
    "MaxActiveQuests": 5
}
```

Copyright© 2020-2026 DayZ Expansion Mod Team. We do not authorize any entity to publish this DayZ Standalone modification without licensing from the DayZ Expansion Mod Team.
