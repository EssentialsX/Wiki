# Color Permissions

<!-- alternative title: Colo_u_r Permissions -->

EssentialsX includes permissions that let you control the individual formatting codes players can use in some commands.

This works for the following:
* Sending a PM with `/msg`: `essentials.msg.<suffix>`
* Sending mails with `/mail`: `essentials.mail.<suffix>`
* Setting your own nickname with `/nick`: `essentials.nick.<suffix>`
* Sending chat messages **(requires EssentialsX Chat)**: `essentials.chat.<suffix>`
* Editing a sign with `/editsign`: `essentials.editsign.<suffix>`
* Colors on signs **(requires color signs to be enabled)**: `essentials.signs.<suffix>`

Below is a list of valid permissions suffixes:

| Suffix           | Color codes                                       |
|------------------|---------------------------------------------------|
| `color` (group)  | `&0 &1 &2 &3 &4 &5 &6 &7 &8 &9 &a &b &c &d &e &f` |
| `format` (group) | `&l &m &n &o &r`                                  |
| `magic` (group)  | `&k`                                              |
| `rgb`            | `&#RRGGBB`                                        |
| `black`          | `&0`                                              |
| `dark_blue`      | `&1`                                              |
| `dark_green`     | `&2`                                              |
| `dark_aqua`      | `&3`                                              |
| `dark_red`       | `&4`                                              |
| `dark_purple`    | `&5`                                              |
| `gold`           | `&6`                                              |
| `gray`           | `&7`                                              |
| `dark_gray`      | `&8`                                              |
| `blue`           | `&9`                                              |
| `green`          | `&a`                                              |
| `aqua`           | `&b`                                              |
| `red`            | `&c`                                              |
| `light_purple`   | `&d`                                              |
| `yellow`         | `&e`                                              |
| `white`          | `&f`                                              |
| `bold`           | `&l`                                              |
| `strikethrough`  | `&m`                                              |
| `underline`      | `&n`                                              |
| `italic`         | `&o`                                              |
| `reset`          | `&r`                                              |

The individual permissions take priority over the "group" permissions. For example, if you set `essentials.nick.color`
to `true` then set `essentials.nick.black` to `false`, players will be able to set their nicknames to any color
except black.

## Nicknames

If you want players to be able to change the color of their nickname but not the text itself, set the permission
`essentials.nick.changecolors` to `true`. This will let them use color codes in their nickname, but the text will still
have to match their own username.
