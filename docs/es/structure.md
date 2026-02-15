---
title: Estructura de carpetas
nav_order: 4
---

# Estructura de carpetas

Ruta típica:
```
plugins/
  FunTalismans/
    config.conf
    rarities/
      rarities.conf
    talismans/
      (aquí tus talismanes .conf)
```

## Carpetas anidadas
Dentro de `talismans/` puedes crear **infinitas carpetas y subcarpetas** para organizarte.

Ejemplo recomendado:
```
talismans/
  common/
    starter.conf
  combat/
    lifesteal.conf
    crit/
      crit_basic.conf
      crit_advanced.conf
  utility/
    miner.conf
    farmer.conf
```

El loader recorre **recursivamente** la carpeta `talismans/` y carga cualquier archivo `.conf`.
