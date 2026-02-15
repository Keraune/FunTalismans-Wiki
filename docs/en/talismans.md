---
title: Create a Talisman
nav_order: 7
---

# Create a Talisman

Create `.conf` files inside `plugins/FunTalismans/talismans/`.

Minimal:
```hocon
talisman {
  id: "example"
  name: "&aExample"
  material: "DIAMOND"
  rarity: "common"
}
```

## Main properties (from the parser)
- Identity: `id`, `name`, `rarity`, `custom_model_data`
- Base item: `material`, `glow`, `unbreakable`, `disableEnchantGlow`, `keepItemOnDeath`
- Lore: `lore`
- Extra: `texture`, `color`
- Combat: `damage`, `attributes`, `flags`, `enchantments`, `effects`
- NBT: `nbt`
- Durability: `maxDurability`, `durability`, `isDurabilityBasedOnUsage`
- Special configs: `armorTrim`, `dropSettings`, `fireworkData`, `instrumentData`, `bookData`
- Stack: `maxStack`, `useMaxStack`
- Modules: `consumable`, `throwable`, `rules`
