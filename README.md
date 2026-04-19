# Hi, I’m Sumed

Electronincs & Instrumentation Engineering student focused on **embedded systems and firmware architecture**.

I build STM32-based systems to develop strong fundamentals in:

- Embedded C
- Interrupt-driven firmware design
- Deterministic timing and hardware-triggered systems
- Peripheral integration (GPIO, timers, ADC, DMA, UART, I2C, PWM)
- Sensor interfacing and embedded communication protocols
- State-machine-based firmware architecture
- Real-time embedded data pipelines

My work emphasizes **hardware-validated systems, deterministic behavior, strict ISR responsibility boundaries, and clean separation between event detection, time management, data flow, and hardware control.**

---

# Key Projects

### BME280 I2C Environmental Monitoring System

Complete sensor-integrated embedded system using the **BME280 over I2C** with timer-driven sampling and interrupt-based UART reporting.

**Key concepts demonstrated:**
- I2C bus bring-up and debugging
- Register-based sensor configuration
- Datasheet-driven firmware development
- Calibration coefficient loading
- Raw ADC data reconstruction
- Compensation algorithms for temperature, pressure, and humidity
- Timer-scheduled sampling
- Non-blocking UART transmission
- Modular driver architecture

**Architecture:**  
TIM2 → Sample Flag → I2C Sensor Read → Compensation Math → UART Output

Demonstrates real-world **sensor interfacing, protocol reasoning, and end-to-end embedded system integration**.

---

### Deterministic Data Acquisition Engine

A hardware-driven real-time data acquisition pipeline using **timer-triggered ADC sampling and DMA circular buffering**.

**Key concepts demonstrated:**
- Timer-triggered deterministic sampling
- ADC conversion timing analysis
- Peripheral-to-memory DMA transfers
- Circular buffer streaming architecture
- Half-transfer / full-transfer interrupt processing
- Real-time throughput and processing window analysis

**Architecture:**  
Timer → ADC → DMA → Circular Buffer → CPU Processing

This design mirrors acquisition pipelines used in **sensor systems, signal monitoring, and embedded instrumentation**.

---

### Multi-Mode PWM LED Control System

A multi-peripheral firmware system integrating:

- Hardware PWM brightness control (TIM3)
- Timer-driven system tick scheduler (TIM2)
- EXTI-based mode switching and fault detection
- UART CLI-based brightness control
- 4×3 matrix keypad input
- Auto-ramp brightness control
- Hierarchical state machine with fault override

Demonstrates **coordinated peripheral control, deterministic timing, and structured firmware architecture**.

---

### Interrupt-Driven UART Command Line Interface

UART command interface built using **interrupt-driven reception and buffered command parsing**.

**Key concepts demonstrated:**
- Interrupt-driven serial communication
- Line buffering and message framing
- Echo and backspace handling
- ISR-to-main-loop data transfer
- Deterministic command execution

Forms a reusable foundation for **embedded configuration interfaces and debugging tools**.

---

### Interrupt-Driven LED Pattern Controller

Firmware system implementing **hierarchical state-machine control** using:

- EXTI interrupts for event-driven transitions
- Timer interrupts for deterministic timing
- Counter-based non-blocking execution

Demonstrates **predictable multi-mode behavior without blocking delays**.

---

# Tools & Platforms

- **STM32 (STM32F446RE)**
- **Embedded C**
- **STM32 HAL**
- **Linux**
- **Git & GitHub**
