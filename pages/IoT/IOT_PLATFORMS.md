# IoT PLATFORMS

Platforms for interaction with IoT environment, The main objectives are:

- collect data from devices
- secure communication with devices
- manage the device state
- analyze data collected from the devices
- build application that can interact with the devices and the data stream

## AWS IoT

Amazon cloud solution for iot hub, that is composed of different cloud services

![](Pasted%20image%2020240613162351.png)

one of the main components is the **device shadow** that preserve the state of a device even when connection is not available.
Data flow can be redirected trough the **rules engine** component to different **AWS** microservices 

## AZURE IoT HUB

![](Pasted%20image%2020240613162421.png)


## SIEMENS MINDSPHERE PLATFORM

![](Pasted%20image%2020240613162502.png)

## EDGEX FOUNDRY

Infrastructure to manage communication with different IoT devices that abstracts from the protocol details and offers a northbound API for application and CLOUD infrastructure

![](Pasted%20image%2020240613162524.png)

EDGEX is a microservice architecture, The principal components are:

- **core-data** manages dataflow from the IoT devices
- **core-metadata** manages information on monitored devices, how to communicate with them and what data and command can be pulled/send to IoT devices
- **core-command** exec command on the nodes
- **device services** bottom elements of the infrastructure, they pull data from specific protocols and transform them in events that can be managed by the core-data component