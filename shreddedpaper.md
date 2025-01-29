---
title: ShreddedPaper
layout: default
---

# ShreddedPaper

The focus of this paper fork is on reliability, in terms of increasing server uptime and reducing issues such as dupes and vanishing entities.

This is an experimental server jar with multithreading rather than being multi-server. Multi-server support will be added later with a MultiPaper 3.0 fork of this, but it will be designed to run on a few large servers with lots of cpu cores, rather than many small servers.

The multithreaded approach not only vastly improves efficiency as there's no serializing and deserializing between servers, but also drastically increases reliability, and makes existing multipaper dupes nearly impossible.
The upcoming multi-server code will also be designed in a way to be dupe-free, but will also limit the number of servers you can have running at once, as servers will need to lock data they edit, which doesn't scale well.

Compared to Folia's multithreaded approach:
 - There are no separated regions: player density can be high while still being multithreaded
 - Almost all plugins that are compatible with Folia will also be compatible with ShreddedPaper
 - Many non-Folia-compatible plugins will be compatible with ShreddedPaper, eg much of Essentials, although with a small performance penalty

Performance comparison as of 25/05/2024 with 500 bots in a 2000x2000 world:
 - ShreddedPaper: 18.28 tps
 - Folia: 4.40 tps
 - Purpur: 5.25 tps
(Tested on 1.20.6 with an M1 Pro 8-performance cores, 2 efficiency cores

Download [here](https://multipaper.io/shreddedpaper/download.html)
