# Command cooldowns

Command cooldowns allow you to limit how often players can run particular commands.

For example, if you want to limit how often a player can `/feed` or go `/home`, simply add those commands to the config:

```yaml
command-cooldowns:
  feed: 10 # 10 seconds
  home: 70 # 1 minute 10 seconds
```

**Advanced users** are able to apply more control to their command matching by using wildcards. Wildcards are specified using asterisks '*'. For example, to match all commands that include the word `potato`, you would simply wrap the world potato in asterisks:

```yaml
command-cooldowns:
  '*potato*': 30
```

> _**Note:** Due to YAML's design, any command starting with * must be wrapped in quotation marks (single or double, ' ")._

For **highly technical users** who understand Regex (Regular Expressions), this feature also supports Regex. In order for EssentialsX to begin interpreting regex, the command must start with a caret '^'. Followed by the explicit regex pattern that EssentialsX should match.

```yaml
command-cooldowns:
  '^^ban([^ip])?( .*)?': 30 # match any ban command that isn't `banip`.
```

> _**Note:** The leading caret is not part of the regex and is simply removed when parsing the regex. For example, `'^ban([^ip])?( .*)?'` actually becomes `'ban([^ip])?( .*)?'`._

> _**Note:** If a plugin command starts with a caret e.g. `^mycommand`, then the caret must be escaped using a blackslash '\' to prevent EssentialsX from interpreting the command as Regex._

## Persistent cooldowns

By default, EssentialsX will store all existing cooldowns across server sessions. This means when the server shuts down the player cooldowns will be saved and loaded for the next startup. This is especially useful for cooldowns that last any more than a few minutes.

However, this feature can be disabled, in which case EssentialsX will store cooldowns only until the server shuts down. This will reset all cooldowns when the server next starts up.

To disable command cooldown persistence, change `command-cooldown-persistence` to `false` in `config.yml`:

```yaml
command-cooldown-persistence: false
```

## Bypassing cooldowns

Users can bypass all command cooldowns if they have the `essentials.commandcooldowns.bypass` permission. This is useful for admins.
