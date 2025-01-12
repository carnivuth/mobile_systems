---
id: MOBILE_MIDDLEWARE
aliases: []
tags: []
index: 32
---

# MOBILE MIDDLEWARE

Mobile Middleware general definition:

*support software stack, typically cross-layer and application-agnostic, which targets issues and challenges at OSI levels >= 4*

## WHY A MIDDLEWARE FOR MOBILE APPLICATIONS

Many of the problems that a mobile application need to resolve are always the same and are related to the **network not always available and no guaranteed performance**.

Given that, is not feasible for a business to address those problems each time there is the need to develop for mobile environments (**e.g. follow the DRY principle**)

A Middleware can also address different environment and hardware infrastructures and offer an homogeneous interface.

## MOBILE VS FIXED MIDDLEWARE

A mobile middleware **has lot of differences to address due to the different deployment environment**

- Context dynamically changes
- Need of decoupling in space and in time
- Asynchronous events, spaces for data sharing
- provisioning of some level/degree of visibility of running conditions to lower layers
- partial visibility of location change
- modifications in the QoS levels currently available

[PREVIOUS](pages/mobility/I_TCP.md) [NEXT](pages/mobile_middleware/MOBILE_MIDDLEWARE_PRINCIPLES.md)
