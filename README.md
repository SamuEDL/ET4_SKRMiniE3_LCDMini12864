# ET4_SKRMiniE3_LCDMini12864
En este repositorio, guardare los ficheros de configuracion para la Anet ET4 modeada con la placa base SKR Mini E3 V3.0 y LCD BTT BIGTREETECH MINI 12864 V2.0.
El motivo de la sustitucion de estos dos componentes, es porque se me quemo la placa y no es posible sustituir la placa sin cambiar la pantalla. A no ser que se use una placa original, que actualmente sale el doble de caro, de peor calidad y peor compatibilidad.

## ¿Por que elegi estos componentes?
Eran los mas baratos y no queria gastar mucho. Como consecuencia, habra que adaptar las conexiones para que se pueda conectar el LCD al SKR.

## ¿Como conecto los componentes?
Encontre esto que puede ser interesante y que puede ayudar en las instalacion de los componentes. https://os.ratrig.com/assets/files/skr-mini-e3-30-wiring-5ed9982d5a1c62e9f30c37b29a2e5571.svg

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
|Comentar linea, para desactivar la pantalla de la ET4 | //#define ANET_ET4_TFT28 |

- Otros cambios: (Opcionales)

| Cambio | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
| Activacion EndStop Z | #define USE_ZMIN_PLUG |
| Cambiar idioma a Español | #define LCD_LANGUAGE es |

- Otros cambios, solo si has cambiado el hotend/extrusor por el de la **Kingroon KP3S**

| Cambio | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
| Sensor Temperatura | #define TEMP_SENSOR_0 1 |
| Cambio de pasos  | #define DEFAULT_AXIS_STEPS_PER_UNIT   { 80.4, 80.4, 403.1, 815 } |

## Agradecimientos a 
- PaulSolodovnikov por explicar los cambios necesarios para marlin (https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/issues/728#issuecomment-1464537556)
- evgarthub por explicar como se deberia conectar la placa a la pantalla (https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/issues/728#issuecomment-1736805084)
- veluska por explicar como hacer funcionar la pantalla en la SKR mini E3 v3.0.1 y hacerla funcionar en klipper (https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/issues/728#issuecomment-1858823385)
- mundoanet por explicar como sustituir la placa en la anet (https://mundoanet.blogspot.com/2020/08/instalacion-placa-mksskr-con-placa.html)
- crazy_3D por el soporte para poner la SKR Mini E3 V3 en la Anet. (https://cults3d.com/es/modelo-3d/herramientas/anet-et4-o-et5-adaptador-placa-base-skr-mini-e3-v3)
- 3dwork.io por su guia de configuracion de marlin ( https://3dwork.io/configurar-marlin-2-0-x-desde-cero/ )
