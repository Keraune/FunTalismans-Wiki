# Creating a talisman

1) Create a `.conf` file inside the talismans folder.
2) Define the talisman section.

```hocon
vampire {
  id = "vampire"
  name = "&cVampire Talisman"
  material = "NETHER_STAR"
  rarityId = "epic"
  glow = true
  unbreakable = true
  lore = [
    "&7Steals life on hit."
  ]
}
```

3) Reload the plugin (see “Reload”).
