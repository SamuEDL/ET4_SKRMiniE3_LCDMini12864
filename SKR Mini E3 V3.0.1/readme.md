Klipper

LCD config

```
[display]
lcd_type: uc1701
cs_pin: PD2
a0_pin: PC0 #a0 is LCD_A0
rst_pin: PB4
encoder_pins: ^PA10,^PA9
click_pin: ^!EXP1_1
contrast: 63
spi_software_sclk_pin: PA5
spi_software_mosi_pin: PA7
spi_software_miso_pin: PA6

[neopixel btt_mini12864]
pin: PB14
chain_count: 3
color_order: RGB
initial_RED: 0.4
initial_GREEN: 0.05
initial_BLUE: 0.0
```
