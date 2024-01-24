## ¿Como debe ir conectada la pantalla a la placa?

| SKR Mini E3 v3 pin (PORT: pin) | Mini 12864 pin (PORT: pin) | 
|---------------------------|-------------|
| EX1: PB5 | EXP1: BTN |
| EX1: TX1 | EXP2: ENCB |
| EX1: RX1 |	EXP2: ENCA |
| EX1: PB8 |	EXP1: LCD-EN |
| EX1: GND |	EXP1: GND |
| EX1: PA15 |	EXP1: D5 |
| EX1: RST |	EXP2: RST |
| EX1: PD6	| EXP1: LCD-CS |
|EX1: 5v |	EXP1: 5v |
|SPI1: MOSI	| EXP2: SD-MOSI
|SPI1: CLK	| EXP2: SD-SCK
|SPI1: MISO	| EXP2: SD-MISO

## Diagramas:
| Objeto | Diagrama | 
|---------------------------|-------------|
| SKR Mini E3 V3 | https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/blob/master/hardware/BTT%20SKR%20MINI%20E3%20V3.0/Hardware/BTT%20E3%20SKR%20MINI%20V3.0_PIN.pdf |
| LCD Mini 12864 | https://github.com/bigtreetech/MINI-12864/blob/master/mini12864_v2.0/Hardware/MINI12864%20V2.0-Pin.png |

## Klipper

LCD config:
```
[display]
lcd_type: uc1701
cs_pin: PB8
a0_pin: PD6
rst_pin: PB9
encoder_pins: ^PA9,^PA10
click_pin: ^!PB5
contrast: 63
spi_software_sclk_pin: PA5
spi_software_mosi_pin: PA7
spi_software_miso_pin: PA6

[neopixel SKR_screen]
pin: PA15
chain_count: 3
initial_RED: 0.4
initial_GREEN: 0.05
initial_BLUE: 0.0
color_order: RGB
```