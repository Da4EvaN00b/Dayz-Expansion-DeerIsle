# Expansion Roaming AI

Summary of the roaming AI patrol feature for DayZ Expansion.

## Overview

Roaming AI are patrols that traverse the entire map dynamically, rather than following fixed waypoint loops. Configuration is in `AIPatrolSettings.json` at:

```
mpmission/<mapname>/expansion/settings/AIPatrolSettings.json
```

---

## Key Settings

1. **Behavior** — Set `"Behaviour": "ROAMING"` in the patrol configuration to enable roaming AI.

2. **Spawn Points** — Only one spawn point is needed for roaming AI. Multiple waypoints can be used if `"UseRandomWaypointAsStartPoint": 1` is set. AI will spawn at ground level on land, or on the water surface for water coordinates.

3. **Movement** — AI will visit every location on the map if they survive long enough. They may occasionally get stuck, but this should be rare. After exploring the whole map they will revisit previously explored areas.

4. **Persistency** — Enable with `"Persist": 1` and a unique name for the patrol. Persistent AI continue from their last position with all acquired gear after server restarts. Persistence data is stored at:
   ```
   mpmissions\<mapname>\storage_x\expansion\ai\
   ```

5. **Loadout** — Recommended to spawn them with minimal gear and let them acquire items themselves through looting.

6. **Respawn and Despawn** — `RespawnTime` and `DespawnTime` settings work for all patrols. If respawn is disabled, they will respawn on the next server restart.

7. **Area Restrictions** — There is currently no way to restrict roaming AI to a specific area without custom mapping.

8. **Despawn Radius** — Set a very large despawn radius to keep roaming AI active when no players are nearby.

9. **Looting** — AI can get stuck in looting loops with each other. This may be addressed in future updates.

10. **Compatibility** — Works with different maps including Deer Isle and Chernarus.

---

## Configuration Tips

- Ensure `MinDist` and `MaxDist` are set sensibly.
- Patrol names must be unique for persistence to work.
- Spaces in names are allowed but may cause issues in some cases.
- A special Chernarus traversal file may be needed to help AI navigate around known map object bugs.

---

## Future Updates

Developers may make looting a separate option from roaming behavior in a future update.
