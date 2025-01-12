---
id: MESSAGING
aliases: []
tags: []
index: 60
---

# MESSAGE MANAGEMENT IN MOBILE ENVIRONMENTS

One of the main principles of messages solution in mobile environment is decoupling resources involved in communication, this can be achieved by the use of standard and open formats

## MESSAGE EXTENSIBILITY

One important key factor is also the possibility to extend the messaging system for improved semantics, different systems can be used to achieve this

- versioning of the messages
- messaging formats with extension points
- forward compatibility with the possibility to ignore unknown parts of the protocol

## MARSHALLING/UNMARSHALLING MANAGEMENT

A messaging solution needs to take into account the marshal/unmarshal operations, possibile solutions are:

- marshal/unmarshal code can be generated from the message format specifications (*e.g. Interface Description Language (IDL)*)
- use of introspection that is more expressive but more expensive at runtime

## DATA FORMATS

Different techniques available for data format agreement:

- **Specification** usual approach of Internet protocols with messages in binary format
- **Negotiation** the two parts negotiate the data format at runtime
- **Receiver-makes-right** sender uses its native formats and specifies metadata to indicate which formats are used

## PROTOCOL ASPECTS

There are also protocol characteristics that need to be take into account

- session management by handling application different from the transport session
- end to end principle or not at the application level
- store and forward approach

## COMMUNICATION SCHEMES

Also the semantics with witch the communication is handled by the application component is important:

- **blocking vs non blocking semantics**  implemented with promises or callbacks
- **different level behavior**  the application can perform the role of the listener at the transport layer and not necessary the same role at the application layer

## LOCATORS

Also locators plays a role given the fact that nodes are mobile is not always possible to use locators as IP/TCP addresses, two principle type of locator are defined:

- **transparent** locators implemented as URI ( *e.g. as in [REST](REST.md)* )
- **opaque** need of a middleware to generate and use locators

## GENERAL CONSIDERATIONS

other general considerations can be made:

- **proxies** usage to split the transport connection in two
- **security**  at message level with ssl approaches
- **durability** in the message exchange phase even if the node is mobile
- **NAT problems** when nodes that wants to offer services are mobile

## RELIABILITY AND QoS

also QoS politics need to be taken into account, possible solution can be ACK based

- Regular
- Cumulative
- Negative
- Piggy-backed

Also in order delivery semantics can be dropped to improve performance

[PREVIOUS](pages/discovery_messages_events/SERVICE_DISCOVERY.md) [NEXT](pages/discovery_messages_events/JAVA_MESSAGE_SERVICE.md)
