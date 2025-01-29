---
title: How it works
layout: default
parent: MultiPaper
---

# How MultiPaper works

MultiPaper allows a server administrator to run a single world across multiple Minecraft servers, allowing the infamous 250 player limit of a Minecraft server to be exceeded. How is this done?

## MultiPaper's architecture
To start with, there's various parts to MultiPaper that allow it to work:

1. The Master database
2. The MultiPaper servers
3. An optional load balancer (eg BungeeCord, Velocity, TCPShield, etc)
4. The players

### 1. The Master database

The Master database is what allows the servers to store data in a central location that can be accessed by all servers. Servers store chunks, maps, level.dat, player data, banned players, and more in this database. This database also keeps track of which chunk is belongs to which server, and coordinates communications between servers.

### 2. The MultiPaper servers

The MultiPaper servers replace your Spigot or Paper server. They are a fork of Paper, with optimisations from both Airplane and Pufferfish, giving you the best possible performance, while still being compatible with the Bukkit plugin ecosystem.

The Master database is great for storing data, but not so good when trying to sync data between the servers in real time. This is where peer-to-peer communications come in. Each MultiPaper server connects to one another to allow data to be updated in real time between them. If a player on server A attacks another player on server B, server A will send that data straight to server B for server B to damage the player and apply any knockback.

The MultiPaper servers also tick the blocks and entities in each loaded chunk. However, time would speed up if multiple servers ticked the same chunk at the same time. Thus, the servers coordinate with the Master server to ensure that each chunk is only ticked by a single server.

### 3. The load balancer (optional)

You will need to equally distribute your players between the servers otherwise MultiPaper will be useless and unable to give you any performance gains. You could tell 50 players to join server A, and another 50 players to join server B, but that system does not scale well as new players constantly want to join your server. Instead, a load balancer should be installed to do this for you.

A load balancer automatically distributes players between servers to balance the load evenly between each server. A few options for doing this with Minecraft servers are listed below. Enterprises may even have their own custom load balancer that can also be applied to MultiPaper.

1. A BungeeCord proxy with the [PlayerBalancer](https://www.spigotmc.org/resources/playerbalancer.55011/) plugin.
2. A Velocity proxy with the [VelocityLoadBalancer](https://github.com/bhopahk/VelocityLoadBalancer) plugin.
3. [TCPShield](https://tcpshield.com/) which includes a built-in load balancer and ddos protection.

### 4. The players

And finally, you need players. Using MultiPaper is pointless if there aren't even enough players to fill a regular Minecraft server.
