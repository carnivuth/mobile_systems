---
id: PATTERNS
aliases: []
tags: []
index: 34
---

# PATTERNS

Mobile environment can exploit several patterns for different tasks typologies

## ARCHITECTURAL PATTERNS

inherited from non mobile environments, patterns for application's architectures that describes how component should interact
### Level-based

Multi-layer sw architecture with different responsibilities “rigidly” allocated to different layers
### Client-Server

Most frequent pattern in distributed computing: clients use resources and services offered by server
### Peer-to-peer

Any node can dynamically play the role of either client or server; functionality could be more or less symmetric
### Pipeline

Pipeline as chain of processing elements aligned in such a way that output of one is offered as input for the successive one in the chain
### Multi-tier

Client-server architecture where applications are run by a multiplicity of different software agents
### Blackboard

A common knowledge base (blackboard) is updated iteratively by different knowledge sources, starting from including problem specification and then evolving to solution results
### Publish/Subscribe

Different nodes publish data to a broker that can be received from different nodes acting as subscribers

other types of patterns specific for mobile nodes are
- [COMMUNICATION_PATTERNS](COMMUNICATION_PATTERNS.md)
- [RESOURCE_MANAGEMENT_PATTERNS](RESOURCE_MANAGEMENT_PATTERNS.md)
- [DISTRIBUTION_PATTERNS](DISTRIBUTION_PATTERNS.md)
Tre categorie principali:
- per la **distribuzione**
	- [RemoteFacade](RemoteFacade.md)
	- [DataTransferObj](DataTransferObj.md)
	- [remoteProxy](remoteProxy.md)
	- [observer](observer.md)
- per la **gestione delle risorse** e la **sincronizzazione**
	- [session token](sessTok.md)
	- [caching](caching.md)
	- [eager](eager.md) acquisition
	- [lazy](lazy.md) acquisition
	- [synchronization](synch.md)
	- [rendezvous & state transfer](stateTransfer.md)
- per la **comunicazione**
	- [connection factory](connFact.md)
	- [multiplexed connection](multiplexedConn.md)
	- [client-initiated connection for push model](clientInit.md)

[PREVIOUS](pages/mobile_middleware/MOBILE_MIDDLEWARE_PRINCIPLES.md) [NEXT](pages/mobile_middleware/DISTRIBUTION_PATTERNS.md)
