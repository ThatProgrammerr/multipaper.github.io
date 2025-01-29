---
title: MultiPaper
layout: home
---

# MultiPaper

Run a single world across multiple Minecraft servers.

Fork of Paper with optimisations from Airplane and Pufferfish, giving you the best possible performance.

{: .warning }
**MultiPaper is in Public Beta!**  
Bugs are infrequent, and may only occur for a few players on your server, however they still exist and can range from duping items to corrupted chunks.
Make sure to keep frequent backups of your world data, and report any bugs on GitHub.

## MultiPaper's architecture

1. The Master database
2. The MultiPaper servers
3. An optional load balancer (eg BungeeCord, Velocity, TCPShield, etc)
4. The players

[Read more](multipaper/how-it-works.html)

## Plugin support

Will my Bukkit plugin work? Probably not.

Some plugins will work out of the box, however most plugins aren't designed for a multi-server environment. MultiPaper-compatible plugins must sync data with other servers in real time, and handle the many edge cases that come along with it. Make sure you're ready to commit the time and capital required to get your plugins working with MultiPaper.
