---
id: ANDROID_PLATFORM
aliases: []
tags: []
index: 38
---

# ANDROID PLATFORM

Android is a complex platform that offers developers with a mobile middleware that handles common mobile problems, it's composed by 4 layers,

- **linux kernel** a stripped and modified version of the linux kernel
- **system level libraries** C++ libraries to interact with hardware components, modified version of the jvm (*dalvik virtual machine*)
- **application framework** java SDK's for interact with the under level components
- **applications**

In the android platform applications must follow the threading model offered by the platform and must be written in JAVA android compatible

## ANDROID IS LINUX? YES TO SOME EXTENT

The kernel part is based on the linux kernel with some additions and some things that got removed

| KERNEL EXTENSIONS<br>                | DESCRIPTION                                                    |
| ------------------------------------ | -------------------------------------------------------------- |
| **ASHMEM** shared memory manager<br> | Support for share memory for process communication             |
| **IPC binder**                       | faster inter process communication support based on **ASHMEM** |
| **ADVANCED POWER MANAGEMENT**        | application callable api for managing power consumption        |

Feature removed from the linux system are

- support for Glibc
- window manager support
- no linux utilities

so for this **android is not a fully compatible linux extension**

## POWER MANAGEMENT WITH WAKELOCKS

applications can through the wakelocks java API can influence the behavior of the kernel power management ( *this is an example of [cross layering pattern](MOBILE_MIDDLEWARE_PRINCIPLES.md#CROSS%20LAYERING%20PRINCIPLE)* )

## NOT ALL THE SYSTEM IS JAVA BASED

Some performance critical components are implemented in C/C++ to improve performance for example the multimedia stack

![](Pasted%20image%2020240507125214.png)

## DALVIK VIRTUAL MACHINE

Implemented in a registry-based model (in order to exploit the ARM architecture of smartphones ), it also run different bytecode of the JAVA standard in order to improve performance (*called .dex also instructions are reduced by 30%* )

## ANDROID SDK MAIN COMPONENT

Android offers to developers some main concept to interact with the android runtime

| COMPONENT              | DESCRIPTION                                                                                           |
| ---------------------- | ----------------------------------------------------------------------------------------------------- |
| **ACTIVITY**           | Main application component that represent an interaction with the user                                |
| **INTENT**             | Request to perform an operation to the android framework (as sharing content)                         |
| **SERVICE**            | codes that runs in the background with no interaction with the user (**no dedicated process/thread**) |
| **BROADCAST RECIEVER** | Application component that handle broadcast messages                                                  |

Other components are available

- **Activity manager** to handle [activity lifecicle](ACTIVITY.md#ACTIVITY%20LIFECICLE) and application management
- **package manager** to handle application management
- **Window Manager & View System**: handle windows on the screen
- **Resource Manager & Content Provider**: handle system resource and data access to them (*e.g. sqlite databases, filesystem*)
- **Telephony, Notification & Location Manager**

[PREVIOUS](pages/mobile_middleware/COMMUNICATION_PATTERNS.md) [NEXT](pages/android/ACTIVITY.md)
