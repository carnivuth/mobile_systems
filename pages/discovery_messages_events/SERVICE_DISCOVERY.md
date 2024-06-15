# SERVICE DISCOVERY

Service discovery is the procedure that allow an application to search for available services in the locality of the application node, a service discovery solution must meet the following requirements

- **AUTO CONFIGURATION** devices must configure themselves to participate to the the offering requesting communications
- **DISCOVERY** advertisement of services from the service provider
- **ACCESS** clients need to be able to communicate with services discovered

## APACHE RIVER (JINI)

Java solution for service discovery, based on a central node playing the role of service broker where nodes register and discover services (*similar to the [pub/sub model](PUB_SUB_MODEL.md)*)

```mermaid
flowchart TD
subgraph service_provider
C[java service object]
D[service attributes]
C ~~~ D
end
subgraph client
E[java service proxy object]
end
subgraph service_broker
A[java service proxy object]
B[service attributes]
A ~~~ B
end
client <--> service_provider
client --> service_broker
service_provider --> service_broker
service_broker --> client
service_broker --> service_provider
```

The protocol relies on service providers registering a proxy object to the service broker that can be received by clients in the discovery phase in order to communicate with the service provider

Failures are managed trough a **lease** mechanism where the resource assigned to client has a lease time, also the registration phase is managed with lease 

The protocol supports scalability by allowing the service providers to subscribe to multiple service brokers and 

### STUB SKEL LIMITATIONS

JINI overcomes stub and skeleton limitations, cause client can get the proxy objects at runtime from the broker

## SERVICE LOCATION PROTOCOL (SLP)

service agents makes periodic broadcast of the available services and user agent listen for the request for the application, optionally a directory agent can be deployed for caching purposes

```mermaid
flowchart TD
E((application))
F((service))
E <--> C
F <--> A
subgraph infrastructure
A[SERVICE AGENT]
B[SERVICE AGENT]
C[USER AGENT]
D[DIRECTORY AGENT]
C --> A
A & B --> D
D --> C
end
```

## UNIVERSAL PLUG AND PLAY (UPnP)

