---
title: Recarga en tiempo real
nav_order: 11
---

# Recarga en tiempo real

FunTalismans tiene un sistema de recarga para:
- `config.conf`
- rarezas
- talismanes
- y sus módulos (rules/consumable/throwable)

## Recomendación
1. Edita el `.conf`
2. Ejecuta el comando de recarga (o el método de recarga que uses)
3. Prueba el talismán

## Consejo
Si algo falla al recargar:
- revisa consola por errores de parseo
- valida que el HOCON esté bien cerrado (llaves `{}` y listas `[]`)

> La recarga es una de las ventajas principales: iteras sin reiniciar.
