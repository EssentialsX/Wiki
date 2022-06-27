---
title: 'Feature: Signs'
wip: true
---

# Signs (WIP)

EssentialsX features several signs which can be created by staff or players on your servers.

## Configuration

To enable EssentialsX signs on your server, you need to enable each type of sign in `config.yml`. You can do this by uncommenting the signs you want to enable under `enabledSigns` (removing the `#` before the line).

For example, this example enables the `[Balance]`, `[Trade]`, `[Free]`, `[Warp]` and `[Disposal]` signs, as well as allowing players to use colours on signs (more info on this [below](#coloured-text)).

```yaml
enabledSigns:
  - color
  - balance
  #- buy
  #- sell
  - trade
  - free
  - warp
  #- kit
  #- mail
  #- enchant
  #- gamemode
  #- heal
  #- info
  #- spawnmob
  #- repair
  #- time
  #- weather
  #- anvil
  #- cartography
  - disposal
  #- grindstone
  #- loom
  #- smithing
  #- workbench
```

## Permissions

TODO

## Sign types

### Buy

### Sell

### Trade

### Free

### Warp

### Kit

### Mail

### Enchant

### Gamemode

### Heal

### Info

### Spawnmob

### Repair

### Time

### Weather

### Anvil

### Cartography

### Disposal

<DocsSign :line1="{ text: '[Disposal]', highlight: 'valid' }" line2="" line3="" line4=""></DocsSign>

Disposal signs allow players to dispose of items they no longer need. Right-click on the sign to open the disposal inventory. Any items placed in this inventory will be deleted as soon as the inventory is closed.

### Grindstone

### Loom

### Smithing

<br>
<br>
<br>
<br>
<br>



## Coloured text

You can give players the ability to use `&` colour codes on signs by enabling `color` in the config.
