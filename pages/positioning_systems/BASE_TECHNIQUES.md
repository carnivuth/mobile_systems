---
id: BASE_TECHNIQUES
aliases: []
tags: []
index: 17
---

# BASE TECHNIQUES

## DISTANCE COMPUTATION

In order to compute position several methods relies on computing distance between nodes, several approaches are available

- **time of arrival (ToA)** , the distance is computed as $lightspeed*ToA$

- **Received signal strength indication (RSSI)** , the distance is computed by the received signal strength

## POSITION COMPUTATION

position can be computed using several geometrical and non geometrical approaches:

### Time difference of arrival (TDoA)

given 2 reference points $ref_1,ref_2$ **TDoA** is the set of points where

$$ToA(ref_1)=ToA(ref_2)$$

![](Pasted%20image%2020240608180440.png)

### LATERATION

the position is determined by computing distances from 3 reference points

### ANGULATION

based on the fact that the distance between 2 reference points is known, it computes the position using the Carnot's theorem:

$$
\displaylines{
a^2=b^2+c^2-2bc*\cos{\alpha} \\
b^2=a^2+c^2-2ac*\cos{\beta}
}
$$

![](Pasted%20image%2020240608180918.png)

### PROXIMITY

The current position is determined by the closest reference point to the node, ToA or RSSI can be deployed

![](Pasted%20image%2020240608181056.png)

### SCENE ANALYSIS

This is a statistical approach based on the knowledge of the deployment environment and of a dataset of observations made of it (*e.g. RSSI*)

this approach is composed by two phases

- **Preliminary phase** data are collected by observation and monitoring of the environment
- **Operational phase** environment observation are  compared to the collected data to estimate position

## ERROR SOURCES

Several things can cause error in position measurement such as:

- **Non Line of Sight (NLOS)** a node is not in direct visibility
- **clock skew**  clock are not synchronized
- **fading** due to obstacle presence

[PREVIOUS](pages/manets/CLUSTERING.md) [NEXT](pages/positioning_systems/TAXONOMY.md)
