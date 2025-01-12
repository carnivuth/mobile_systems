---
id: HIERARCHICAL_MOBILE_IPV6
aliases: []
tags: []
index: 29
---

# HIERARCHICAL MOBILE IPV6 (HMIP)

This solution is based on a hierarchical structure of the infrastructure where foreign agents are associated with a foreign agent proxy (mobile anchor point MAP) that manages handoff procedures between foreign agents

```mermaid
flowchart BT
A[(HA)]
B((internet))
C{foreign\n agent\n gateway}
D{foreign\n agent\n gateway}
E[foreign\n agent]
F[foreign\n agent]
G[foreign\n agent]
H[foreign\n agent]
I[foreign\n agent]
J[mobile\n node]
A & C & D --> B
E & F & G --> C
H & I --> D
J --> E
```

the handoff can be

- **local subnet handoff** local to a MAP
- **MAP domain handoff** between to different MAPs

The mobile nodes organizes themselves in MAPS dynamically based on **service rate** and **mobility rate**

[PREVIOUS](pages/mobility/MOBILE_IP.md) [NEXT](pages/mobility/PROXY_HIERARCHICAL_MOBILE_IPV6.md)
