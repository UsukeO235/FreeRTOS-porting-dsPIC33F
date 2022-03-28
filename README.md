# FreeRTOS-porting-dsPIC33F
Porting instructions of FreeRTOS for dsPIC33F family

## Overview
This repository shows how to port a FreeRTOS kernel to a dsPIC33F microcontroller.
In these instructions, we focus on a dsPIC33FJ128MC804.

## Environment
| Item | Version |
| ---- | ---- |
| OS (Development PC) | Windows 10 Home 21H2 |
| FreeRTOS kernel | V10.4.6 |
| MPLAB X IDE | v6.00 | 
| XC16 compiler | v2.00 |

## Instructions
### Download FreeRTOS kernel source and demo code
- kernel source:https://github.com/FreeRTOS/FreeRTOS-Kernel/tree/main
- FreeRTOS repository including some demo:https://github.com/FreeRTOS/FreeRTOS/tree/main
### Create new MPLAB X project
Create new standalone project.
### Copy necessary files to project folder
Copy following files:
- FreeRTOS-Kernel-main\portable\MPLAB\PIC24_dsPIC\port.c
- FreeRTOS-Kernel-main\portable\MPLAB\PIC24_dsPIC\portasm_dsPIC.S
- FreeRTOS-Kernel-main\portable\MPLAB\PIC24_dsPIC\portmacro.h
- FreeRTOS-Kernel-main\portable\MemMang\heap_1.c
- FreeRTOS-Kernel-main\include\\*.h
- FreeRTOS-Kernel-main\croutine.c
- FreeRTOS-Kernel-main\event_groups.c
- FreeRTOS-Kernel-main\list.c
- FreeRTOS-Kernel-main\queue.c
- FreeRTOS-Kernel-main\tasks.c
- FreeRTOS-Kernel-main\timers.c
- FreeRTOS-main\FreeRTOS\Demo\dsPIC_MPLAB\FreeRTOSConfig.h

Destinations are as follows:
- project_root\FreeRTOS-Kernel\portable\MPLAB\PIC24_dsPIC\port.c
- project_root\FreeRTOS-Kernel\portable\MPLAB\PIC24_dsPIC\portasm_dsPIC.S
- project_root\FreeRTOS-Kernel\portable\MPLAB\PIC24_dsPIC\portmacro.h
- project_root\FreeRTOS-Kernel\portable\MemMang\heap_1.c
- project_root\FreeRTOS-Kernel\include\\*.h
- project_root\FreeRTOS-Kernel\croutine.c
- project_root\FreeRTOS-Kernel\event_groups.c
- project_root\FreeRTOS-Kernel\list.c
- project_root\FreeRTOS-Kernel\queue.c
- project_root\FreeRTOS-Kernel\tasks.c
- project_root\FreeRTOS-Kernel\timers.c
- project_root\FreeRTOSConfig.h
### Modify FreeRTOSConfig.h
You can find the line that includes a device specific header in FreeRTOSConfig.h.
```c
#include <p33FJ256GP710.h>
```
In these instructions, we change the line like this:
```c
#include <p33FJ128MC804.h>
```
### Build project
