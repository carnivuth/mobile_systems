---
id: RADAR
aliases: []
tags: []
index: 23
---

# RADAR

Positioning system for indoor environment based on RSSI computation and fingerprinting, it exploits a [scene analisys](BASE_TECHNIQUES.md#SCENE%20ANALYSIS)

![](Pasted%20image%2020240609155153.png)

## OFFLINE PHASE

A central server collects data sent by devices in UDP packets containing orientation and position, manually inserted by users

## ONLINE PHASE

mobile nodes send periodically UDP packets to the server that compares the packets to the dataset collected in the offline phase

[PREVIOUS](pages/positioning_systems/ACTIVE_BAT.md) [NEXT](pages/positioning_systems/EKAHAU.md)
