---
title: Electronic Components, Circuits, and Microcontroller Basics
nav_order: 4
-------------

## Introduction to Electronics and Components

Electronic circuits form the core of embedded systems and IoT technologies. They integrate numerous components working collectively to manage electrical signals effectively.

### Fundamental Electronic Components

* **Resistors** – Restrict electric current flow
* **Capacitors** – Store and discharge electrical energy
* **Inductors** – Store energy magnetically when current flows
* **Diodes** – Enable current flow in a single direction
* **Transistors** – Serve as switches or signal amplifiers
* **Integrated Circuits (ICs)** – Miniaturized circuits comprising multiple components
* **Microcontrollers (MCUs)** – Programmable units that manage inputs and outputs

### Essential Electrical Properties

* **Voltage (V)** – Electric potential difference
* **Current (I)** – Electric charge movement, measured in Amperes
* **Resistance (R)** – Opposes current flow, measured in Ohms
* **Power (P)** – Rate of energy usage, calculated as P = V × I

## Microcontroller Overview: ESP32 and Raspberry Pi Pico

ESP32 and Raspberry Pi Pico are widely adopted microcontrollers with distinct features and uses.

### ESP32 Characteristics

* Dual-core CPU (Xtensa LX6 or RISC-V variants)
* Integrated Wi-Fi and Bluetooth connectivity
* Versatile interfaces: GPIO, SPI, I2C, UART, ADC, DAC
* Optimized for low-power IoT deployments

#### ESP32 Pin Diagram

![ESP32 Pinout](esp32.webp)

### Raspberry Pi Pico Characteristics

* RP2040 dual-core ARM Cortex-M0+ CPU
* USB support for easy programming
* Features 26 multi-functional GPIO pins
* External modules needed for wireless connectivity

#### Raspberry Pi Pico Pin Diagram

![Raspberry Pi Pico Pinout](Pico.svg)

### GPIO (General-Purpose Input/Output) Explained

GPIO enables microcontrollers to communicate and control external hardware.

* **Input Mode** – Reading sensors or buttons
* **Output Mode** – Managing LEDs, buzzers, or relays
* **PWM (Pulse Width Modulation)** – Analog signal emulation via digital pulses
* **I2C, SPI, UART** – Standardized peripheral communication protocols

## Programming Microcontrollers with Arduino IDE

The Arduino IDE simplifies programming microcontrollers through its user-friendly interface.

* Leverage Serial Monitor for troubleshooting
* Connect sensors using functions like `analogRead()` and `digitalRead()`
* Establish Wi-Fi connections with the `WiFi.h` library for IoT integration

## Summary

This module covered foundational electronics concepts, microcontroller hardware details (ESP32 & Raspberry Pi Pico), and microcontroller programming essentials via the Arduino IDE. Grasping these components and GPIO functions is essential for successful embedded systems development and effective IoT solutions.

[Back](module2.md) / [Next](module4.md)
