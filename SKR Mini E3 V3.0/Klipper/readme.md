# Klipper
Esta configuracion la dejo para tenerla a mano por si mas adelante quiero probar Klipper en la impresora. Pero de momento no lo tengo planeado.

## Configuracion LCD / LCD config:
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
