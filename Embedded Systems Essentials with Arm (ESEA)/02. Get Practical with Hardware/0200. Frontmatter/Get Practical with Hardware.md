---
program: "[[Embedded Systems Essentials with Arm (ESEA)]]"
page_type: course
course_number: "02"
---
# Course Material Overview and Navigation

## Course Overview

For learners with undergraduate-level engineering knowledge and basic C/C++ skills, this course provides hands-on experience with serial communication, RTOSs, microcontroller peripherals, and CMSIS APIs on the **ST Nucleo F401RE**.

---
## What the Course Covers

### 1. Serial Communication

Explore serial communication technologies with the **CMSIS API**.

### 2. Real-Time Operating Systems (RTOS)

Learn RTOS fundamentals and their support in **CMSIS**.

### 3. Microcontroller Peripherals

Control these peripherals through the **CMSIS API**:

- Digital I/O
- Analogue I/O
- Interrupts
- Pulse-width modulation (PWM)
- Timers

### 4. CMSIS-RTOS in Practice

Use **CMSIS-RTOS APIs** to build a music player on the **ST Nucleo F401RE**.

---
### I2C and SPI Terminology

In the context of **I2C** and **SPI**, the course uses:

| Current terminology | Previous terminology |
|---|---|
| Controller | Master |
| Target | Slave |
| CITO | MISO |
| COTI | MOSI |

The course therefore uses **Controller** and **Target**, with the related signal terminology **CITO** and **COTI**.

---
## Course Learning Journey

```text
Serial communication technologies
        ↓
CMSIS communication APIs
        ↓
RTOS fundamentals
        ↓
Microcontroller peripherals
        ↓
Digital & analogue I/O, interrupts, PWM & timers
        ↓
CMSIS-RTOS APIs
        ↓
Music player project on the ST Nucleo F401RE
```

## Key Takeaway

> The course combines embedded systems theory with practical work on the ST Nucleo F401RE, covering serial communication, RTOS concepts, microcontroller peripherals, and the CMSIS APIs used to control and coordinate them.