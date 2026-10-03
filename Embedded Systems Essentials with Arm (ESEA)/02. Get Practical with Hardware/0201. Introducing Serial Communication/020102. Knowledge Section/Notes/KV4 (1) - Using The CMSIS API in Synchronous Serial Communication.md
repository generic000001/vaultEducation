---
module: "[[Introducing Serial Communication]]"
page_type: note
note: KV4 (1) - Using The CMSIS API in Synchronous Serial Communication
---

**Watch this video** to learn how to implement simple synchronous serial links in physical environments using the CMSIS API.

Please note that the terms SCL and SCK are used interchangeably in the video.
### Transcript:

This video looks at how an embedded device can be configured as an SPI, serial peripheral interface controller or target. More often, you want your device to be a controller, because this allows you to manage the communication. With other devices, you don't have the ability to control the communication.

These are some, but not all, of the functions that the CMSIS API provides to the SPI peripheral as a controller. The SPI interface can be used to write data words out from the SPI port and return the data from the SPI target. It's possible to configure the SPI clock frequency and format to suit specific requirements. In addition to the frequency, the controller can also configure the mode. The mode is feature of SPI that allows you to choose which clock edge is used to clock data into the shift register, this is indicated as data strobe in the diagram. Mode determines whether it's the rising edge, or the falling edge which clocks the data. In this diagram, Mode 0 is the rising edge, and Mode 1 is the falling edge.

This example shows an SPI controller being configured. A single byte is sent to the selected target, which then responds with the requested ID byte. Here we define the SPI interface used on the embedded system. In our test function, we start by initializing the interface and turning its power on. Then we set up the format and communication frequency. Next, we activate the chip select line, then issue the transfer. When the transfer is complete, the callback function will be invoked.

Here we deactivate the chip select line and print out the result. This is an example of device we can use with SPI. This is a 3-axis accelerometer placed a breakout board. It has COTI, CITO and serial clock pins which give it SPI capability. The other pins shown extend its capability beyond SPI.

CMSIS also has good capability for application with UARTs. CMSIS can set up the standard characteristics such as board rate, data length, the use of parity, and number of stop bits. If you don't want to configure these manually, you can use the default settings for your chosen microcontroller, usually 9600 8N1. This translates to 9600 bits per second, eight data bits, no parity, and one stop bit. This example shows an extract of a program which configures a serial port and repeats back any data received.