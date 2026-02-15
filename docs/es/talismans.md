---
title: Crear un Talismán
nav_order: 7
---

# Crear un Talismán

Los talismanes se definen en archivos `.conf` dentro de `plugins/FunTalismans/talismans/`.

El loader:
- Busca **recursivamente** archivos `.conf`.
- Por cada archivo, crea un talismán usando `talisman { ... }`.

Ejemplo mínimo:
```hocon
talisman {
  id: "example"
  name: "&aTalismán de Ejemplo"
  material: "DIAMOND"
  rarity: "common"
}
```

## Propiedades del talismán

> Muchos campos son opcionales. Si no están, se usan valores por defecto (según el parser).

### Identidad
- `id` (string) — identificador único del talismán.
- `name` (string) — nombre visible.
- `rarity` (string) — id de rareza.
- `custom_model_data` (int) — CustomModelData (si usas resourcepack).

### Item base
- `material` (string) — material Bukkit (`DIAMOND_SWORD`, `PAPER`, etc.).
- `glow` (bool) — brillo visual.
- `unbreakable` (bool) — irrompible.
- `disableEnchantGlow` (bool) — si quieres desactivar brillo por encantamientos.
- `keepItemOnDeath` (bool) — mantener al morir (si tu lógica lo usa).

### Lore / descripción
- `lore` (lista de strings)

### Visual / extra
- `texture` (string) — textura (según tu implementación).
- `color` (string) — color (ej: `#FFAA00` o formato soportado).
- `customModelData` (alternativo si tu config lo usa; el parser usa `custom_model_data`)

### Combate / atributos
- `damage` (int)
- `attributes` (lista) — atributos custom (ver tu sección de atributos).
- `flags` (lista) — item flags.
- `enchantments` (lista)
- `effects` (lista)

### NBT
- `nbt` (mapa) — clave/valor para NBT (según tu implementación).

### Durabilidad
- `maxDurability` (int)
- `durability` (int)
- `isDurabilityBasedOnUsage` (bool) — si el uso consume durabilidad.

### Configs especiales (objetos)
- `armorTrim` (Config)
- `dropSettings` (Config)
- `fireworkData` (Config)
- `instrumentData` (Config)
- `bookData` (Config)

### Stack
- `maxStack` (int)
- `useMaxStack` (bool)

### Módulos
- `consumable` (objeto) — habilita modo consumible (ver sección Consumibles).
- `throwable` (objeto) — habilita modo arrojable (ver sección Throwables).
- `rules` (objeto) — reglas del talismán (ver sección Reglas).

## Ejemplo más completo
```hocon
talisman {
  id: "miner"
  name: "&bMiner Talisman"
  material: "DIAMOND_PICKAXE"
  rarity: "epic"

  glow: true
  unbreakable: true
  lore: [
    "&7Aumenta tu eficiencia."
    "&7Funciona sólo en minas."
  ]

  custom_model_data: 1001

  rules {
    allowedWorlds: [ "world" ]
    blockedRegions: [ "spawn" ]
    denyActions { message: "&cNo puedes usarlo aquí." sound: "ENTITY_VILLAGER_NO" }
  }
}
```
