# Hi, I’m Sumed

Instrumentation Engineering student focused on **embedded systems and firmware architecture**.

I build STM32-based projects to develop strong fundamentals in:

- Embedded C
- GPIO, EXTI, and timer interrupts
- Hardware PWM (duty-cycle control)
- UART communication and interrupt-driven serial interfaces
- Matrix keypad scanning
- Fault handling and safety state design
- Polling vs interrupt-driven systems
- State-based, event-driven, and time-driven architectures

My work emphasizes **hardware-validated designs**, strict ISR responsibility boundaries, deterministic timing, and clean separation between event detection, time management, and hardware control.

---

## Projects

### GPIO-Driven Status Controller  
Foundational project exploring GPIO configuration, polling vs interrupts, software debouncing, and interrupt flow to understand basic input/output handling on STM32.

### Event-Driven LED Controller  
Event-driven design using EXTI for input handling and timer interrupts for output control, demonstrating separation between event detection and time-based execution.

### Interrupt-Driven LED Pattern Controller  
Hierarchical state-machine implementation using EXTI for mode transitions and TIM interrupts for deterministic, non-blocking pattern execution. Introduces structured state layering and counter-based timing logic.

### Mode Timeout Controller  
Interrupt- and timer-driven controller demonstrating **time-based state decay**. Modes automatically expire after fixed durations, combining event-driven transitions with timer-enforced state lifetime management.

### Interrupt-Driven UART Command Line Interface  
UART-based CLI using interrupt-driven RX, line buffering, echo handling, backspace support, and command parsing. Demonstrates ISR-to-main-loop handoff, message framing, and safe command dispatch architecture.

### Multi-Mode PWM LED Control System  
Integrated firmware system combining:
- Hardware PWM (TIM3)
- Timer-based system tick (TIM2)
- EXTI-based mode control and fault handling
- 4x3 matrix keypad scanning
- UART CLI brightness control
- Auto-ramp brightness algorithm
- Hierarchical state machine with fault override layer

Demonstrates multi-peripheral coordination, deterministic timing, non-blocking control logic, and structured state transitions in a hardware-validated environment.

More projects will be added as I continue building.

---

## Tools & Platforms
- STM32 (STM32F446RE)
- Embedded C
- STM32 HAL
- Linux
- Git & GitHub
