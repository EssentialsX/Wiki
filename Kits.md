# Kits

EssentialsX supports a wide range of kit functionality. Kits can contain anything from stacks of simple items, to complicated 'unique' items, utilising advanced item meta, enchantments, and item lore.

EssentialsX also supports commands within kits, permission based kits, kit signs, new player kits, and kit cooldowns to prevent abuse.

## Creating a Kit

Kits can be manually defined within the `Essentials/kits.yml` file, or created in-game using the `/createkit` convenience command. 

Due to server limitations, `/createkit` cannot capture all existing item data like NBT tags. However, NBT can still be manually applied to kit items by copying the desired NBT string into the `kits.yml` file.

### Kit delay (cooldowns)

You can set a delay (or cooldown) on each kit to prevent abuse. This delay is defined in **seconds**. A delay of `3600` would prevent the kit from being used more than once per hour.

If you want no delay on the kit, use `0` as the delay value. If you want the kit to be one-time use, use `-1` as the delay value.

If a player has the permission `essentials.kit.exemptdelay`, the kit delay will not be checked when they redeem a kit.

### Using /createkit

To create a new kit with `/createkit`, fill your inventory with the items you wish to include in your kit and run `/createkit <name> <delay>`, where `<name>` is the name of the new kit and `<delay>` is the delay between kit redemptions.

For example, to create a new kit called `starter` with a delay of 5 minutes (300 seconds), the command would be `/createkit starter 300`.

As mentioned above, `/createkit` can't capture all of the information that an item may hold, especially when attempting to include custom items from other plugins in kits. When this happens, it may be necessary to manually define the kit inside `kits.yml` instead.

**Plugin Developers:** You can use EssentialsX's [ItemResolver API](https://jd-v2.essentialsx.net/net/ess3/api/iitemdb.itemresolver) ... etc information about that here

### Using kits.yml

Manually defined EssentialsX kits support a number of different elements. The format for defining kits is fairly simple:
```yaml
kits:
  <kit name>:
    delay: <delay in seconds between usage>
    items:
      - <item name> <amount> <meta>
      - <item name> <amount> {NBT}
      - /command ... {USERNAME} ...
```
EssentialsX kits support items using optional EssentialsX item meta (example 1), items using vanilla NBT tags (example 2), and executing commands as console upon kit redemption (example 3).

The `{USERNAME}` tag used above is part of EssentialsX's [Keywords list](...), and will be replaced with the username of the player redeeming the kit. All keywords in the list can be used as part of kit item definitions.

**Please note that EssentialsX meta and NBT tags are not compatible. Only one of the two can be used on any given item.**

Examples:

```yaml
kits:
  tools:
    delay: 10
    items:
      - stonesword 1
      - stoneshovel 1
      - stonepickaxe 1
      - stoneaxe 1
  dtools:
    delay: 600
    items:
      - dpickaxe 1 efficiency:1 durability:1 fortune:1 name:&4Gigadrill lore:The_drill_that_&npierces|the_heavens
      - dshovel 1 digspeed:3 name:Dwarf lore:Diggy|Diggy|Hole
      - lhelm 1 color:255,255,255 name:Top_Hat lore:Good_day,_Good_day
      - daxe:780 1
      - /broadcast {USERNAME} just got some fancy tools!
  notch:
    delay: 6000
    items:
      - playerhead 1 player:Notch
  color:
    delay: 6000
    items:
      - writtenbook 1 title:&4Book_&9o_&6Colors author:KHobbits lore:Ingame_color_codes book:Colors
  bone:
    delay: -1
    items:
      - bone 1 {Enchantments:[{id:"minecraft:knockback",lvl:3s}]}
```
The `tools` kit will give the player a set of stone tools.

The `dtools` kit will give the player some enchanted tools and armor with custom names and lore using EssentialsX item meta, a diamond axe with damage value `780`, and will execute the broadcast command from console replacing `{USERNAME}` with the player's username.

The `notch` kit will give the player a player skull with the skull texture of player `Notch`.

The `color` kit will give the player a book of colors, specified using EssentialsX's book meta system. 

Finally, the `bone` kit will give the player a bone enchanted with Knockback 3 using NBT tags (1.16 format). 

## Removing a Kit

Kits can be removed by manually deleting the relevant section within `kits.yml`, or by using the `/delkit <name>` convenience command, where `<name>` is the name of the kit to be deleted.

## Using a Kit

After a kit has been created, it can be redeemed in-game using `/kit <name>`, where `<name>` is the name of the kit. Players require permissions in order to be able to use `/kit` and to redeem specific kits.

Kits can also be forcibly redeemed for players by using `/kit <name> <username>`, where `<name>` is the name of the kit and `<username>` is the username of the player the kit will be given to. This requires the executor to have the `essentials.kit.others` permission.

### Kit Permissions

To give your players permission to use kits, you must first grant them the base permission `essentials.kit`. From there, kits can be selectively granted using the `essentials.kits.<kitname>` permission. 

For example, if you want a player to be able to redeem the `starter` kit, the player must have both the `essentials.kit` and `essentials.kits.starter` permissions.

Please note that while `essentials.kit` grants players the ability to use `/kit`, the permission is not required for kit signs.

| Permission                    | Description                                                                   |
|-------------------------------|-------------------------------------------------------------------------------|
| `essentials.kit`              | Allows player to use `/kit`                                                   |
| `essentials.kits.<kitname>`   | Allows player to use `/kit <kitname>`                                         |
| `essentials.kit.others`       | Allows player to grant kit to another player with `/kit <kitname> <username>` |
| `essentials.kit.exemptdelays` | Allows player to bypass kit delay checks                                      |

## Extra Features

A number of other EssentialsX features integrate with the kits system.

### Kit Costs

...

### New Player Kits

...
