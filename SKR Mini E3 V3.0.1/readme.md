| SKR Mini E3 v3.0.1 (PORT: pin) | Mini 12864(PORT: pin) | 
|---------------------------|-------------|
| EX1: PB15 | EXP1: BTN |
| EX1: PA9 | EXP2: ENCB |
| EX1: PA10 |	EXP2: ENCA |
| EX1: PD2 |	EXP1: LCD-EN |
| EX1: GND |	EXP1: GND |
| EX1: PB14 |	EXP1: D5 |
| EX1: RST |	EXP2: RST |
| EX1: PC0	| EXP1: LCD-CS |
|EX1: 5v |	EXP1: 5v |
|SPI1: MOSI (PA7)	| EXP2: SD-MOSI
|SPI1: CLK (PA5)	| EXP2: SD-SCK
|SPI1: MISO (PA6)	| EXP2: SD-MISO

## Diagramas:
| Objeto | Diagrama | 
|---------------------------|-------------|
| SKR Mini E3 V3.0.1 | [https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/blob/master/hardware/BTT%20SKR%20MINI%20E3%20V3.0/Hardware/BTT%20E3%20SKR%20MINI%20V3.0_PIN.pdf](https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/blob/master/hardware/BTT%20SKR%20MINI%20E3%20V3.0.1/Hardware/BTT%20E3%20SKR%20MINI%20V3.0.1_PIN.pdf) |
| LCD Mini 12864 | https://github.com/bigtreetech/MINI-12864/blob/master/mini12864_v2.0/Hardware/MINI12864%20V2.0-Pin.png |




## Klipper

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
