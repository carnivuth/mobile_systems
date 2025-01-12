---
id: SIEMENS_MINDSPHERE
aliases: []
tags: []
index: 50
---

# SIEMENS MINDSPHERE PLATFORM

Siemens cloud and edge based solution for IoT

![](Pasted%20image%2020240613162502.png)

### HANDLE CONNECTION TO DEVICES

the mindconnect layer is the one responsible for offering the connection support to the IoT devices, it's an all-in-one hardware/software solution that provides connectivity for the most popular industrial protocols such as

### MINDSPHERE GATEWAY

Mindsphere infrastructure relies on a central gateway to handle request from application components and devices that want to send data

```mermaid
flowchart TD
A[client application]
B[mindsphere device]
subgraph core_services
C{mindsphere\n gateway}
D[(mindsphere gateway\n registry)]

end
A & B --> C
C --gets routes and\n access roules--> D
```

### MINDSPHERE IoT SERVICES

- **File Service**: provides a basic file management tools with an interface to manage, search and download data. Each file is linked to an asset, has some properties that describe it and can be retrieved after a connection to the IoT gateway. APIs provide CRUD operations on files.

- **Time Series service**: a service similar to File service, but only for the data type time series. Time series records are linked to an asset and an aspect and consist of a timestamp, one or more values and a quality indicator for variables.

- **Aggregation service**: creates aggregated summaries of time series data and interfaces to read them. It is particularly useful to reduce the amount of data sent to cloud for analysis. Once chosen a time interval to aggregate provides standard aggregate information such as min, max, average, tot number of points

### MINDSPHERE CONNECTIVITY SERVICES

- **Agent management service**: provides API to create, update, delete and manage the rights of agents. Agents are the primary actors that perfom actions on data in Mindsphere, when created they are assigned an access token which is the key to get authenticated and autorized to communicate

- **MindConnect API**: API to send data securely from the shop floor devices to Mindsphere. Only agents that supports HTTP processing, TLS and JSON parsing have the requirements to communicate. It allows also to set the configuration for both the data source from which retrieve the data and the data model to be shared

- **OPC UA PubSub Service**: specific module that provides MQTT- based API to agents to upload data according to OPC UA specification

[PREVIOUS](pages/IoT/AZURE_IOT_PLATFORM.md) [NEXT](pages/IoT/EDGEX_IOT_PLATFORM.md)
