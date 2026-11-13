# STM32 FreeRTOS Touch Input Task Control System

## Overview
An event-driven task control system developed using the STM32F429ZIT6 Discovery Board and FreeRTOS. The system responds to touch-based GPIO inputs and UART commands to dynamically control task execution.

## Hardware Requirements
- STM32F429ZIT6 Discovery Board
- Touch input switches/sensors connected to GPIO pins
- LEDs for task status indication

## Software Requirements
- Embedded C
- STM32CubeIDE
- FreeRTOS
- STM32 HAL Library
- Tera Term or any UART terminal

## Features
- GPIO external interrupt-based input detection
- FreeRTOS Event Groups for event communication
- Software timers for periodic input checking and event counting
- Dynamic task suspension and resumption
- UART interrupt-based command reception
- UART commands for selecting operating modes
- Task status monitoring through UART

## Task Architecture
- **Task1:** Toggles LED on PG10.
- **Task2:** Toggles LED on PG11.
- **Task3:** Toggles LED on PG12.
- **EMG Task:** Toggles LED on PG14.
- **Control Task:** Waits for event bits and activates the selected task while suspending the others.
- **UART Task:** Processes commands received through UART.

## Communication and Synchronization
- GPIO external interrupts detect input events.
- FreeRTOS Event Groups communicate events to the Control Task.
- Software timers handle periodic operations.
- Task notifications signal UART command reception.
- USART1 is configured at 115200 baud for serial communication.

## UART Commands
| Command | Function |
|---|---|
| `SET_MODE=TASK1` | Activates Task1 |
| `SET_MODE=TASK2` | Activates Task2 |
| `SET_MODE=TASK3` | Activates Task3 |
| `SET_MODE=ETASK` | Activates EMG Task |
| `STATUS?` | Displays task status |

## Concepts Used
- FreeRTOS Multitasking
- Task Suspension and Resumption
- Event Groups
- Software Timers
- Task Notifications
- GPIO External Interrupts
- UART Interrupt Handling
- Inter-Task Communication

## Author
Sneha B.
