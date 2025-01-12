---
id: EXTENSIBLE_MESSAGING_AND_PRESENCE_PROTOCOL
aliases: []
tags: []
index: 63
---

# EXTENSIBLE MESSAGING AND PRESENCE PROTOCOL (XMPP)

Protocol develop for large scale distributed application to notify if a user is connected to the application (*online status*).It's  a [pub/sub](PUB_SUB_MODEL.md) protocol with messages codified in xml format

XMPP is based on the client server model of interaction, where client send XML encoded data flows to the server after parameter negotiation.

## INTERACTION SEMANTICS

The protocol manages one-to-one and one-to-many communication

- message stanza one-to-one mechanism
- presence stanza one-to-many mechanism based on pub/sub
- info/query stanza request-response mechanism

## NOT SPECIFIC DESIGNED FOR THE PURPOSE

XMPP is not designed for message exchange but given the popularity is a good candidate with some major flaws

- XML format is expensive for constrained devices
- high cost for message interaction cause connection needs to be reestablished with each interaction

to address this flows Android use a proprietary implementation to address this issues

![](Pasted%20image%2020240616164345.png)

[PREVIOUS](pages/discovery_messages_events/CORBA_MESSAGING.md) [NEXT](pages/discovery_messages_events/EVENTS.md)
