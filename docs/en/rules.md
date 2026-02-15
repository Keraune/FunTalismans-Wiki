---
title: Rules
nav_order: 6
---

# Rules (rules)

Rules limit where/when a talisman works.

Default behavior is **AND** of keys:
```hocon
rules {
  world: "world"
  gamemode: "SURVIVAL"
  permission: "funtalismans.use"
}
```

Supported:
- `if`, `world`, `gamemode`, `permission`, `region`
- `allowedWorlds/blockedWorlds`, `allowedRegions/blockedRegions`
- wrappers: `and`, `or`, `oneof`
- `denyActions { message, sound }`
