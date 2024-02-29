# WIRELESS PROTOCOL

Wireless LAN -> 802.11 small areas like homes
Wireless man 802.11p vehicle communication


Different wireless technologies have different characteristics -> need to make a weighted choice based on what are the system requirements

LORAWAN suitable for machine -> machine communication the idea is that nodes communicate in time intervals before going to sleep, low consumption energy


## ETHERNET PROTOCOL 802.x

in a physically connected network all nodes share the same communication medium, so there is the need to handle collisions

```mermaid
flowchart LR
subgraph nodes
A[node a]
B[node b]
C[node c]
end
M[medium]
A --> M
B --> M
C --> M
```

## CSMA/CD

First solution relies on the collision detection and re-transmission after a random time wait

There are also solution that avoid collisions like token-passing ring that relies on a token being passed between nodes and only the nodes that have the token can transmit, this solution has a lot of overhead due to the token passing case

In Wireless networks there is also the same problem cause the ether is shared among the notes

```mermaid
flowchart LR
subgraph ether
A[node a]
B[node b]
C[node c]
end
```

## WIRELESS PROTOCOL

The wirless protocol is the same as the ethernet ones, CSMA

```mermaid
flowchart TD
A{channel is free}
B[send message]
C{collection detected}
D[wait a random time]
A-->|yes|B
B-->C
C-->|yes|D
D-->A
```

Due to the nature of the protocol there are no certainties about the communication performances

In order to avoid the hidden node problems the MACA (multiple access collision avoidance) which relies on requests and replies in order to start communication, this is not the default behavior 
MACA not avoid collisions of pre data communication or in cases some nodes joins the network after pre data communication appens


### WIFI ARCHITECTURES

#### BASE STATION

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

This is a classical use case that it's completely handled by the standard TCP/IP stack

In this configuration there are still problems due to nodes movements
#### AD-HOC P2P

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

In this architecture, no HW infrastructure is required but a lot of communication problems rise up (for example re-transmissions time rise up with the number of nodes), and TCP/IP does perform poorly

