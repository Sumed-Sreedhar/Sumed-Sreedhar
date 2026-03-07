# Hi, I’m Sumed

Instrumentation Engineering student focused on **embedded systems and firmware architecture**.

I build STM32-based projects to develop strong fundamentals in:

- Embedded C
- Interrupt-driven firmware design
- Deterministic timing and hardware-triggered systems
- Peripheral integration (GPIO, timers, ADC, DMA, UART)
- State-machine based firmware architecture
- Real-time embedded data pipelines

My work emphasizes **hardware-validated systems, deterministic behavior, strict ISR responsibility boundaries, and clean separation between event detection, time management, and hardware control.**

---

# Key Projects

### Deterministic Data Acquisition Engine
A hardware-driven real-time data acquisition pipeline using **timer-triggered ADC sampling and DMA circular buffering**.

Key concepts demonstrated:
- Timer-triggered deterministic sampling
- ADC conversion timing analysis
- Peripheral-to-memory DMA transfers
- Circular buffer streaming architecture
- Half-transfer / full-transfer interrupt processing
- Real-time throughput and processing window analysis

Architecture:

```
Timer → ADC → DMA → Circular Buffer → CPU Processing
```

This design mirrors acquisition pipelines used in **sensor systems, signal monitoring, and embedded instrumentation**.

---

### Multi-Mode PWM LED Control System

Integrated multi-peripheral firmware system implementing:

- Hardware PWM brightness control (TIM3)
- Timer-driven system tick scheduler (TIM2)
- EXTI-based mode switching and fault detection
- UART CLI brightness control
- 4×3 matrix keypad input
- Auto-ramp brightness algorithm
- Hierarchical state machine with fault override

Demonstrates **coordinated peripheral control, deterministic timing, and structured firmware architecture**.

---

### Interrupt-Driven UART Command Line Interface

UART command interface built using **interrupt-driven RX and buffered command parsing**.

Key concepts demonstrated:

- Interrupt-driven serial reception
- Line buffering and message framing
- Echo and backspace handling
- ISR-to-main-loop data handoff
- Deterministic command processing

This project establishes a reusable foundation for **embedded system configuration interfaces and debugging tools**.

---

### Interrupt-Driven LED Pattern Controller

Firmware system implementing **hierarchical state-machine control** using:

- EXTI interrupts for event-driven mode transitions
- Timer interrupts for deterministic pattern timing
- Counter-based non-blocking timing logic

Demonstrates how embedded firmware can implement **predictable multi-mode behavior without blocking delays**.

---

### Event-Driven LED Controller

Early event-driven firmware project demonstrating separation between:

- **event detection (EXTI)**
- **time-based execution (timer interrupts)**

This project established the architectural foundation for later **state-machine-based firmware designs**.

---

# Tools & Platforms

- **STM32 (STM32F446RE)**
- **Embedded C**
- **STM32 HAL**
- **Linux**
- **Git & GitHub**
