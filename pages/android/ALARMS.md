---
id: ALARMS
aliases: []
tags: []
index: 43
---

# ALARMS

Alarms are task that can be scheduled at a given time, they fires intents, it can be recurring and does not need the application to be active, several benefits:

- Device does not have to be awake
- Does not use resources until it goes off
- Use with [broadcast receiver](ACTIVITY.md#BROADCAST%20RECEIVER) to start services and other operations

## ALARM TYPES

|                       | ELAPSED REAL TIME (ERT) | REAL TIME CLOCK (RTC) |
| --------------------- | ----------------------- | --------------------- |
| Do not wake up device | ELAPSED_REALTIME        | RTC                   |
| wake up device        | ELAPSED_REALTIME_WAKEUP | RTC_WAKEUP            |

## ALARMS BEST PRACTICES

Real time clock alarms are not suitable for client server interaction cause they can cause burst of requests

minimize the time an alarm wake up the device and use inexact alarms that can be grouped together  and fired at the same time by the android runtime

[PREVIOUS](pages/android/JOB_SCHEDULER.md) [NEXT](pages/android/SOCKETS.md)
