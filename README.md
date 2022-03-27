# FreeRTOS-porting-dsPIC33F
Porting instructions of FreeRTOS for dsPIC33F family

## Overview
This repository shows how to port a FreeRTOS kernel to a dsPIC33F microcontroller.

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
### Modify FreeRTOSConfig.h

### Build project
