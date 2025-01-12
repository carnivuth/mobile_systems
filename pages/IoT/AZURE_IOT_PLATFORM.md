---
id: AZURE_IOT_PLATFORM
aliases: []
tags: []
index: 49
---

# AZURE IoT PLATFORM

Microsoft cloud solution for IoT application, the main component is the azure IoT hub that communicates with the IoT devices and redirect the dataflow to the cloud components

![](Pasted%20image%2020240613162421.png)

## AZURE IoT EDGE

azure IoT offers also the possibility to perform edge computing tasks thanks to the edge runtime, the edge device can run azure modules, that are the smallest computational entities of an azure IoT solution (*e.g. docker compatible containers*)

```mermaid
flowchart LR
subgraph Azure_IoT_Edge_device
direction TB
A[azure module]
B[azure module]
C[azure module]
D[azure IoT edge runtime]
end
E[(IoT hub)]
D --> E
A & B & C --> D
```

[PREVIOUS](pages/IoT/AWS_IOT_PLATFORM.md) [NEXT](pages/IoT/SIEMENS_MINDSPHERE.md)
