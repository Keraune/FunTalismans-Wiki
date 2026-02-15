---
title: Reglas (rules)
nav_order: 6
---

# Reglas (rules)

Las `rules` sirven para limitar **dónde/cuándo** funciona un talismán, consumible o throwable.

## Estructura general
Las reglas se interpretan como un **AND** por defecto:
```hocon
rules {
  world: "world"
  gamemode: "SURVIVAL"
  permission: "funtalismans.use"
}
```

## Reglas disponibles
- `if`: condición textual (según tu implementación interna)
- `world`: nombre del mundo
- `gamemode`: SURVIVAL / CREATIVE / ADVENTURE / SPECTATOR
- `permission`: permiso requerido
- `region`: región o lista de regiones (WorldGuard)
- Filtros mejorados:
  - `allowedWorlds` / `blockedWorlds`
  - `allowedRegions` / `blockedRegions`
  (también soporta kebab-case: `allowed-worlds`, etc.)

## Wrappers lógicos

### AND explícito
```hocon
rules {
  and: [
    { world: "world" }
    { permission: "funtalismans.use" }
  ]
}
```

### OR
```hocon
rules {
  or: [
    { world: "world" }
    { world: "world_nether" }
  ]
}
```

También existe `or { ... }` donde cada clave es una opción.

### ONEOF (elige una opción y aplica acciones locales)
```hocon
rules {
  oneof: [
    {
      permission: "vip"
      actions { message: "&aEres VIP" }
    }
    {
      permission: "default"
      actions { message: "&7Modo normal" }
    }
  ]
}
```

## denyActions (mensaje/sonido al negar)
```hocon
rules {
  denyActions {
    message: "&cNo puedes usar esto aquí."
    sound: "ENTITY_VILLAGER_NO"
  }
}
```
