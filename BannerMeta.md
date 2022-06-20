# BannerMeta

BannerMeta lets you create custom flag designs for banners and shields. Each banner can have unlimited patterns and patterns listed first will show underneath patterns listed later.

<!-- TODO: use images/bannermeta.png -->
![BannerMeta example](https://user-images.githubusercontent.com/1917406/63939958-5f891000-ca60-11e9-8025-32808f018757.png)

## Base Color

Base color should be the first thing listed for a banner. It will be displayed as RGB. Base color will show below all patterns.

Note that on 1.13 and above, you don't need to specify a base color for banners, as banners already have a base color.

## Patterns

Patterns will be listed after the base color and will include the type with the color listed after a comma.
[PatternTypes can be found here.](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/block/banner/PatternType.html)

### Example Syntax

An example banner:

`- BANNER:13 1 basecolor:11685080 SQUARE_TOP_RIGHT:14188339`
