---
title: Formato HOCON
nav_order: 3
---

# Formato HOCON (Tiposafe Config)

FunTalismans usa **HOCON**, un formato de configuración muy flexible (de Typesafe Config).

## Diferencias vs YAML
- No necesitas `:` para todo.
- Puedes usar `{ }` para bloques.
- Soporta comentarios con `#` y `//`.
- Las comillas son opcionales en muchos casos.

## Ejemplos rápidos

### Objetos (bloques)
```hocon
talisman {
  name: "Mi Talismán"
  material: DIAMOND
  glow: true
}
```

### Listas
```hocon
lore: [
  "&7Línea 1"
  "&bLínea 2"
]
```

### Strings sin comillas (cuando no hay espacios)
```hocon
material: DIAMOND_SWORD
```

### Herencia / repetición (útil para copiar estructuras)
```hocon
base = {
  glow: true
  unbreakable: true
}

talismanA = ${base} { name: "A" material: STICK }
talismanB = ${base} { name: "B" material: BLAZE_ROD }
```

### Duraciones (si el campo lo soporta)
En varias secciones (consumables/throwables) se soportan tiempos tipo:
`"500ms"`, `"2s"`, `"3m"`, `"1h"`.
