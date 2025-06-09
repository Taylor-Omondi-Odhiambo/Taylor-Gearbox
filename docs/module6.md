---
title: "Introduction to Wired Communication Protocols"
nav_order: 7
---

## Introduction to Wired Communication Protocols

Embedded systems rely on robust wired interfaces for sensor data exchange and device control. This module covers common protocols and sensor integration techniques.

### Communication Protocols in Embedded Systems

Communication protocols define rules for data transfer between microcontrollers and peripherals. Key considerations include:

* **Signaling**: Voltage levels, signaling edges (rising/falling), and idle states
* **Speed**: Data rates (baud rate for UART, clock frequency for SPI/I2C)
* **Topology**: Point-to-point vs. multi-drop bus
* **Error Checking**: Parity bits, checksums, acknowledgments
* **Master/Slave Roles**: Which device initiates and controls transactions

### Working with I²C, UART, and SPI

#### I²C (Inter-Integrated Circuit)

* Two-wire bus (SDA data, SCL clock) with pull-up resistors
* Supports multiple masters and slaves using 7- or 10-bit addresses
* Standard speeds: 100 kHz (Standard), 400 kHz (Fast), up to 3.4 MHz (High-Speed)

#### UART (Universal Asynchronous Receiver/Transmitter)

* Full-duplex, two-wire (TX/RX) asynchronous communication
* Configurable baud rate, data bits, stop bits, and parity
* Simple wiring; commonly used for serial consoles and GPS modules

#### SPI (Serial Peripheral Interface)

* Four-wire synchronous bus: MOSI, MISO, SCLK, CS (chip select)
* Driven by a single master controlling one or more slaves
* High throughput—clock speeds often exceed 10 MHz

### Interfacing an Ultrasonic Distance Sensor

Ultrasonic modules (e.g., HC-SR04) measure distance by timing echo return.

```python
from machine import Pin, time_pulse_us
import time

trigger = Pin(2, Pin.OUT)
echo    = Pin(3, Pin.IN)

while True:
    trigger.low()
    time.sleep_us(2)
    trigger.high()
    time.sleep_us(10)
    trigger.low()

    duration = time_pulse_us(echo, 1)
    distance_cm = (duration / 2) / 29.1
    print("Distance:", distance_cm, "cm")
    time.sleep(0.5)
```

* **time\_pulse\_us()** captures echo pulse width.
* Distance calculation uses sound speed constant (\~29.1 µs/cm).

### Interfacing a PIR Motion Sensor

Passive Infrared (PIR) sensors detect IR radiation changes to sense motion.

```python
from machine import Pin
o = Pin(4, Pin.IN)

while True:
    if o.value():
        print("Motion Detected")
    time.sleep(0.2)
```

* **Pin.IN** reads digital high when motion is detected.
* Add debounce or retrigger delay if needed.

## Summary

This module detailed wired communication protocols (I²C, UART, SPI) and demonstrated interfacing ultrasonic and PIR sensors with microcontrollers. Mastery of these techniques is vital for reliable sensor data acquisition and control.

[Module 5](module5.md) - [Module 7](module7.md)
