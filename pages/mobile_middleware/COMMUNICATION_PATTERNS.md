---
id: COMMUNICATION_PATTERNS
aliases: []
tags: []
index: 37
---

# COMMUNICATION PATTERNS

Patterns that handle communication between nodes in a mobile environment
## CLIENT INITIATED CONNECTION FOR PUSH MODEL

Pattern that resolves the problem of reaching the client from the server for server -> client push interactions. the client starts a connection to the server that updates the client status (*e.g. AJAX interaction*)

![](Pasted%20image%2020240608151433.png)

## CONNECTION FACTORY

Pattern that decouple connection management and application business code by hiding connection details behind a factory component (*used by java mobile edition M.E.*)

## MULTIPLEXED CONNECTION

Pattern to allow multiple logic connections to travel on a single level 4 physical connection in order to improve performance instead of creating multiple channels (*e.g. SCTP stream control transfer protocol for multimedia streaming*)

[PREVIOUS](pages/mobile_middleware/RESOURCE_MANAGEMENT_PATTERNS.md) [NEXT](pages/android/ANDROID_PLATFORM.md)
