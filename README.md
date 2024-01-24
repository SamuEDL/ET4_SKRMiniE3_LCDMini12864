# ET4_SKRMiniE3_LCDMini12864
En este repositorio, guardare los ficheros de configuracion para la Anet ET4 modeada con la placa base SKR Mini E3 V3.0 y LCD BTT BIGTREETECH MINI 12864 V2.0.
El motivo de la sustitucion de estos dos componentes, es porque se me quemo la placa y no es posible sustituir la placa sin cambiar la pantalla. A no ser que se use una placa original, que actualmente sale el doble de caro, de peor calidad y peor compatibilidad.

## ¿Por que elegi estos componentes?
Eran los mas baratos y no queria gastar mucho. Como consecuencia, habra que adaptar las conexiones para que se pueda conectar el LCD al SKR.

## ¿Cambios realizados en los ficheros de marlin?
Las modificaciones se realizaron a partir del fichero de ejemplo ET4+ disponible en el repositorio de marlin. Todos los cambios se han realizado en configuration.h.

- Cambios referentes a la placa

**Aviso:** Puse el principio tanto el de la SKR 3.0 como el de la 3.0.1, porque es una loteria de cual te puede llegar. Asi que añade solo **una** de las dos lineas dependiendo de lo que te haya llegado.

| Cambio | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
| Cambio de placa por la SKR V3.0 | #define MOTHERBOARD BOARD_BTT_SKR_MINI_E3_V3_0 |
| Cambio de placa por la SKR V3.0.1 | #define MOTHERBOARD BOARD_BTT_SKR_MINI_E3_V3_0_1 |
| Cambio de velocidad de comunicacion | #define BAUDRATE 115200|
| Serial Port | #define SERIAL_PORT 2 |
| Serial Port | #define SERIAL_PORT_2 -1 |
| Cambio de Driver en Y | #define Y_DRIVER_TYPE TMC2209 |
| Cambio de Driver en X | #define X_DRIVER_TYPE TMC2209 |
| Cambio de Driver en Z | #define Z_DRIVER_TYPE TMC2209 |
| Cambio de Driver en E0 | #define E0_DRIVER_TYPE TMC2209 |

- Cambios referentes al LCD:

| Cambio | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
|Añadir linea (despues de la de  #define MOTHERBOARD)| #define SKR_MINI_SCREEN_ADAPTER |
|Descomentar linea para activar LCD| #define FYSETC_MINI_12864_2_1    // Type A/B. NeoPixel RGB Backlight |
|Selecionar el tipo de pantalla | #define NEOPIXEL_TYPE NEO_RGB |

- Otros cambios: (Opcionales)

| Cambio | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
| Activacion EndStop Z | #define USE_ZMIN_PLUG |
| Cambiar idioma a Español | #define LCD_LANGUAGE es |


## Agradecimientos a 
- PaulSolodovnikov por explicar los cambios necesarios para marlin (https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/issues/728#issuecomment-1464537556)
- evgarthub por explicar como se deberia conectar la placa a la pantalla (https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/issues/728#issuecomment-1736805084)
- mundoanet por explicar como sustituir la placa en la anet (https://mundoanet.blogspot.com/2020/08/instalacion-placa-mksskr-con-placa.html)
- crazy_3D por el soporte para poner la SKR Mini E3 V3 en la Anet. (https://cults3d.com/es/modelo-3d/herramientas/anet-et4-o-et5-adaptador-placa-base-skr-mini-e3-v3)
- 3dwork.io por su guia de configuracion de marlin ( https://3dwork.io/configurar-marlin-2-0-x-desde-cero/ )
