<h1 align="center">Hi, I'm Sumed 👋</h1>

<p align="center">
  Embedded firmware developer working with STM32 microcontrollers.<br/>
  I like the layer where software meets hardware: interrupts, DMA, communication protocols,<br/>
  and firmware that stays <b>predictable when something goes wrong</b>.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/MCU-STM32F446RE-03234B?logo=stmicroelectronics&logoColor=white" />
  <img src="https://img.shields.io/badge/Core-Cortex--M4-0091BD" />
  <img src="https://img.shields.io/badge/Language-C-A8B9CC?logo=c&logoColor=black" />
  <img src="https://img.shields.io/badge/Python-tooling-3776AB?logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Focus-Boot%20%26%20Reliability-orange" />
</p>

> 🎓 3rd-year Electronics & Instrumentation Engineering student, Bengaluru
> 🎯 Targeting embedded firmware roles in automotive and mobility

---

## 🚧 In Progress

### 🛰️ STM32 Flight Computer
*Under active development* · [**View repository →**](https://github.com/Sumed-Sreedhar/STM32-Embedded-Flight-Computer)

A flight computer on the STM32F446RE that reads an IMU, magnetometer, barometer and GPS, estimates orientation and altitude, and logs flight data to an SD card. The goal is one coherent firmware architecture, not a pile of separate sensor demos.

- **Sensors:** MPU6500 (IMU), MLX90393 (magnetometer), BMP280 (barometer), NEO-6M (GPS)
- **Firmware:** sensor drivers over SPI/I2C/UART, self-test and fault handling, Mahony filter for attitude, PID control, FatFS logging
- **Structure:** a flight state machine first as a bare-metal loop, then ported to FreeRTOS tasks

```text
BOOT → SELF_TEST → INIT → READY → ARMED → FLIGHT → LANDING → SHUTDOWN
                  any fault (GPS, IMU, SD, UART) → FAULT
```

### 🔐 Custom Bootloader (STM32F446RE)
*Under active development* · [**View repository →**](https://github.com/Sumed-Sreedhar/STM32F446-Custom-Bootloader)

A bootloader that stays resident in flash, **validates** a separately linked application, and only then hands over control. It covers the parts of startup that normally stay hidden: flash partitioning, linker layout, image integrity, and the handoff into the application's reset handler.

```text
0x08000000  Bootloader          32 KB
0x08008000  Application Header  16 KB   magic · size · CRC-32
0x0800C000  Application Image  464 KB   vector table starts here
```

**Working today**
- Separate bootloader and application projects with custom flash partitioning and a dedicated `.header` linker section
- Application linked at a non-default address, with vector table relocation by the application
- Image validation before every boot: **magic number → reset handler → size → hardware CRC-32**, each failure reported with its own code over UART
- Header-free binary generation (`objcopy --remove-section=.header`) and a Python utility that reproduces the STM32 hardware CRC convention for size and checksum metadata
- Controlled handoff: interrupts disabled, SysTick stopped, MSP loaded, jump to the application's reset handler
- Verified on hardware: valid image boots, corrupted CRC is rejected, bad magic number is rejected

**Next**
- Stricter vector-table checks, automated header generation, and full negative-test coverage
- A firmware update path, version metadata, and dual-image fallback
- Fault-aware boot, with the goal of hosting the flight computer firmware so it can be updated and recovered without a debugger

---

## 📦 Previous Work

| Project | What it does |
|---|---|
| **Road Surface Monitoring Device** | STM32F446RE + ESP32-S3. Detects road anomalies with an IMU and ultrasonic sensor, tags them with GPS, and uploads them over Wi-Fi. Uses interrupt-driven UART with a ring buffer for NMEA parsing and a custom STM32 ↔ ESP32 packet protocol. |
| **Deterministic Data Acquisition Engine** | Timer-triggered ADC sampling into a circular DMA buffer, processed on half- and full-transfer interrupts. |
| **BME280 Environmental Monitor** | I2C driver written from the datasheet, with calibration and compensation, timer-based sampling and UART output. |
| **Multi-Mode PWM Controller** | PWM, EXTI, UART commands and a matrix keypad, coordinated by a hierarchical state machine with fault override. |
| **Interrupt-Driven UART CLI** | Buffered command interface with echo, backspace handling and command parsing. |

---

## 🛠️ Skills

| | |
|---|---|
| **Languages** | C, Python (build and host-side tooling) |
| **Platforms** | STM32F4 (CubeProgrammer, HAL, CubeMX, CubeIDE), ESP32-S3 (PlatformIO) |
| **Interfaces** | UART, SPI, I2C, ADC, DMA, timers/PWM, EXTI, hardware CRC |
| **Focus** | Interrupt-driven design, state machines, streaming data, sensor drivers, memory layout, linker scripts, boot flow and image validation |
| **Tools** | Git, ST-LINK, GNU Arm toolchain (`objcopy`, `objdump`), logic analyzer, Linux |
| **Learning** | FreeRTOS, sensor fusion, fault-tolerant boot and recovery |

---

<p align="center">
  Interested in embedded firmware, real-time systems, and low-level software.<br/>
  <a href="https://github.com/Sumed-Sreedhar?tab=repositories">Browse my repositories</a>
</p>
