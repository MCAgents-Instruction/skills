# PaperMC Technical Standards

When working within the `platforms:papermc` submodule, strictly adhere to the following rules.

## 1. Task Scheduling & Concurrency

- Utilize the standard Paper scheduling API for task management and scheduling.
- Ensure all heavy computations, API calls, and database interactions run asynchronously off the main server thread.
- Synchronize with the main thread only when interacting with thread-unsafe Bukkit/Paper API methods.

### Never use Bukkit.getScheduler()

### Player-Specific Tasks

```java
player.getScheduler().run(plugin, task -> { ... }, null);
```

### Asynchronous Tasks

```java
plugin.getServer().getAsyncScheduler().runNow(plugin, task -> { ... });
```

## 2. UI & Messages

- ALWAYS use `Component.translatable(key, defaultText)` via the Adventure API for player messages.
- Use `NamedTextColor`.

## 3. Event Handling

- Register events securely.
- Use `EventPriority.MONITOR` with `ignoreCancelled = true` for observation-only logic.
