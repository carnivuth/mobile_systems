# ANDROID ARCHITECTURE

![](Pasted%20image%2020240507122305.png)

developers cannot mange the software infrastructure and application need to rely on the already given platform


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

applications can through the wakelocks java API can influence the behavior of the kernel power management

## NOT ALL THE SYSTEM IS JAVA BASED

Some performance critical components are implemented in C/C++ to improve performance for example the multimedia stack

![](Pasted%20image%2020240507125214.png)

## DALVIK VIRTUAL MACHINE

Implemented in a registry-based model (in order to exploit the ARM architecture of smartphones ), it also run different bytecode of the JAVA standard in order to improve performance (called **.dex**)