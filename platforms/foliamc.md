# FoliaMC Technical Standards

When working within the `platforms:foliamc` submodule, strictly adhere to the following rules.

## 1. Regionalized Threading (CRITICAL)

- Strictly utilize concurrent programming and respect Region constraints.

### No Global Schedulers

Methods like `Bukkit.getScheduler()` do not exist or may throw exceptions.

### Entity / Player Tasks

- Use Global Threading Entity Schedules for all entity-related tasks.
- Always use the entity scheduler.

```java
player.getScheduler().run(plugin, task -> { ... }, null);
```

### Location / Chunk Tasks

Always use the RegionScheduler.

```java
Bukkit.getRegionScheduler().run(plugin, location, task -> { ... });
```

### Global Async Tasks

Use AsyncScheduler for world-independent tasks.

```java
Bukkit.getAsyncScheduler().runNow(plugin, task -> { ... });
```

## 2. UI & Messages

- STRICTLY use the Adventure API (`Component.translatable(...)` and `NamedTextColor`) for player messages (similar to PaperMC).

## 3. State Integrity

- Do not share mutable state across regions without thread-safe collections.
- Use asynchronous teleport APIs when moving entities across regions.
