---
id: CELLULAR_NETWORKING
aliases: []
tags: []
index: 6
---

# CELLULAR NETWORKING

Originated from the evolution of telecom solution of communication of mobile devices, based on a grid of low powered antenna for scalability reason, frequencies can be reused in non adjacent cells The architecture is the following:

```mermaid
flowchart LR
A{mobile\n switching\n center}
B{mobile\n switching\n center}
G[(internet)]
subgraph cells
direction TB
C[cell]
D[cell]
E[cell]
F[cell]
end
C & D --> A
E & F --> B
A & B --> G
```

Where:

- cells service a base local area, and is the connection point for the mobile devices
- MSC manages mobility of the nodes, connection to the van and setup of local calls

The range of a single cell depends on many factors such as:

- landscape and obstacles
- technology used

In common deployment scenarios cells coverage area overlaps, this enables QoS practices

## TECHNOLOGY EVOLUTIONS

With time cellular networking technology converged in the internet communication technologies

| GENERATION | FEATURES                                 |
| ---------- | ---------------------------------------- |
| 2(GSM)     | digital communications, only voice calls |
| 2.5(GPRS)  |                                          |
| 3(UMTS)    |                                          |
| 4(LTE)     |                                          |

## GSM ARCHITECTURE

![](Pasted%20image%2020240307143626.png)

Where:

- **MS** is the mobile node that communicates whit the **BSS** using the hardware support of the **MT** and authenticates with the **TE** component towards the infrastructure
- **BSS** communicates with the single nodes with the **BTS** component that manages handovers signals channel allocation and frequency hopping, the communication with the **MSC** is done trough the network card **A**
- **MSC** plays the role of gateway towards the **PSTN** network, the call routing is done trough the use of the **VLR** **HLR** registries
- the **OSS** components offers services of authentication of the nodes through **AUC** and the identification of fraudulent identities with the **EIR**, it also offers network monitoring control and management through the **OMC** **NMC** **ADC**

## HANDOFF

A big problem of cellular networking is to handle mobility of the phones during communication operations, there are various motivation that can cause an handoff procedure to be triggered:

- load balancing
- stronger signal from other BSS cause the node is moving towards them

**the policy is not dictated by the MSC, only the mechanism**

```mermaid
flowchart TD
I[The old BSS triggers an handoff\n by signaling to the msc a list of new possible bss]
A[The MSC set the new path for the new BSS]
B[The new BSS allocates the channel for the device]
C[The new BSS notify the old BSS and MSC that it's ready]
D[old BSS notify the device to start the switching process]
E[The device ask the new BSS to start channel communication]
F[The device notify MSC that handover is completed]
G[Resources are de-allocated on the old BSS]
H[This procedure had a lot of critical situation that needs addressing]
I --> A
A --> B
B --> C
C --> D
D --> E
E --> F
F --> G
G --> H
```

The principle goal of this procedure it's service continuity so in this context wasting resources is accepted

### HANDOFF PROCEDURE FOR DIFFERENT MSC

In this particular case the call is still routed trough the MSC where it has began ANCHOR MSC, other MSC are appended to the chain as the node is moving

![](Pasted%20image%2020240606103443.png)

### HANDOFF TAXONOMY

| TAXONOMY          | MEANING                                                                                                        |
| ----------------- | -------------------------------------------------------------------------------------------------------------- |
| HORIZONTAL        | Handoff is performed between same technologies                                                                 |
| VERTICAL          | Handoff is performed between different technologies                                                            |
| MOBILE INITIATED  | Handoff is started by the mobile device                                                                        |
| NETWORK INITIATED | Handoff is started by the networking infrastructure                                                            |
| REACTIVE          | Handoff is started in response to a node exiting the coverage area                                             |
| PROACTIVE         | Handoff is started before the node exits the coverage area                                                     |
| HARD              | The handoff procedure does not allow the mobile node to be connected to multiple BSS in the same time interval |
| SOFT              | The handoff procedure allow the mobile node to be connected to multiple BSS in the same time interval          |

[PREVIOUS](pages/wireless/WIMAX.md) [NEXT](pages/wireless/BLUETOOTH.md)
