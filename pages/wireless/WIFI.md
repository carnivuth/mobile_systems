---
id: WIFI
aliases: []
tags: []
index: 4
---

# WIFI

The IEEE 802.11 standard is the most widespread solution for wireless communications, it provides 2 primary configurations

- **BASE STATION MODE** where the nodes are connected to a base station and communication can only append trough the base station itself

```mermaid
flowchart LR
subgraph net1
A[ap1]
C[node1]
end
subgraph net2
B[ap2]
D[node2]
end
C --> A
D --> B
E((internet))
A & B -->  E
```

- **AD HOC MODE** all nodes are potentially mobile and communicate directly, en example of ad hoc network are [manets](MANETS.canvas)

```mermaid
flowchart LR
subgraph net
A[node1]
B[node2]
C[node3]
D[node4]
E[node5]
A  <--> B & C
B  <--> D
C  <--> D
D  <--> E
E  <--> B
end
```

## WIFI MESH NETWORK

The objective is to cover with wireless connectivity technology wide areas like cities with a mesh network

![](Pasted%20image%2020240604192831.png)

[PREVIOUS](pages/wireless/CSMA.md) [NEXT](pages/wireless/WIMAX.md)
