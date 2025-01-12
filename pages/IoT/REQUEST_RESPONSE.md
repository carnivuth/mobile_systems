---
id: REQUEST_RESPONSE
aliases: []
tags: []
index: 56
---

# REQUEST RESPONSE

Model of interaction where one of the nodes plays the role of the server listening and accepting communications by client machines that makes requests, in this model **only client can start a communication**

```mermaid
flowchart LR
A(client)
B(server)
A --request--> B
B --response--> A
```

possible interaction with this model can be:

- **pull** actuators request configurations from the server
- **push** sensors send data to the server

[PREVIOUS](pages/IoT/PUB_SUB_PROTOCOLS.md) [NEXT](pages/IoT/REST.md)
