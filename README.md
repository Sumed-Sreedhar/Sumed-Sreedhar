# Hi, I'm Sumed

Electronics & Instrumentation Engineering student focused on **embedded systems, firmware architecture, and real-time embedded communication systems**.

I build STM32-based systems to develop strong fundamentals in:

* Embedded C
* Interrupt-driven firmware design
* Deterministic timing and hardware-triggered systems
* Peripheral integration (GPIO, Timers, ADC, DMA, UART, I2C, PWM)
* Sensor interfacing and embedded communication protocols
* State-machine-based firmware architecture
* Inter-MCU communication systems
* Real-time telemetry pipelines
* Streaming data architectures
* Embedded networking integration

My work emphasizes **hardware-validated systems, deterministic behavior, clean ISR ownership, modular driver design, robust communication architectures, and structured data flow from acquisition through telemetry.**

---

# Key Projects

## Road Surface Monitoring Device

A distributed embedded telemetry system built around STM32F446RE and ESP32-S3 for real-time road anomaly detection, GPS localization, event classification, and cloud telemetry.

Unlike a typical sensor project, this system focuses heavily on **data movement architecture, communication design, and telemetry pipelines**, integrating multiple sensing and communication subsystems into a complete end-to-end embedded system.

### Key Contributions

* Designed overall firmware architecture and subsystem integration
* Developed interrupt-driven GPS reception using UART
* Implemented ring-buffer-based streaming architecture for continuous NMEA processing
* Built NMEA sentence reconstruction and parsing logic
* Designed STM32 ↔ ESP32 inter-MCU communication protocol
* Implemented structured telemetry packet generation
* Integrated IMU shock detection with GPS localization
* Integrated ultrasonic measurements into anomaly classification
* Developed event-driven telemetry generation
* Implemented embedded-to-cloud telemetry architecture
* Integrated multiple communication interfaces within a single system

### Technical Concepts Demonstrated

* Interrupt-driven UART architecture
* Ring buffer design
* Producer-consumer systems
* Stream-oriented protocol handling
* Inter-MCU communication
* Packet-based telemetry systems
* Real-time event pipelines
* Multi-sensor integration
* GPS telemetry systems
* Embedded networking integration
* Distributed embedded architecture
* Modular firmware design

### System Architecture

```text
LSM6DS3 IMU
HC-SR04
NEO-6M GPS
     │
     ▼
STM32F446RE
(Sensor Processing)
     │
     ▼
Road Event Classification
     │
     ▼
Telemetry Packet Generation
     │
     ▼
UART Inter-MCU Link
     │
     ▼
ESP32-S3
(Communication Gateway)
     │
     ▼
HTTP Telemetry Upload
     │
     ▼
Backend Server
```

This project demonstrates the complete path from sensor acquisition to cloud telemetry, including communication architecture, protocol design, data streaming, and distributed embedded system integration.

---

## STM32 Deterministic GPS Telemetry Node

Real-time GPS telemetry system using the NEO-6M GPS module with interrupt-driven UART reception, ring buffer streaming, and structured NMEA parsing.

### Key Concepts Demonstrated

* Interrupt-driven UART reception
* Ring buffer architecture
* Producer-consumer data flow
* NMEA sentence reconstruction
* GPS protocol parsing
* Multi-UART firmware design
* Real-time telemetry pipelines
* Coordinate extraction and formatting
* Non-blocking serial communication

### Architecture

```text
GPS Module
     │
     ▼
UART RX Interrupt
     │
     ▼
Ring Buffer
     │
     ▼
NMEA Parser
     │
     ▼
Structured Telemetry Output
```

Demonstrates real-world stream-oriented communication handling and telemetry system design.

---

## BME280 I2C Environmental Monitoring System

Complete sensor-integrated embedded system using the BME280 over I2C with timer-driven sampling and interrupt-based UART reporting.

### Key Concepts Demonstrated

* I2C bus bring-up and debugging
* Register-level sensor configuration
* Datasheet-driven firmware development
* Calibration coefficient loading
* Raw ADC reconstruction
* Compensation algorithms
* Timer-scheduled acquisition
* Non-blocking UART transmission
* Modular driver architecture

### Architecture

```text
TIM2
 │
 ▼
Sample Scheduler
 │
 ▼
I2C Sensor Read
 │
 ▼
Compensation Processing
 │
 ▼
UART Telemetry
```

Demonstrates sensor interfacing, protocol reasoning, and complete embedded system integration.

---

## Deterministic Data Acquisition Engine

A hardware-driven real-time acquisition pipeline using timer-triggered ADC sampling and DMA circular buffering.

### Key Concepts Demonstrated

* Timer-triggered deterministic sampling
* ADC conversion timing analysis
* DMA circular buffering
* Peripheral-to-memory transfers
* Half-transfer interrupt processing
* Full-transfer interrupt processing
* Real-time throughput analysis
* Continuous streaming architectures

### Architecture

```text
Timer
  │
  ▼
ADC
  │
  ▼
DMA
  │
  ▼
Circular Buffer
  │
  ▼
CPU Processing
```

Mirrors acquisition systems used in instrumentation, sensing, and embedded monitoring applications.

---

## Multi-Mode PWM LED Control System

A multi-peripheral firmware project integrating several STM32 subsystems under a hierarchical state-machine architecture.

### Integrated Subsystems

* TIM3 PWM brightness control
* TIM2 scheduler
* EXTI mode switching
* EXTI fault detection
* UART command interface
* Matrix keypad input
* Auto-ramp control
* Fault override logic

### Key Concepts Demonstrated

* Peripheral integration
* State-machine architecture
* Interrupt-driven control
* Deterministic scheduling
* Event-driven firmware design
* Fault handling systems
* Coordinated subsystem interaction

Demonstrates structured firmware design for complex embedded applications.

---

## Interrupt-Driven UART Command Line Interface

UART command interface built using interrupt-driven reception and buffered command parsing.

### Key Concepts Demonstrated

* Interrupt-driven serial communication
* Message framing
* Buffered reception
* Echo and backspace handling
* ISR-to-main-loop communication
* Command parsing
* Deterministic execution

Provides a reusable foundation for embedded debugging and configuration interfaces.

---

# Technical Focus Areas

* Embedded C
* Real-Time Embedded Systems
* Firmware Architecture
* UART Communication Systems
* Inter-MCU Communication
* Streaming Data Architectures
* Embedded Telemetry
* GPS Systems
* Sensor Integration
* DMA-Based Data Acquisition
* Interrupt-Driven Design
* State Machine Design
* Embedded Networking
* Hardware/Software Co-Design

---

# Tools & Platforms

### Hardware

* STM32F446RE
* ESP32-S3
* NEO-6M GPS
* LSM6DS3 IMU
* BME280
* HC-SR04

### Software

* Embedded C
* STM32 HAL
* STM32CubeIDE
* PlatformIO
* Linux
* Git
* GitHub

### Protocols & Interfaces

* UART
* I2C
* DMA
* PWM
* ADC
* EXTI
* HTTP
* Wi-Fi

---

# Current Direction

Currently focused on expanding expertise in:

* Advanced STM32 firmware development
* Communication architecture design
* Real-time telemetry systems
* Embedded networking
* Sensor fusion systems
* Distributed embedded systems
* Embedded data pipelines
* Deterministic firmware architecture

Interested in firmware engineering, embedded software development, real-time systems, and embedded communication infrastructure.
