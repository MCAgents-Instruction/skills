# Database & State Management

The project uses a dual-layer architecture (RAM Cache + Persistent Database).

## 1. Asynchronous Database Access

- All database interactions MUST go through a provider or manager.
- All fetches and updates return `CompletableFuture`.
- Never block the main thread with `.join()` or `.get()`.

### Example

```java
IdentityProvider.instance.getProperties(uuid).thenAccept(optProps -> {
    // Handle result
});
```

## 2. RAM Caching (Optimistic Updates)

Update RAM cache synchronously first, then database asynchronously.

### Example

```java
IdentityManager.updateProperties(uuid, newProps);
IdentityProvider.instance.updateProperties(uuid, newProps);
```

## 3. Connection Pooling

Use HikariCP for pooling.

Ensure connections are properly closed or returned to the pool.
