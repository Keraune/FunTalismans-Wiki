---
title: HOCON format
nav_order: 3
---

# HOCON (Typesafe Config)

FunTalismans uses **HOCON** (Typesafe Config).

## Quick examples

Object:
```hocon
talisman {
  name: "Example"
  material: DIAMOND
  glow: true
}
```

List:
```hocon
lore: [
  "&7Line 1"
  "&bLine 2"
]
```

Reuse:
```hocon
base = { glow: true unbreakable: true }
a = ${base} { name: "A" material: STICK }
```
