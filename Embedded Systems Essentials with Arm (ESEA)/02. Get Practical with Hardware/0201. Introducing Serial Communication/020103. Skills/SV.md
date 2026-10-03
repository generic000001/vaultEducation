
STM32 Nucleo-F401RE (Nucleo)
TI SN74HC595N 8-bit Shift Register (SR)
Breadboard (Bread)

Nucleo 3V3 -- Bread + (LHS)
Nucleo GND -- Bread - (LHS)

Bread + (LHS) -- Bread + (RHS)
Bread - (LHS) -- Bread - (RHS)

GreenLED1 Anode (+) -- Bread + (LHS)
GreenLED1 Cathode (-) -- Bread - (LHS)

GreenLED2 Cathode (-) -- Bread - (LHS)
RedLED1 Cathode (-) -- Bread - (LHS)

Bread + (RHS) -- SR VCC (16)
Nucleo PA7/PWM/MOSI/D11 -- SR SER (14)
Bread - (RHS) -- SR OE (13)
Nucleo PB6/PWM/CS/D10 -- SR RCLK (12)
Nucleo PA5/SCK/D13 -- SR SRCLK (11)
Bread + (LHS) -- SR SRCLR (10)
Bread - (RHS) -- SR GND (8)

GreenLED2 Anode (+) -- SR QD (3)
RedLED1 Anode (+) -- SR QC (2)

  

Nucleo 3V3 -- Bread + (LHS)  
Nucleo GND -- Bread - (LHS)  

Bread + (LHS) -- Bread + (RHS)  
Bread - (LHS) -- Bread - (RHS)  

GreenLED1 Anode (+) -- Bread + (LHS)  
GreenLED1 Cathode (-) -- Bread - (LHS)  

GreenLED2 Cathode (-) -- Bread - (LHS)  
RedLED1 Cathode (-) -- Bread - (LHS)  

Bread + (RHS) -- SR VCC (16)  
Nucleo PB15/SPI2_MOSI/CN7-28 -- SR SER (14)  
Bread - (RHS) -- SR OE (13)  
Nucleo PB6/PWM/CS/D10 -- SR RCLK (12)  
Nucleo PB13/SPI2_SCK/CN7-26 -- SR SRCLK (11)  
Bread + (LHS) -- SR SRCLR (10) 
Bread - (RHS) -- SR GND (8)

GreenLED2 Anode (+) -- SR QD (3)
RedLED1 Anode (+) -- SR QC (2)