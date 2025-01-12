---
id: PROXY_HIERARCHICAL_MOBILE_IPV6
aliases: []
tags: []
index: 30
---

# PROXY HIERARCHICAL MOBILE IPV6

One of the principal problems of [HMIP](PROXY_HIERARCHICAL_MOBILE_IPV6.md)  is that is not transparent to mobile nodes that need to implement it in the kernel space that is hard to push updates, PHMIP resolves this problem, it's meant to be used on limited networks where signals for handoff procedures have minimal costs

The main components of PHMIP are:

- **Local Mobility Domain** PHMIP capable network
- **Local Mobility Anchor** component where all mobile nodes traffic is routed trough
- **Mobile Access Gateway** perform mobility handoff procedure, it's the first hop gateway for the mobile nodes
- **NetLmm** Network based Localized Mobility Management
- **Binding Cache** Cache maintained by LMA, it contains Binding Cache Entries (BCE), with fields MN-ID, MAG proxy-CoA and MN-prefix
- **Binding Update List**  Cache maintained from MAG with info on attached mobile nodes
- **Proxy Binding Update (PBU)**  packet sent from MAG to LMA to signal an handoff procedure
- **Proxy Binding Acknowledge (PBA)** response packet of a PBU sent frol LMA to MAG
- **Proxy Care of Address (PCoA)**  public address of MAG
- **Mobile Node Identifier (MN-ID)**  unique identifier assigned to mobile nodes
- **Home Network Prefix** prefix assigned to mobile nodes from LMA

![](Pasted%20image%2020240608155305.png)

[PREVIOUS](pages/mobility/HIERARCHICAL_MOBILE_IPV6.md) [NEXT](pages/mobility/I_TCP.md)
