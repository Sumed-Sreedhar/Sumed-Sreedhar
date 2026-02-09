# Hi, I’m Sumed

Instrumentation Engineering student focused on **embedded systems**.

I’m currently building STM32-based projects to strengthen fundamentals in:
- Embedded C
- GPIO, EXTI, and timer interrupts
- UART communication and serial interfaces
- Polling vs interrupt-driven design
- State-based, event-driven, and time-driven system architecture

My work emphasizes **hardware-validated designs**, clean interrupt handling, and understanding how embedded systems behave under real constraints.

---

## Projects

### GPIO-Driven Status Controller
Foundational project exploring GPIO configuration, polling vs interrupts, software debouncing, and interrupt flow to understand basic input/output handling on STM32.

### Event-Driven LED Controller
Event-driven design using EXTI for input handling and timer interrupts for output control, demonstrating clear separation between event detection and time-based execution.

### Interrupt-Driven LED Pattern Controller
STM32-based interrupt-driven LED pattern controller using EXTI for mode transitions and TIM interrupts for deterministic, non-blocking pattern execution. Implements hierarchical state behavior, counter-based timing logic, and strict peripheral ownership to ensure predictable firmware behavior.

### Mode Timeout Controller
Interrupt- and timer-driven controller demonstrating **time-based state decay**. Modes automatically expire after a fixed duration without further user input, combining event-driven transitions (EXTI) with time-driven enforcement (TIM) to manage state lifetime deterministically.

### Interrupt-Driven UART Command Line Interface
UART-based command line interface built on STM32 using interrupt-driven RX, line buffering, and command parsing. Demonstrates safe ISR–main loop separation, message framing, and deterministic command dispatch, serving as a foundation for future DMA-based and bare-metal UART work.

More projects will be added as I continue building.

---

## Tools & Platforms
- STM32 (STM32F446RE)
- Embedded C
- STM32 HAL
- Linux
- Git & GitHub
