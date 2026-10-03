---
page_type: assessment
assessment: "[[Knowledge Check - Initial Assessment]]"
question_number: 1
---
### Question

Serial data communication is an important feature of the embedded system landscape. Identify the one statement that is **not correct**.

1. The serial receiver and transmitter are usually based on a shift register; this can clock in serial data at its input or clock it out at its output.

2. In asynchronous serial communication, the clock frequency is agreed in advance and is then generated locally within the receiver or transmitter.

3. A shift register allows data to be converted from serial to parallel form.

4. In synchronous serial communication, the clock signal is generated in the Target, and then connected to the Controller.

5. Serial data communication demands fewer interconnecting wires when compared to parallel communication.

### Answer

**In synchronous serial communication, the clock signal is generated in the Target, and then connected to the Controller.**

### Explanation

1. Serial receivers and transmitters can use **shift registers** to shift individual bits serially into or out of the device.

2. In **asynchronous serial communication**, a separate clock signal is not transmitted between the devices. The communication rate is agreed in advance and timing is generated locally.

3. A shift register can perform **serial-to-parallel conversion**, accumulating incoming serial bits into a parallel value.

4. The selected statement is incorrect because in a synchronous Controller/Target arrangement such as SPI, the **Controller generates the clock**, not the Target.

5. Serial communication generally requires fewer signal connections than transmitting multiple bits simultaneously over a parallel bus.
