---
title: Consumables
nav_order: 8
---

# Consumables

Enable with:
```hocon
consumable { enabled: true }
```

Core fields:
- `consumeItem`, `radius`, `cooldown`
- `targets { includePlayers includeMobs includeSelf rules }`
- `sound { name volume pitch category broadcastRange }`
- `particles { enabled particle { ... } }`
- `effects { self/caster, cleanse, ranges, groups }`
