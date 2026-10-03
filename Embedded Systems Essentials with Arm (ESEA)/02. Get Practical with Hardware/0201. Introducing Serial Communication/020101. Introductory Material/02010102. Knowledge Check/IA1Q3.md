---
page_type: assessment
assessment: "[[Knowledge Check - Initial Assessment]]"
question_number: 3
---
### Question

A UART sends data that is formatted in a particular way. Identify the one correct statement.

1. Every byte transmitted by a UART is framed by a start bit and a stop bit.

2. It is a requirement that the data byte is always followed by a parity bit.

3. Multiple bytes can be sent in sequence by the UART, with a start bit at the start of the first and a stop bit at the end of the last.

4. Standard terminology for UART connections are RX and TX; when forming a link between two nodes, each node's TX and RX should be connected.

5. The baud rate can change from one byte to the next. The receiver will adapt to the change.

### Answer

**Every byte transmitted by a UART is framed by a start bit and a stop bit.**

### Explanation

1. UART is **asynchronous**, so each transmitted character is framed to allow the receiver to synchronise with it. A frame begins with a **start bit** and ends with one or more **stop bits**.

2. A **parity bit is optional**. UART can operate without parity.

3. Each character requires its own framing. A stream of bytes does not ordinarily share one start bit and one stop bit around the entire sequence.

4. UART uses **TX** and **RX**, with the transmitter of one device connected to the receiver of the other:

```text

Device A TX ──────► Device B RX

Device A RX ◄────── Device B TX

```

5. The transmitter and receiver must use compatible communication rates. The receiver does not simply adapt to arbitrary baud-rate changes between bytes.

A typical UART frame can be visualised as:

```text

Idle │ Start │ Data bits │ Optional parity │ Stop │ Idle

     │   0   │ d0 ... d7 │       P         │  1   │

```
