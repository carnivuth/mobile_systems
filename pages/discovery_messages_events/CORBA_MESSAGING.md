---
id: CORBA_MESSAGING
aliases: []
tags: []
index: 62
---

# [CORBA](https://www.corba.org/) MESSAGING

Also the CORBA project offers support for messaging infrastructure, the messaging infrastructure is made of 2 principal components:



- **Asynchronous Messaging Interface (AMI)** Possibility of both polling and callback (*callback is passed as CORBA object, therefore even not in the same addressing space of client*)
- **Time Independent Invocation (TII)** to specify which CORBA objects play the role of router for the message ( *implementation of the [store and forward](MESSAGING.md#PROTOCOL%20ASPECTS) principle* )
## [LOCATORS](MESSAGING.md#LOCATORS) IN CORBA

locators are implemented trough Interoperable Object Reference (IOR), with different profiles depending on binding protocol

## CALLBACK VS POLLING

For the callback approach the application defines a callback function to be called

```c
voidsendpoll_somma (in int i, in int j)
voidpollsomma (out int success, out int somma)
```

![](Pasted%20image%2020240616160030.png)

For the Polling approach the application decides when to interrogate the CORBA support to retrieve the operation result:

```c
voidsendpoll_somma (in int i, in int j)
voidpollsomma (out int success, out int somma)
```

![](Pasted%20image%2020240616160048.png)

[PREVIOUS](pages/discovery_messages_events/JAVA_MESSAGE_SERVICE.md) [NEXT](pages/discovery_messages_events/EXTENSIBLE_MESSAGING_AND_PRESENCE_PROTOCOL.md)
