---
id: MEDIUM_ACCESS_CONTROL
aliases: []
tags: []
index: 2
---

# MEDIUM ACCESS CONTROL

IEEE defines a section of standards for wireless connectivity technologies at data link layer under the section 802.xx

```mermaid
flowchart TD
subgraph higher_layer
A[802.2]
B[802.3]
C[802.5]
D[802.11]
end
subgraph medium_access_control
E[CSMA/CD]
F[Token-passing]
G[CSMA]
end
higher_layer ~~~ medium_access_control
```

## WIRELESS ARCHITECTURES

There are two possible configuration for a wireless infrastructure:

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


- **AD HOC MODE** all nodes are potentially mobile and communicate directly

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

[PREVIOUS](pages/wireless/WIRELESS_COMMUNICATION.md) [NEXT](pages/wireless/CSMA.md)
