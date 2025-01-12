---
id: TAXONOMY
aliases: []
tags: []
index: 18
---

# TAXONOMY

Positioning systems can be classified in different categories

| CATEGORY          | DESCRIPTION                                                |
| ----------------- | ---------------------------------------------------------- |
| **PHYSICAL**      | position is computed as a numerical value                  |
| **SYMBOLIC**      | position is computed as a logical value (*e.g. city name*) |
| **ABSOLUTE**      | position is computed with a single reference system        |
| **RELATIVE**      | position is relative to some element of the infrastructure |
| **CENTRALIZED**   | one nodes computes positions of the other nodes            |
| **DECENTRALIZED** | each nodes compute is own position                         |

## CHARACTERISTICS

There are several characteristics to aim for a positioning system

- **ACCURACY** the error range of a measurements
- **PRECISION** the trust degree of a measurements
- **SCALABILITY** how much the positioning system can handle in terms of area of coverage and number of nodes
- **COSTS** cost of maintenance deployment time, client capabilities
- **LIMITATIONS** deployment environment that can host the positioning system (*e.g. indoor/outdoor*)

The deployment dictates what feature is requested from the positioning system together with  application requirements and user constraints

```mermaid
flowchart LR
A[application requirements]
B[user constraints]
C[deployment environment]
D((positioning system\n capabilities))
A & B & C --> D
```

[PREVIOUS](pages/positioning_systems/BASE_TECHNIQUES.md) [NEXT](pages/positioning_systems/MANET_POSITIONING_SYSTEMS.md)
