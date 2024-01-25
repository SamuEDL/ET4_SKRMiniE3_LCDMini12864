## ¿Que funciona? / It works?

| Periferico / Peripheral | Funciona? / Work ? | 
|---------------------------|-------------|
| Pantalla | ? |
| Motor Z | ? |
| Motor X  |	? |
| Motor Y |	?|
| Motor Extrusor | ? |
| Sensor Inductivo  / Inductive Sensor| ? |
| EndStop Z |	? |
| Enstop X |	? |
| EndStop Y|	? |
| Sensor Temp Hotend	| ? |
| Hotend |	? |
| Sensor Temp Cama / Sensor Temp Bed	| ? |
| Cama / Bed	| ? |


## ¿Cambios realizados en los ficheros de marlin?
Las modificaciones se realizaron a partir del fichero de ejemplo Ender 3 con placa SKR Mini E3 V3.0 disponible en el repositorio de marlin. Todos los cambios se han realizado en configuration.h.

- Cambios referentes al LCD:

| Cambio | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
|Añadir linea (despues de la de  #define MOTHERBOARD)| #define SKR_MINI_SCREEN_ADAPTER |
|Descomentar linea para activar LCD| #define FYSETC_MINI_12864_2_1    // Type A/B. NeoPixel RGB Backlight |
|Selecionar el tipo de pantalla | #define NEOPIXEL_TYPE NEO_RGB |

- Cambios para la estructura de la Anet ET4:

| Cambios | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
| Tamaño de Cama Caliente X| #define X_BED_SIZE 220 |
| Tamaño de Cama Caliente Y| #define Y_BED_SIZE 220 |
| Cambio de pasos  | #define DEFAULT_AXIS_STEPS_PER_UNIT   { 80.4, 80.4, 403.1, 100.7 } |


- Otros cambios: (Opcionales)

| Cambio | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
| Cambiar idioma a Español | #define LCD_LANGUAGE es |

- Otros cambios, solo si has cambiado el hotend/extrusor por el de la **Kingroon KP3S**

| Cambio | Parametro Implementado / Sustituido| 
|---------------------------|-------------|
| Cambio de pasos  | #define DEFAULT_AXIS_STEPS_PER_UNIT   { 80.4, 80.4, 403.1, 815 } |
