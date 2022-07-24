---
title: 'Feature: Signs'
wip: true
---

# Signs (WIP)

EssentialsX features several signs which can be created by staff or players on your servers.

## Configuration

To enable EssentialsX signs on your server, you need to enable each type of sign in `config.yml`. You can do this by uncommenting the signs you want to enable under `enabledSigns` (removing the `#` before the line).

The following example enables the `[Balance]`, `[Trade]`, `[Free]`, `[Warp]` and `[Disposal]` signs, as well as allowing players to use colours on signs (more info on this [below](#coloured-text)).

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

TODO explain create/use/destroy perms

## Sign types

### Buy

TODO buy sign examples

`[Buy]` signs allow players to buy items from the server for money (TODO: or items? check this).

### Sell

TODO sell sign examples

`[Sell]` signs allow players to sell their items to the server for money (TODO: again check for items).

### Trade

TODO trade sign examples

`[Trade]` signs allow players to set up their own shops. Players can create trade signs to buy, sell or exchange different items, and then other players can right-click these signs to trade with them.

### Free

TODO free sign examples

`[Free]` signs allow players to claim free items from the server.

### Warp

TODO warp sign examples

`[Warp]` signs allow players to teleport to warps. TODO explain groups nonsense

### Kit

TODO kit sign examples

`[Kit]` signs allow players to claim kits.

### Mail

TODO mail sign examples

`[Mail]` signs allow players to check their mails.

### Enchant

TODO enchant sign examples

`[Enchant]` signs allow players to enchant items they are holding with a given enchantment.

### Gamemode

TODO gamemode sign examples

`[Gamemode]` signs allow players to change their gamemode to the gamemode on the sign.

### Heal

<KitCard>

<KitLevel>

<DocsSign line1="[Heal]" line2="[Cost]"></DocsSign>

<DocsSign :line1="{ text: '[Heal]', highlight: 'valid' }"></DocsSign>

<DocsSign :line1="{ text: '[Heal]', highlight: 'valid' }" line2="$1200"></DocsSign>

</KitLevel>

</KitCard>

Heal signs allow players to heal themselves. You can optionally charge players for using these signs by adding a cost on the second line.

### Info

TODO info sign example

TODO info sign explanation

### Spawnmob

TODO spawnmob sign example

TODO spawnmob sign explanation

### Repair

TODO repair sign example

TODO repair sign explanation

### Time

TODO time sign example

TODO time sign explanation

### Weather

TODO weather sign example

TODO weather sign explanation

### Disposal

<KitCard>

<KitLevel>

<DocsSign :line1="{ text: '[Disposal]', highlight: 'valid' }"></DocsSign>

<DocsSign :line1="{ text: '[Disposal]', highlight: 'valid' }" line2="Rubbish Bin"></DocsSign>

</KitLevel>

</KitCard>

Disposal signs allow players to dispose of items they no longer need. Right-click on the sign to open the disposal inventory. Any items placed in this inventory will be deleted as soon as the inventory is closed.

You can optionally add a custom title for the disposal inventory on the second line.

### Crafting signs

EssentialsX has signs for the various crafting stations available in the game. Note that most of these will only work if your server is running Paper.

<KitCard>

<div class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 grid-flow-row gap-4 justify-items-center">

<DocsSign :line1="{ text: '[Anvil]', highlight: 'valid' }"></DocsSign>

<DocsSign :line1="{ text: '[Cartography]', highlight: 'valid' }"></DocsSign>

<DocsSign :line1="{ text: '[Grindstone]', highlight: 'valid' }"></DocsSign>

<DocsSign :line1="{ text: '[Loom]', highlight: 'valid' }"></DocsSign>

<DocsSign :line1="{ text: '[Smithing]', highlight: 'valid' }"></DocsSign>

<DocsSign :line1="{ text: '[Workbench]', highlight: 'valid' }"></DocsSign>

</div>

</KitCard>

## Coloured text

You can give players the ability to use `&` colour codes on signs by enabling `color` in the config.

TODO explain and link to colour perms
