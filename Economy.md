# EssentialsX Economy
The built in economy API will redirect to any other detected economy system such as vault. This means you can use EssEco api as a economy api instead of vault if your plugin is dependent on Essentials.

## Commands
There are a number of commands for use in-game, including but not limited to:
   - /eco, /economy: Allows you to take, give, or reset a player's money.
   - /sell: Sells an item and amount at the price specified in the worth.yml.
   - /balance, /bal, /money: Displays the current balance of a player.
   - /baltop, /balancetop: Displays a list of the richest people.
   - /pay: Pays a specified player from your balance.

## Configuration
There are a number of different options related to the internal economy system which can be found in the `config.yml`.
Most of the config options are explained adequately in the comments:

```yml
# Defines the balance with which new players begin. Defaults to 0.
starting-balance: 0

# Defines the cost to use the given commands PER USE.
# Some commands like /repair have sub-costs, check the wiki for more information.
command-costs:
  # /example costs $1000 PER USE
  #example: 1000
  # /kit tools costs $1500 PER USE
  #kit-tools: 1500

# Set this to a currency symbol you want to use.
# Remember, if you want to use special characters in this document, 
# such as accented letters, you MUST save the file as UTF-8, not ANSI.
currency-symbol: '$'

# Enable this to make the currency symbol appear at the end of the amount rather than at the start.
# For example, the euro symbol typically appears after the current amount.
currency-symbol-suffix: false

# Set the maximum amount of money a player can have.
# The amount is always limited to 10 trillion because of the limitations of a java double.
max-money: 10000000000000

# Set the minimum amount of money a player can have (must be above the negative of max-money).
# Setting this to 0, will disable overdrafts/loans completely.  Users need 'essentials.eco.loan' perm to go below 0.
min-money: -10000

# Enable this to log all interactions with trade/buy/sell signs and sell command.
economy-log-enabled: false

# Enable this to also log all transactions from other plugins through Vault.
# This can cause the economy log to fill up quickly so should only be enabled for testing purposes!
economy-log-update-enabled: false
```

EssentialsX adds the ability to specify the minimum transaction amount to prevent the dreaded microtransactions:

```yml
# Minimum acceptable amount to be used in /pay.
minimum-pay-amount: 0.001
```

EssentialsX adds currency format to improve the localization. You may uncomment the `currency-symbol-format-locale` to use our preformatted styles or uncomment `currency-format` and create your own:

```yml
# The format of currency, excluding symbols. See currency-symbol-format-locale for symbol configuration.
#
# "#,##0.00" is how the majority of countries display currency.
#currency-format: "#,##0.00"

# Format currency symbols. Some locales use , and . interchangeably.
# Some formats do not display properly in-game due to faulty Minecraft font rendering.
#
# For 1.234,50 use de-DE
# For 1,234.50 use en-US
# For 1'234,50 use fr-ch
#currency-symbol-format-locale: en-US
```

#### Permissions
[Permissions for commands can be found here](https://essinfo.xeya.me/permissions.html) (Community maintained list)

Important permissions include `essentials.eco` and  `essentials.pay`.

## Signs & Shops
Signs may be used to create shops where players can buy and sell items/blocks to and from the server in exchange for money. 

#### Signs
To create a sign, ensure that you have the `signs.create.trade` permission and that you have uncommented `- buy` and `- sell` under `enabledSigns:` in the config.yml
Signs follow the format:
```
[Buy]/[Sell]
Quantity
[Material](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)
Cost
```
###### Example:
What is typed into the sign UI | Essentials will turn the `[Buy]`/`[Sell]` blue when done sucessfully
:-------------------------------:|:-------------------------------:
| ![Image of Sign Creation UI](/images/EcoBuySignUI.png?v=4&s=360) | ![Image of Completed Buy/Sell Signs](/images/EcoBuySellSign.png?v=4&s=400) |

The sign will allow players with the `signs.use.buy` permission to purchase 1 dirt for $1 when left clicked. If `[Buy]` is changed to `[Sell]` and the player has the respective permission, the player may sell 1 dirt to the server in exchange for $1.
#### Shops
To prevent players exploiting the the economy by purchasing from the server using a buy sign and `/sell`, only create Buy signs at or above the rates found in `worth.yml`.
A good server shop typically offers bulk Sell signs at better rates than the `worth.yml` to encourage players to use the shop over `/sell`.
Alternatively, if players aren't given the `essentials.sell` permission, their only option is to trade between players or go to the shop.
