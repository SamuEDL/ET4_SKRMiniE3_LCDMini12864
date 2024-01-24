# ET4_SKRMiniE3_LCDMini12864
En este repositorio, guardare los ficheros de configuracion para la Anet ET4 modeada con la placa base SKR Mini E3 V3.0 y LCD BTT BIGTREETECH MINI 12864 V2.0.
El motivo de la sustitucion de estos dos componentes, es porque se me quemo la placa y no es posible sustituir la placa sin cambiar la pantalla. A no ser que se use una placa original, que actualmente sale el doble de caro, de peor calidad y peor compatibilidad.

## ¿Por que elegi estos componentes?
Eran los mas baratos y no queria gastar mucho. Como consecuencia, habra que adaptar las conexiones para que se pueda conectar el LCD al SKR.

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

## ¿Donde lo compre?

| Objeto | URL | 
|---------------------------|-------------|
| SKR Mini E3 V3 | https://es.aliexpress.com/item/1005006042517491.html |
| LCD Mini 12864 | https://es.aliexpress.com/item/1005005910581710.html |


## ¿Cambios realizados en los ficheros de marlin?
Las modificaciones se realizaron a partir del fichero de ejemplo ET4+ disponible en el repositorio de marlin.

Cambios referentes a la placa

| Cambio | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
| Cambio de placa por la SKR | #define MOTHERBOARD BOARD_BTT_SKR_MINI_E3_V3_0 |
| Cambio de velocidad de comunicacion | #define BAUDRATE 115200|
| Serial Port | #define SERIAL_PORT 2 |
| Serial Port | #define SERIAL_PORT_2 -1 |
| Cambio de Driver en Y | #define Y_DRIVER_TYPE  TMC2209 |
| Cambio de Driver en X | #define X_DRIVER_TYPE  TMC2209 |
| Cambio de Driver en Z | #define Z_DRIVER_TYPE  TMC2209 |
| Cambio de Driver en E0 | #define E0_DRIVER_TYPE  TMC2209 |

Cambios referentes al LCD:
| Cambio | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
|En proceso|En proceso|

Otros cambios:
| Cambio | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
| Activacion EndStop Z | #define USE_ZMIN_PLUG |


## Agradecimientos a 
- evgarthub por explicar como se deberia conectar la placa a la pantalla (https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/issues/728#issuecomment-1736805084)
- mundoanet por explicar como sustituir la placa en la anet
- crazy_3D por el soporte para poner la SKR Mini E3 V3 en la Anet. (https://cults3d.com/es/modelo-3d/herramientas/anet-et4-o-et5-adaptador-placa-base-skr-mini-e3-v3)
- 3dwork.io por su guia de configuracion de marlin ( https://3dwork.io/configurar-marlin-2-0-x-desde-cero/ )
