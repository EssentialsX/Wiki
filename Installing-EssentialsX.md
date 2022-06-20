# Installing EssentialsX

## Preparations

First of all, make sure you're running a supported Minecraft server platform. EssentialsX officially supports CraftBukkit, Spigot and Paper. We strongly recommend using [**Paper**](https://papermc.io) as it contains many performance improvements over Spigot and CraftBukkit, especially on recent Minecraft versions.

> _**Note:** Some server software, such as forks of Paper or Forge-Bukkit hybrid servers, can cause issues with EssentialsX. The EssentialsX team cannot help with any issues that arise on Paper forks or Forge-Bukkit hybrid servers. If you encounter an issue while using alternative server software, please reproduce the issue on a standard Paper server before reporting it to us._

You will also need to install [**Vault**](https://www.spigotmc.org/resources/vault.34315/) to allow EssentialsX to talk to certain other installed plugins. Without Vault, prefixes, suffixes and group-related features won't work, and other plugins won't be able to interact with EssentialsX's economy features.

If you don't already have a permissions plugin, we strongly recommend that you set up [**LuckPerms**](https://luckperms.net) on your server. LuckPerms is an easy-to-use plugin that allows you to manage groups (ranks), permissions, prefixes and suffixes for your players. Even on small private servers, LuckPerms is an invaluable tool for managing your server.

## Downloading EssentialsX

You can download EssentialsX from the official [downloads page](https://essentialsx.net/downloads.html). You can choose either the **stable build** which has been tested thoroughly, or **development builds** which include the latest features and bug fixes.

### Optional EssentialsX addons

The only jar needed for most of EssentialsX's features to work is the main `EssentialsX` jar. This contains most of the core features most servers will need.

Some of EssentialsX's other features have been split off into optional addon plugins. These are also available on the official downloads page. See the [[Module-Breakdown|Module Breakdown]] page for more information on what each addon does.

> _**Note:** There are some unofficial addons for EssentialsX on sites such as SpigotMC which have not been developed by the EssentialsX team. The EssentialsX team cannot guarantee unofficial addons will work correctly, and we cannot provide help for these addons. If you choose to install unofficial addons, please contact the developers of those plugins for help with them._

> _**Note:** When downloading EssentialsX, you **must** ensure that you install the same versions of EssentialsX and official addons. You will likely encounter issues if you run different versions of EssentialsX and its addons._

## Adding EssentialsX to your server

Once you've decided which EssentialsX modules you need, copy the required `.jar` files into the `plugins/` directory.

Finally, restart your server. EssentialsX will create configuration files under `plugins/Essentials/` when it starts up, and will upgrade old Essentials data if needed.

## Optional: Configuring EssentialsX

EssentialsX comes with sensible defaults for all of its settings. However, you may wish to change how certain EssentialsX features work.

You can edit the `plugins/Essentials/config.yml` file to customise EssentialsX to your liking. Most settings are explained in comments, so be sure to read the options carefully.

Once you've made your changes to the `config.yml` file, save it, then run `ess reload` in your server console or `/ess reload` in-game. EssentialsX will apply your changes instantly.

> _**Note:** It may be tempting to use a plugin manager (such as PlugMan or ServerUtils) to "reload" EssentialsX. However, reloading using a plugin manager is dangerous and is likely to break certain parts of EssentialsX. If you need to reload EssentialsX, you should run `/ess reload` or restart your server._

> _**Note:** Some settings might require a full restart of your server to apply. If this is the case, it will usually be documented in a comment in the `config.yml` file. Again, do not use a plugin manager to force this - it will likely break EssentialsX and require a restart to fix._
