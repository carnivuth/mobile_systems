# ZIGBEE

Protocol optimized for some vertical domains where [bluetooth](BLUETOOTH.md) fails like

- industrial application
- home automation and home appliances controls
- environmental monitoring

## TOPOLOGIES

![](Pasted%20image%2020240321144834.png)

Nodes can be of different kinds

- PAN COORDINATOR main network controller
- Full function device participates to packets routing
- Reduced function device

### CLUSTER TREE

PAN COORDINATOR is the root of a tree-shaped network in this architecture a non leaf node is a full function device

Pan coordinator is the more stressed nodes as the majority of the traffic passes through him

### MESH TOPOLOGY

No constraints in the ways that nodes are connected, intermediary nodes are full function nodes

## OPTIONS FOR CHANNEL ACCESS

### NON BEACONED METHOD

wifi approach, CSMA-CA is used in order to retransmit packets in case of collision

### BEACONED METHOD

bluetooth approach, the coordinator syncronize the nodes and transimissions appens at fixed time intervals

usefull when working with sensors
