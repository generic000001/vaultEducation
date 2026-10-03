---
module: "[[Introducing Serial Communication]]"
page_type: assessment
assessment_type: practice
assessment: KE4
question_number: 1
---
### Question:

A CMSIS program using an SPI port contains the lines shown.

```C

/* --------------------------- SPI1 Pin Mapping --------------------------- */

#define SPI1_CITO_PIN_ID   GPIO_PIN_ID_PORTA(7)
#define SPI1_COTI_PIN_ID   GPIO_PIN_ID_PORTA(6)
#define SPI1_SCLK_PIN_ID   GPIO_PIN_ID_PORTA(5)

/* ------------------------------------------------------------------------- */

static void SPI1_Init_CMSIS(void)  
{  
    Driver_SPI1.Initialize(NULL);  
    Driver_SPI1.PowerControl(ARM_POWER_FULL);  
    Driver_SPI1.Control(ARM_SPI_MODE_MASTER |  
                        ARM_SPI_CPOL0_CPHA1 |     
                        ARM_SPI_DATA_BITS(8) |  
                        ARM_SPI_MSB_LSB |  
                        ARM_SPI_SS_MASTER_UNUSED,  
                        2500000U);                
  
    Driver_SPI1.Control(ARM_SPI_SET_DEFAULT_TX_VALUE, 0x00U);  
}

```

### Answer:

COTI is PA6, SCLK is PA5, format is 8 bit, data is clocked in on falling clock edge, clock idles low, clock frequency is 2.5 MHz.

### Explanation:

- COTI is PA6, because SPI1_COTI_PIN_ID is mapped to GPIO_PIN_ID_PORTA(6).

- SCLK is PA5, because SPI1_SCLK_PIN_ID is mapped to GPIO_PIN_ID_PORTA(5).

- The data format is 8-bit because the data width is configured with ARM_SPI_DATA_BITS(8).

- Data is clocked in on the falling clock edge, because Clock Polarity (CPOL) = 0 **AND** Clock Phase (CPHA) = 1.

- Clock idles low, because Clock Polarity (CPOL) = 0.

- Clock Frequency is 2.5MHz, because value is 2500000U.

| CPOL | CPHA | Idle | Sampling edge |
| ---- | ---- | ---- | ------------- |
| 0    | 0    | Low  | **Rising**    |
| 0    | 1    | Low  | **Falling**   |
| 1    | 0    | High | **Falling**   |
| 1    | 1    | High | **Rising**    |
