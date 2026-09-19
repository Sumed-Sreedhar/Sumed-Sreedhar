# Hi, I'm Sumed

Embedded firmware developer working with STM32 microcontrollers. I like the layer where software meets hardware: interrupts, DMA, communication protocols, and firmware that stays predictable when something goes wrong.

Right now I'm building a **flight computer** and a **custom bootloader**.

---

## In Progress

### STM32 Flight Computer
*Under active development*

A flight computer on the STM32F446RE that reads an IMU, magnetometer, barometer and GPS, estimates orientation and altitude, and logs flight data to an SD card. The goal is one coherent firmware architecture, not a pile of separate sensor demos.

- **Sensors:** MPU6500 (IMU), MLX90393 (magnetometer), BMP280 (barometer), NEO-6M (GPS)
- **Firmware:** sensor drivers over SPI/I2C/UART, self-test and fault handling, Mahony filter for attitude, PID control, FatFS logging
- **Structure:** a flight state machine first as a bare-metal loop, then ported to FreeRTOS tasks

```text
BOOT → SELF_TEST → INIT → READY → ARMED → FLIGHT → LANDING → SHUTDOWN
                  any fault (GPS, IMU, SD, UART) → FAULT
```

### Custom Bootloader (STM32F446RE)
*Under active development*

A bootloader that stays resident in flash and launches a separately linked application. It covers the parts of startup that normally stay hidden: flash partitioning, linker layout, vector table relocation, and the handoff into the application's reset handler.

- **Building:** separate bootloader and application images, an application header region, and a controlled jump into the app
- **Next:** image validation, a firmware update path, version metadata, and fault-aware boot
- **Goal:** host the flight computer firmware so it can be updated and recovered without a debugger

---

## Previous Work

| Project | What it does |
|---|---|
| **Road Surface Monitoring Device** | STM32F446RE + ESP32-S3. Detects road anomalies with an IMU and ultrasonic sensor, tags them with GPS, and uploads them over Wi-Fi. Uses interrupt-driven UART with a ring buffer for NMEA parsing and a custom STM32 ↔ ESP32 packet protocol. |
| **Deterministic Data Acquisition Engine** | Timer-triggered ADC sampling into a circular DMA buffer, processed on half- and full-transfer interrupts. |
| **BME280 Environmental Monitor** | I2C driver written from the datasheet, with calibration and compensation, timer-based sampling and UART output. |
| **Multi-Mode PWM Controller** | PWM, EXTI, UART commands and a matrix keypad, coordinated by a hierarchical state machine with fault override. |
| **Interrupt-Driven UART CLI** | Buffered command interface with echo, backspace handling and command parsing. |

---

## Skills

**Languages:** C
**Platforms:** STM32F4 (HAL, CubeMX, CubeIDE), ESP32-S3 (PlatformIO)
**Interfaces:** UART, SPI, I2C, ADC, DMA, timers/PWM, EXTI
**Focus:** interrupt-driven design, state machines, streaming data, sensor drivers, memory layout and boot flow
**Tools:** Git, ST-LINK, Linux
**Learning:** FreeRTOS, sensor fusion, linker scripts

---

Interested in embedded firmware, real-time systems, and low-level software.
