---
title: Consumibles
nav_order: 8
---

# Consumibles (consumable)

Un talismán puede actuar como **consumible** si define el bloque `consumable { ... }`.

Ejemplo básico:
```hocon
talisman {
  id: "heal_pulse"
  name: "&aPulso de Curación"
  material: "PAPER"

  consumable {
    enabled: true
    consumeItem: true
    radius: 6
    cooldown: "10s"

    targets {
      includePlayers: true
      includeMobs: false
      includeSelf: true
    }

    sound {
      name: "ENTITY_EXPERIENCE_ORB_PICKUP"
      volume: 1.0
      pitch: 1.0
      broadcastRange: 20
      category: "MASTER"
    }

    particles {
      enabled: true
      particle { name: "HAPPY_VILLAGER" count: 30 speed: 0.1 radius: 2 upY: 1.0 mode: "sphere" }
    }

    effects {
      self: [
        { type: "REGENERATION" amplifier: 1 duration: "5s" }
      ]
    }
  }
}
```

## Campos principales (según el parser)
- `enabled` (bool)
- `consumeItem` (bool) — si consume el ítem al usar.
- `radius` (double) — radio de aplicación.
- `cooldown` (time) — cooldown (`"10s"`, `"500ms"`, etc.)

### targets
- `includePlayers` (bool)
- `includeMobs` (bool)
- `includeSelf` (bool)
- `rules` (objeto rules)

### sound
- `name` (string Sound)
- `volume` (double)
- `pitch` (double)
- `category` (SoundCategory)
- `broadcastRange` (double)

### particles
- `enabled` (bool)
- `particle { ... }` o `particle-double { ... }`
  - `name`, `color`, `size`, `start-radius`, `speed`, `count-radius`, `upY`, `mode`
  - `volume { layers step jitterRadius jitterY jitterAngle jitterDir }`

### effects
Soporta:
- `caster` / `self` (lista de efectos)
- `cleanse` (limpieza de efectos)
- `ranges` (rangos con listas de efectos y extras como `ignite` / `freeze`)
- `groups` (grupos nombrados con `rules` y `ranges`)

> Los consumibles son la parte más “compleja”. Empieza simple y luego añade ranges/grupos.
