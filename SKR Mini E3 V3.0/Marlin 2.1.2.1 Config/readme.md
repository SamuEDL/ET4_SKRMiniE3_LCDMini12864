Cambios basados en los ficheros de configuracion de Escrich y Ruben Mota (Gracias a ambos) para la SKR Mini E3 V2.0 en la Anet ET4. https://github.com/Escrich/00_SKR_Mini_00/tree/master

Estos ficheros estan preparados para ser utilizados para **Marlin 2.1.2.1 Estable** https://github.com/MarlinFirmware/Marlin/releases/tag/2.1.2.1


## AVISO
No me hago responsable de dispositivos brickeados, tarjetas SD dañada o que la impresora empiece a imprimir un cuerpo para gobernar el mundo. 

## NOTA
Los ficheros de configuracion estan preparados para la Anet ET4 con el extrusor/hotend de la kingroon kp3s, en caso que la tengas de serie tendras que modificar los parametros relacionados con el extrusor/hotend y posiblemente el giro del motor. Igualmente abajo os dejo los parametros que hay que tocar referente a ello. ([Cambios para el extrusor/hotend de serie de la Anet ET4](https://github.com/SamuEDL/ET4_SKRMiniE3_LCDMini12864/tree/main/SKR%20Mini%20E3%20V3.0/Marlin%202.1.2.1%20Config#cambios-para-el-extrusor-de-serie-de-la-anet-et4)) 


## ¿Que funciona? / It works?

| Periferico / Peripheral | Funciona? / Work ? | 
|---------------------------|-------------|
| Compila | YES! |
| Pantalla / Screen | YES |
| Motor Z | YES |
| Motor X  |	YES |
| Motor Y |	YES |
| Motor Extrusor | YES |
| Sensor Inductivo  / Inductive Sensor| No testeado / Not tested |
| EndStop Z |	YES |
| Enstop X |	YES |
| EndStop Y|	YES |
| Sensor Temp Hotend	| YES |
| Hotend |	YES |
| Sensor Temp Cama / Sensor Temp Bed	| YES |
| Cama / Bed	| YES |


## ¿Cambios realizados en los ficheros de marlin?
Las modificaciones se realizaron a partir del fichero de ejemplo de la Ender 3 con placa SKR Mini E3 V3.0 disponible en el repositorio de marlin y se hicieron los cambios basados en el fichero de la SKR 2.0 para Anet ET4 de Escrich y Ruben Mota. Todos las lineas modificadas en el fichero de configuracion esta comentado con un \\SAM, para saberlo.

A continuacion, he puesto algunos cambios aparte que he realizado para el funcionamiento de la pantalla, poner marlin en español o para usar el extrusor de la kingroon kp3s

- Cambios referentes al LCD:
  
Modificaciones en el configuration.h

| Cambio | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
|Añadir linea (despues de la de  #define MOTHERBOARD)| #define SKR_MINI_SCREEN_ADAPTER |
|Descomentar linea para activar LCD| #define FYSETC_MINI_12864_2_1    // Type A/B. NeoPixel RGB Backlight |
|Selecionar el tipo de pantalla | #define NEOPIXEL_TYPE NEO_RGB |
|Direccion de la rueda | #define REVERSE_ENCODER_DIRECTION |

Modificaciones en el configuration_adv.h

| Cambio | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
| Activacion de backlight|  #define LED_CONTROL_MENU |

- Cambios para la estructura de la Anet ET4:

| Cambios | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
| Tamaño de Cama Caliente X| #define X_BED_SIZE 220 |
| Tamaño de Cama Caliente Y| #define Y_BED_SIZE 220 |


- Otros cambios: (Opcionales)

| Cambio | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
| Cambiar idioma a Español | #define LCD_LANGUAGE es |

- Otros cambios, solo si has cambiado el hotend/extrusor por el de la **Kingroon KP3S**

| Cambio | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
| Cambio de pasos  | #define DEFAULT_AXIS_STEPS_PER_UNIT   { 80.4, 80.4, 403.1, 407.5 } |
| Longitud maxima de extrusion  | #define EXTRUDE_MAXLENGTH 1000 |
| Posicion de Homing X  | #define X_MIN_POS 0  |
| Posicion de Homing Y  | #define Y_MIN_POS -32 |

----------------------------

## Cambios para el extrusor de serie de la Anet ET4:

| Cambios | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
| Cambio de pasos  | #define DEFAULT_AXIS_STEPS_PER_UNIT   { 80.4, 80.4, 403.1, 100.7 } |
| Giro del motor  | #define INVERT_E0_DIR true |
| Posicion de Homing X  | #define X_MIN_POS -1  |
| Posicion de Homing Y  | #define Y_MIN_POS -11 |
