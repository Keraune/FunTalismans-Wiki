# HOCON (.conf) format

HOCON is a flexible format (Typesafe Config).

## Quick tips
- Use `=` (you can also use `:`).
- Lists without commas.
- Comments with `#` or `//`.

```hocon
vampire {
  id = "vampire"
  name = "&cVampire Talisman"
  material = "NETHER_STAR"
  glow = true
  lore = [
    "&7Line 1"
    "&7Line 2"
  ]
}
```
