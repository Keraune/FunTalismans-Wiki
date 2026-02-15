---
title: Throwables
nav_order: 9
---

# Arrojables (throwable)

Un talismán puede lanzar un proyectil si define `throwable { ... }`.

Ejemplo básico:
```hocon
talisman {
  id: "ice_orb"
  name: "&bOrbe de Hielo"
  material: "SNOWBALL"

  throwable {
    enabled: true
    consumeItem: true
    cooldown: "3s"

    projectile {
      type: "SNOWBALL"
      velocity: 1.5
      gravity: true
      hitRadius: 5.0
      maxLife: "8s"
    }

    castSound { name: "ENTITY_SNOWBALL_THROW" volume: 1 pitch: 1 }
    impactSound { name: "BLOCK_GLASS_BREAK" volume: 1 pitch: 1 }

    targets {
      includePlayers: true
      includeMobs: true
      includeSelf: false
    }
  }
}
```

## Campos principales
- `enabled` (bool)
- `consumeItem` (bool)
- `cooldown` (time)

### projectile
- `type` (string) — tipo de entidad/proyectil (por nombre)
- `velocity` (double)
- `gravity` (bool)
- `hitRadius` (double)
- `maxLife` (time)

### castSound / impactSound
- `name`, `volume`, `pitch`, `category`, `broadcastRange`

### particles / effects
El throwable comparte gran parte de la lógica de **particles** y **effects** con consumables.
