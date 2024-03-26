# AD HOC ON DEMAND DISTANCE VECTOR

AODV tries to address the problem of the variable sized header of [DSR](DYNAMIC%20SOURCE%20ROUTING.md) by maintain a reduced routing table suitable for manets

```mermaid
flowchart TD
a[the source sends a packet \n with source and destination in flooding mode]
b[nodes that recive the packets \n start the creation of a routing table of the inverse paths]
c[the destination recives the packet \n and send a route reply packet to the source \n the unicast transmision does not contain the full path \n but exploits the routing tables]
d[nodes that recive the packets \n start the creation of a routing table of the direct paths]
a --> b
b --> b
b --> c
c --> d
```

![](Pasted%20image%2020240326130744.png)

## PATH TABLE STRUCTURE

### INVERSE PATHS C TABLE EXAMPLE

| SOURCE | DESTINATION | DISTANCE FROM THE SOURCE |
| ------ | ----------- | ------------------------ |
| S      | D           | 1                        |

### DIRECT PATHS C TABLE EXAMPLE

| SOURCE | DESTINATION | NEXT HOP | DISTANCE FROM THE DESTINATION |
| ------ | ----------- | -------- | ----------------------------- |
| S      | D           | F        | 3                             |

The direct path tables is the one the does the heavy lifting in data packet routing, the inverse path is only needed for the route reply routing

## ROUTE ERROR 

In the route error scenario the node that detects the route error situation informs the other nodes like in [DSR](DYNAMIC%20SOURCE%20ROUTING.md) and they update their routing table, the message is broadcast to the neighbors route error to inform them

## LINK FAILURE DETECTION

Extension that force all nodes to send hello messages to the neighbors in order to discover broken routing table lines

## POSSIBLE OPTIMIZATION

In a route request situation an intermediate node can respond with something in the routing table 
