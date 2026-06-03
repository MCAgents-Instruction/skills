# GUI, Items, and Serialization

## 1. NBT Data & PersistentDataContainer

- Use `NamespacedKey` and `PersistentDataContainer`.
- Verify `item.hasItemMeta()` before access.

## 2. Custom Player Heads (SkullMeta)

Use `PlayerProfile` and Base64 textures.

### Example

```java
PlayerProfile profile = Bukkit.createProfile(UUID.randomUUID());
profile.setProperty(new ProfileProperty("textures", base64TextureString));
skullMeta.setPlayerProfile(profile);
```

## 3. Item Serialization

Use ItemStackSerializer.

```java
ItemStackSerializer.serialize(item);
ItemStackSerializer.deserialize(base64);
```

## 4. GUI Management

- GUIs should use `InventoryClickEvent`.
- Always call `event.setCancelled(true)`.
- Placeholder slots should use stained glass panes with `Component.empty()`.
