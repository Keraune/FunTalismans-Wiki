# Formato HOCON (.conf)

HOCON es un formato flexible (Typesafe Config).

## Tips rápidos
- Usa `=` (también sirve `:`).
- Listas sin comas.
- Comentarios con `#` o `//`.

```hocon
vampire {
  id = "vampire"
  name = "&cVampire Talisman"
  material = "NETHER_STAR"
  glow = true
  lore = [
    "&7Linea 1"
    "&7Linea 2"
  ]
}
```
