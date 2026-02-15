---
title: Rarezas
nav_order: 5
---

# Rarezas (rarities)

Las rarezas se cargan desde `rarities/rarities.conf`.

Cada rareza necesita un `id` y puede definir:
- `displayName` (nombre visible)
- `color` (hex tipo `#FFAA00`)
- `weight` (peso/probabilidad o prioridad, según tu uso)
- `modelData` (CustomModelData por defecto)
- `lorePrefix` (prefijo decorativo para lore)
- `disableEnchantGlow` (si quieres evitar brillo por encantamiento)
- `dropSettings` (si aplicas drops por rareza)

Ejemplo (idea):
```hocon
rarities {
  common {
    id: "common"
    displayName: "&fComún"
    color: "#FFFFFF"
    weight: 50
  }

  epic {
    id: "epic"
    displayName: "&dÉpico"
    color: "#FF55FF"
    weight: 10
  }
}
```

> Nota: FunTalismans lee el bloque `rarities` y construye un mapa por `id`.
