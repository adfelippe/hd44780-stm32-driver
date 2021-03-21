# hd44780-stm32-driver
## STM32 driver for LCDs running with the HD44780 controller
### Port for use with STM HAL libraries

This driver is just a port from the one developed by Tilen Majerle and available [here](https://github.com/MaJerle/stm32fxxx-hal-libraries). It is intended to be used with STM HAL libraries.

The library uses 4-bit mode to control the LCD. The only configuration needed is to set the correct pins from your project in the `stm32_hd44780.h` file.

Usage example with a 16x2 LCD:

```
#include "stm32_hd44780.h"

int main(void)
{
    /* Initialize 16x2 LCD */
    HD44780_Init(16, 2);

    /* Write string to LCD */
    HD44780_Puts(0, 0, "LCD Test");
    HD44780_Puts(0, 1, "Test line 2!");

    HAL_Delay(3000);

    /* Clear LCD */
    HD44780_Clear();
    
    /* Show cursor */
    HD44780_CursorOn();
    
    /* Write new text */
    HD44780_Puts(0, 0, "LCD cleared!");
    
    HAL_Delay(1000);

    * Enable cursor blinking */
    HD44780_BlinkOn();
}
```
