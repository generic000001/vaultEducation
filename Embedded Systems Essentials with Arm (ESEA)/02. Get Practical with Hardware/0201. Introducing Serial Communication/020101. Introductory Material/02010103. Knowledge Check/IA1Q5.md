---
page_type: assessment
assessment: "[[Knowledge Check]]"
question_number: 5
---
### Question

When designing with microcontrollers, it is important to recognise and evaluate the relative advantages of different serial protocols. Identify the correct statements below.

1. SPI is widely used in motor vehicle applications due to its inherent high reliability.

2. UARTs are often associated with the transmission of textual data, in which case ASCII coding is applied.

3. SPI's advantages are particularly felt with multi-node applications, as the same CS (Chip Select) line can be connected to all Target nodes.

4. A UART port's hardware is a little more complex than that of SPI, as each UART must generate its own clock and synchronise it with incoming data.

5. The data framing bits of a UART signal help streamline the communication, making it faster than SPI of equivalent clock frequency.

### Answer

The two correct statements are:

- **UARTs are often associated with the transmission of textual data, in which case ASCII coding is applied.**

- **A UART port's hardware is a little more complex than that of SPI, as each UART must generate its own clock and synchronise it with incoming data.**

### Explanation

1. SPI is useful for short-distance communication between devices, but the statement that its defining advantage is inherent high reliability for motor vehicle applications is not correct here.

2. UART is commonly used to transmit textual information. Characters can be represented using **ASCII values** and transmitted as serial data.

3. In a conventional multi-Target SPI arrangement, Targets generally require **separate Chip Select signals** so that the Controller can select the intended Target:

```text

                    ┌── CS1 ──► Target 1

Controller ─────────┼── CS2 ──► Target 2

                    └── CS3 ──► Target 3

SCK  ────────────────────────► Targets

COTI ────────────────────────► Targets

CITO ◄──────────────────────── Targets

```

4. UART does not receive a shared clock signal in the way a synchronous SPI connection does. Each UART therefore needs local timing and must synchronise reception using the incoming UART frame.

5. UART framing introduces **additional transmitted bits**, such as start and stop bits. These are overhead rather than making UART inherently faster than SPI at an equivalent bit or clock rate.
