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

## Marlin

En caso, de que no funcione añadir este codigo en el fichero pins_BTT_SKR_MINI_E3_V3_0_1.h entre "#elif HAS_WIRED_LCD"  y "#if ENABLED(CR10_STOCKDISPLAY)"


```
#if ENABLED(SKR_MINI_SCREEN_ADAPTER)
    /** https://github.com/VoronDesign/Voron-Hardware/tree/master/SKR-Mini_Screen_Adaptor/SRK%20Mini%20E3%20V3.0
     *
     *            SKR Mini E3 V3.0.1                   SKR Mini Screen Adaptor
     *                 ------                                ------
     *            5V  | 1  2 | GND                     MISO | 1  2 | SCK
     *            CS  | 3  4 | SCK               (EN1) PA10 | 3  4 | --
     *          MOSI  | 5  6 | MISO              (EN2)  PA9   5  6 | MOSI
     *           3V3  | 7  8 | GND                       -- | 7  8 | --
     *                 ------                           GND | 9 10 | RESET (Kill)
     *                  SPI                                  ------
     *                                                        EXP2
     *
     *                 ------                                ------
     *           PB15 | 1  2 | PB14                      -- | 1  2 | PB5  (BTN_ENC)
     *            PA9 | 3  4 | RESET           (LCD CS) PB8 | 3  4 | PD6  (LCD_A0)
     *           PA10 | 5  6 | PB4              (RESET) PB9 | 5  6 | PA15 (DIN)
     *            PD2 | 7  8 | PC0                       -- | 7  8 | --
     *            GND | 9 10 | 5V                       GND | 9 10 | 5V
     *                 ------                                ------
     *                  EXP1                                  EXP1
     */
    #if ENABLED(FYSETC_MINI_12864_2_1)
      #define BTN_ENC                EXP1_01_PIN
      #define BTN_EN1                EXP1_03_PIN
      #define BTN_EN2                EXP1_05_PIN
      #define BEEPER_PIN                    -1
      #define LCD_RESET_PIN          EXP1_06_PIN
      #define DOGLCD_CS              EXP1_07_PIN
      #define DOGLCD_A0              EXP1_08_PIN
      #define DOGLCD_SCK                    PA5
      #define DOGLCD_MOSI                   PA7

      #define FORCE_SOFT_SPI
      #define LCD_BACKLIGHT_PIN             -1
      #define NEOPIXEL_PIN           EXP1_02_PIN
    #else
      #error "Only FYSETC_MINI_12864_2_1 / MKS_MINI_12864_V3 / BTT_MINI_12864 / BEEZ_MINI_12864 are currently supported on the BIGTREE_SKR_MINI_E3 with SKR_MINI_SCREEN_ADAPTER."
    #endif

  #else
```
