# ET4_SKRMiniE3_LCDMini12864
En este repositorio, guardare los ficheros de configuracion para la Anet ET4 modeada con la placa base SKR Mini E3 V3.0 y LCD BTT BIGTREETECH MINI 12864 V2.0.
El motivo de la sustitucion de estos dos componentes, es porque se me quemo la placa y no es posible sustituir la placa sin cambiar la pantalla. A no ser que se use una placa original, que actualmente sale el doble de caro, de peor calidad y peor compatibilidad.

## ¿Por que elegi estos componentes?
Eran los mas baratos y no queria gastar mucho. Como consecuencia, habra que adaptar las conexiones para que se pueda conectar el LCD al SKR.

## ¿Como conecto los componentes?
Encontre esto que puede ser interesante y que puede ayudar en las instalacion de los componentes. https://os.ratrig.com/assets/files/skr-mini-e3-30-wiring-5ed9982d5a1c62e9f30c37b29a2e5571.svg

## Mi pantalla no funciona correctamente cuando imprimo ¿Que puedo hacer?
Un usuario le ocurria algo semejante y posiblemente sea por el aislamiento del cable. En estos casos recomiendan poner un nucleo de ferrita para evitarlo.
https://www.reddit.com/r/BIGTREETECH/comments/uhgxn1/display_freezes_while_printing_prints_fine_though/

## STLs
- Adaptador pantalla para Anet ET4: https://www.thingiverse.com/thing:4035968
- Adaptador de placa SKR 3 para Anet ET4 (De pago): https://cults3d.com/es/modelo-3d/herramientas/anet-et4-o-et5-adaptador-placa-base-skr-mini-e3-v3

## Agradecimientos a 
- **PaulSolodovnikov** por explicar los cambios necesarios para marlin (https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/issues/728#issuecomment-1464537556)
- **evgarthub** por explicar como se deberia conectar la placa a la pantalla (https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/issues/728#issuecomment-1736805084)
- **ichibey** por su diseño para la pantalla LCDMini12864 en Anet ET4 (https://www.thingiverse.com/thing:4035968)
- **mundoanet** por explicar como sustituir la placa en la anet (https://mundoanet.blogspot.com/2020/08/instalacion-placa-mksskr-con-placa.html)
- **crazy_3D** por el soporte para poner la SKR Mini E3 V3 en la Anet. (https://cults3d.com/es/modelo-3d/herramientas/anet-et4-o-et5-adaptador-placa-base-skr-mini-e3-v3)
- **3dwork.io** por su guia de configuracion de marlin ( https://3dwork.io/configurar-marlin-2-0-x-desde-cero/ )
- **Escrich** y **Ruben Mota** a su configuracion para la SKR Mini E3 V2.0, que me sirvio para guiarme en la configuracion de la SKR E3 3.0 ( https://github.com/Escrich/00_SKR_Mini_00/tree/master )
