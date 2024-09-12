---
id: GREEDY_PERIMETER_STATELESS_ROUTING
aliases: []
tags: []
index: 6
---

# GREEDY PERIMETER STATELESS ROUTING

**GPSR** is a geographic routing protocol based on 2 big assumptions

- each nodes knows is location and the destination location
- each nodes maintains a list of the neighbors and they're positions

**This are two big assumption that are not always guaranteed**

## DATA TRANSMISSION MODES

there are 2 possible modes for data transmission in **GPSR**

- **greedy** the packet is forwarded to the neighbor that is closest to the destination

 - **perimeter face forwarding** each nodes computes the relative neighborhood graph and when greedy fails the first node in the graph is traversed and then greedy is tried again
[PREVIOUS](ADHOC_ON_DEMAND_DISTANCE_VECTOR.md) [NEXT](TEMPORARY_ORDERED_ROUTING_ALGORITHM.md)
