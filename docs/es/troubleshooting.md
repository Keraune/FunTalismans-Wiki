---
title: Solución de problemas
nav_order: 12
---

# Solución de problemas

## “No contiene plugin.yml”
Si Paper dice que el jar no contiene `plugin.yml`:
- Asegúrate de que tu build **no lo esté excluyendo**.
- En `maven-shade-plugin`, **NO excluyas** tu `plugin.yml`.
  - Si quieres evitar `plugin.yml` ajeno, usa filters más específicos, no un exclude general.

## VerifyError / stackmap frames
Si aparece un error tipo `VerifyError: Expecting a stackmap frame...`:
- Asegúrate de usar ProGuard con configuración segura:
  - `-dontoptimize`
  - `-dontshrink`
  - `-dontpreverify` (en plugins suele ayudar)
- Confirma que estás ofuscando el jar final (shaded) y con librerías correctas.

## “No carga talismanes”
- Revisa que los `.conf` estén dentro de `plugins/FunTalismans/talismans/`
- El loader solo lee archivos `.conf` (y recorre subcarpetas).
- Asegúrate de que cada archivo tenga:
  - `talisman { id: "..." ... }`

## Colores / sonidos inválidos
- Usa `#RRGGBB` para colores si tu parser espera hex.
- Para sonidos, usa nombres válidos de Bukkit/Paper.
