---
id: ZIGBEE
aliases: []
tags: []
index: 8
---

# ZIGBEE (IEEE 802.15.4)

Protocol optimized for some vertical domains IOT oriented where [bluetooth](BLUETOOTH.md) fails like

- industrial application
- home automation and home appliances controls
- environmental monitoring

The protocol has several improvements over [BLUETOOTH](BLUETOOTH.md) as:

- higher node limits (up to 65536 nodes)
- support for full mesh networking
- better support for real time appliances

## TOPOLOGIES

![](Pasted%20image%2020240321144834.png)

## NODES ROLES

In a zigbee network a node can play different roles:

- **PAN COORDINATOR** main network controller
- **Full function device** participates to packets routing
- **Reduced function device** device with limited capabilities

## CHANNEL MANAGEMENT

The zigbee protocol offers to possible solution for physical channel management

- [CSMA/CA](CSMA.md#CSMA/CA%20VARIANT)
- Beacon enabled network where the **PAN COORDINATOR** sends periodic messages, this solution is similar to what [BLUETOOTH](BLUETOOTH.md) does, is better suited for sensors communication

[PREVIOUS](pages/wireless/BLUETOOTH.md) [NEXT](pages/manets/MANETS.md)
