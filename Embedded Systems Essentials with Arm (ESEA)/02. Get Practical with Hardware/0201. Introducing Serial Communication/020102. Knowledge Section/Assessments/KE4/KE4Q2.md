---
module: "[[Introducing Serial Communication]]"
page_type: assessment
assessment_type: practice
assessment: KE4
question_number: 2
---
### Question:

An ADXL accelerometer is linked to a certain CMSIS device through its SPI port. CMSIS is initialized with the lines of code shown below.

```C

/* ---------------------------- SPI1 Pin Mapping ---------------------------- */
#define SPI1_CITO_PIN_ID   GPIO_PIN_ID_PORTA(7)   
#define SPI1_COTI_PIN_ID   GPIO_PIN_ID_PORTA(6)   
#define SPI1_SCLK_PIN_ID   GPIO_PIN_ID_PORTA(5)   
/* Chip Select */
#define ADXL_CS_PIN_ID     GPIO_PIN_ID_PORTB(6)   

/* -------------------------------------------------------------------------- */

void SPI1_Init(void)
{
    Driver_SPI1.Initialize(NULL);
    Driver_SPI1.PowerControl(ARM_POWER_FULL);

    
    Driver_SPI1.Control(ARM_SPI_MODE_MASTER |
                        ARM_SPI_CPOL1_CPHA1 |   /* Mode 3 */
                        ARM_SPI_DATA_BITS(8) |
                        ARM_SPI_MSB_LSB |
                        ARM_SPI_SS_MASTER_UNUSED,
                         2000000U);              
}

```

Write four lines of code to:

- set the SPI clock so that a 1-byte transmission takes 4 us
- select the accelerometer
- write 0x31 to the accelerometer
- deselect the accelerometer

### Answer:

Set the SPI Clock:

```C
Driver_SPI1.Control(ARM_SPI_SET_BUS_SPEED, 2000000U);
```

Select the accelerometer:
```C
Driver_GPIO0.SetOutput(ADXL_CS_PIN_ID, 0U);
```

Write to the accelerometer:
```C
Driver_SPI1.Send((uint8_t[]){0x31}, 1U);
```

Deselect the accelerometer:
```C
Driver_GPIO0.SetOutput(ADXL_CS_PIN_ID, 1U);
```

### Explanation:

- Eight bits need to be transmitted in 4 µs, so, set the bus speed to 2000000U: 
$$  
f = \frac{8\text{ bits}}{4\,\mu\text{s}}  

= 2{,}000{,}000\text{ bits/s}  

= 2\text{ MHz}  
$$
- SPI chip select is active-low as accelerometer is a target device, and according to CMSIS SPI documentation, target devices are active/selected when low. Therefore: 0U means selected and 1U means deselected.
- 1U in Driver_SPI1.Send() means send 1 data item. The U means the integer literal 1 is unsigned and the SPI has previously been configured so each data item is 8 bits.