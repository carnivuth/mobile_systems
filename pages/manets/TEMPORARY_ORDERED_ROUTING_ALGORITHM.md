---
id: TEMPORARY_ORDERED_ROUTING_ALGORITHM
aliases: []
tags: []
index: 15
---

# TEMPORARY ORDERED ROUTING ALGORITHM

TORA is designed to work in highly dynamic environment with a lot of mobility, ope of the main focus is to localize the control messages to a relative small portion of the network

The basic function of TORA are

- **route maintenance** is done through the link reversal algorithm that limits the node involved to a local area around the fault
- **route creation** in this phase a direct acyclic graph is created from the source to the destination, this graph is created exploiting [flooding](MANETS_ROUTING.md#FLOODING%20(level%200%20solution))
- **route erasure** a packet is routed in order to invalid routes

TORA maintains a local DAG for each node of the network, nodes are labeled with a height metric that is dependent on the logical time of the node

| ADVANTAGES                                                                                | DISADVANTAGES                                                                  |
| ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Less control overload cause control packets are limited to a small portion of the network | local changes results in non optimal routing                                   |
|                                                                                           | the concurrent deletion and deduction of routes can results in temporary loops |

[PREVIOUS](pages/manets/GREEDY_PERIMETER_STATELESS_ROUTING.md) [NEXT](pages/manets/CLUSTERING.md)
