---

title: Introduction to Python and Raspberry Pi Pico
nav_order: 5
-------------

## Introduction to Python for Embedded Systems

Python is a versatile, high-level programming language that has gained popularity in embedded development due to its readability and extensive ecosystem. When used on microcontrollers like the Raspberry Pi Pico, Python (via MicroPython or CircuitPython) enables rapid prototyping and easy code maintenance.

### Why Python?

* **Readability**: Clear syntax speeds up development and debugging.
* **Rich Libraries**: Access to modules for hardware interaction, networking, and data processing.
* **Community Support**: Extensive documentation and examples for embedded Python.

## Core Python Concepts

Before deploying code to a microcontroller, understanding these fundamentals is essential:

* **Data Types**: `int`, `float`, `str`, `bool`, `list`, `dict`, `tuple`
* **Control Flow**: `if`, `elif`, `else`, `for` loops, `while` loops
* **Functions**: Defining reusable blocks with `def`, returning values
* **Modules & Packages**: Organizing code into files and importing functionality with `import`

```python
# Example: Simple function and loop
def blink_message(times):
    for i in range(times):
        print("Blink", i+1)

blink_message(3)
```

## Raspberry Pi Pico Overview

The Raspberry Pi Pico is a cost-effective microcontroller board powered by the RP2040 chip.

* **Processor**: Dual-core ARM Cortex‑M0+ @ 133 MHz
* **Memory**: 264 KB SRAM, 2 MB flash storage
* **GPIO**: 26 multi-function pins (digital I/O, ADC, PWM, SPI, I2C, UART)
* **Interfaces**: USB 1.1 for power and data transfer

### MicroPython on Pico

MicroPython is a lean implementation of Python 3 optimized for microcontrollers.

* **Firmware**: Downloadable UF2 file flashed via USB boot mode.
* **REPL**: Interactive prompt accessible over USB serial for immediate testing.
* **File System**: Pico appears as a USB mass storage device for script upload.

### Thonny IDE Setup

Thonny is a beginner-friendly Python IDE that simplifies MicroPython deployment.

1. **Install Thonny**: Available on Windows, macOS, and Linux.
2. **Configure Interpreter**: Select "MicroPython (Raspberry Pi Pico)" and the correct COM port.
3. **Upload Script**: Write code in Thonny and use "Run" to save `main.py` on the Pico.

## GPIO Programming in Python

Controlling pins with MicroPython is straightforward using the `machine` module.

```python
from machine import Pin
import time

# Initialize onboard LED (GP25) as output
led = Pin(25, Pin.OUT)

# Blink loop
while True:
    led.toggle()
    time.sleep(0.5)
```

* **Pin(25, Pin.OUT)**: Creates an output pin instance.
* **toggle()**: Flips LED state.
* **sleep()**: Pauses execution (in seconds).

## Summary

This module introduced Python programming fundamentals and showed how to run MicroPython on the Raspberry Pi Pico. You learned basic Python syntax, Pico hardware specs, firmware setup, and simple GPIO control. These skills form the basis for developing advanced IoT and embedded applications.

[Back](module3.md) / [Next](module5.md)