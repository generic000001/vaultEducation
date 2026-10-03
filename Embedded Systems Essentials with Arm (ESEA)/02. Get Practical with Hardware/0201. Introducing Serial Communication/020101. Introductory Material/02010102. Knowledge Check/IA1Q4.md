---
page_type: assessment
assessment: "[[Knowledge Check - Initial Assessment]]"
question_number: 4
---
### Question

The following code fragment is written using CMSIS. If this code were running, identify the correct answer.

```c

...

SPI_A->Initialize(NULL);

SPI_A->PowerControl(ARM_POWER_FULL);

SPI_A->Control(ARM_SPI_MODE_MASTER |

               ARM_SPI_DATA_BITS(8) |

               ARM_SPI_SS_MASTER_SW,

               1000000);

SPI_A->Control(ARM_SPI_CONTROL_SS, ARM_SPI_SS_ACTIVE);

char c = 0x4F;

SPI_A->Send(&c, sizeof(c));

while (SPI_A->GetStatus().busy) { }

SPI_A->Control(ARM_SPI_CONTROL_SS, ARM_SPI_SS_INACTIVE);

...

```

### Answer

**The transmission of each byte takes 8 μs, the CS (Chip Select) line must be at logic 0 to activate the Target, the clock frequency is 1 MHz, and the number `0x4F` is the data output by the Controller.**

### Explanation

1. The SPI data width is configured as **8 bits**:

```c

ARM_SPI_DATA_BITS(8)

```

2. The SPI clock is configured to **1 MHz**:

```c

1000000

```

Therefore, one clock period is:

```text

T = 1 / f

  = 1 / 1,000,000

  = 1 μs

```

3. One byte contains 8 bits and therefore requires 8 clock cycles:

```text

8 bits × 1 μs/bit = 8 μs

```

The transmission of one byte therefore takes **8 μs**.

4. Software-controlled Target selection is configured using:

```c

ARM_SPI_SS_MASTER_SW

```

The Target is selected before transmission:

```c

SPI_A->Control(ARM_SPI_CONTROL_SS, ARM_SPI_SS_ACTIVE);

```

and deselected after transmission:

```c

SPI_A->Control(ARM_SPI_CONTROL_SS, ARM_SPI_SS_INACTIVE);

```

5. The value:

```c

char c = 0x4F;

```

is passed to:

```c

SPI_A->Send(&c, sizeof(c));

```

Therefore, `0x4F` is the **data being transmitted by the Controller**, not the address of the Target.
