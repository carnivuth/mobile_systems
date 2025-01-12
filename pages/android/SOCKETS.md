---
id: SOCKETS
aliases: []
tags: []
index: 44
---

# SOCKETS AND NETWORKING IN ANDROID

the java solution for sockets are available in android (*e.g. `Socket` `ServerSocket`*), they require a [multi-thread solution](ASYNCHRONOUS_TECHNIQUES.md), and explicit permission in the manifest file

## MANAGING NETWORK STATE

There are also components to interact with the network state

- **ConnectivityManager** Answers queries about state of network connectivity and Notifies applications when network connectivity changes
- **NetworkInfo** Describes status of a network interface of a given type (*e.g. Mobile or WiFi* )

## COMMUNICATION LIBRARIES

There are also libraries that handles the networking requests and the threading issues related like [volley](https://google.github.io/volley/) and [okhttp](https://square.github.io/okhttp/)

## NETWORK CARD MANAGEMENT

The network card can operate at different energy limited levels:

- **high power** max data transfer rate maximum energy consumption
- **low power** network card at the 50% of the power
- **idle** no connection available minimum energy consumption

## BEST PRACTICE: BUNDLE DATA TRANSFERS

In order to be energy efficient a best practice is to bundle the data transfers to limit the amount of time the network card is active

![](Pasted%20image%2020240618124220.png)

[PREVIOUS](pages/android/ALARMS.md) [NEXT](pages/IoT/IOT.md)
