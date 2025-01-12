---
id: PUB_SUB_PROTOCOLS
aliases: []
tags: []
index: 55
---

# PUB/SUB PROTOCOLS
## MESSAGE QUEUE TELEMETRY TRANSPORT (MQTT)

protocol that implements the [pub/sub model](PUB_SUB_MODEL.md) that relies on TCP to handle connections, that supports different delivery semantics for messages:

- at least ones
- at most ones
- at most ones

clients can also setup wills that are messages that are delivered to nodes when the node is disconnected

## ADVANCED MESSAGE QUEUING PROTOCOL (AMQP)

protocol based on the [pub/sub model](PUB_SUB_MODEL.md), richer semantics than MQTT but also heavier

## DATA DISTRIBUTION SERVICE (DDS)

brokerless solution based on multicast communication that is designed for mission critical environments where performance and reliability are essentials

![](Pasted%20image%2020240615103454.png)

[PREVIOUS](pages/IoT/PUB_SUB_MODEL.md) [NEXT](pages/IoT/REQUEST_RESPONSE.md)
