# 5.3. Iteracion 1: Consultar listado de sensores

En esta primera iteración nos hemos propuesto poder consultar desde la aplicación móvil qué sensores hay disponibles para conectarse. Para ello, antes que nada será necesario estudiar cuales son las principales caracteristicas del protocolo Bluetooth LE para posteriormente crear una aplicación y configurarla para que permita escanear los sensores disponibles. Además, deberemos crear una interfaz acorde con el diseño de la UI analizada en el Capitulo 5. El desglose de las tareas que vamos a realizar podemos observarla en la Tabla 5.3.1.

| Tarea | Descripción |
| -- | -- |
| 1.1 | Estudio del protocolo Bluetooth LE |
| 1.2 | Creación de proyecto para la aplicación en Android Studio |
| 1.3 | Configuración del proyecto para utilizar Bluetooth LE |
| 1.4 | Crear controlador para detectar dispositivos bluetooth disponibles |
| 1.5 | Generar la interfaz del listado de dispositivos |
##### *Tabla 5.3.1: Tareas de la iteración 1* 


## 5.3.1 Estudio del protocolo Bluetooth LE

Al contrario que ocurría con el Bluetooth clásico, Bluetooth Low Energy está diseñado para proporcionar un significante bajo consumo energético. Android da soporte a este protocolo desde su versión 4.3, esto le permite comunicarse con sensores, monitores de ritmo cardiaco, dispositivos deportivos y muchos más. Algunos de los conceptos que hay que conocer sobre Bluetooth LE son:

- **Generic Attribute Profile (GATT)**: el perfil GATT una especificación general para el envío y la recepción de pequeñas piezas de datos también conocidas como "atributos" a través de una conexión BLE. Actualmente, todos los perfiles de comunicación actuales están basados en GATT. El consorcio Bluetooth tiene definidos multitud de perfiles GATT para diversos propósitos. Hay que tener en cuenta que un mismo dispositivo puede implementar varios de estos perfiles, algunos ejemplos de perfiles GATT son:
   - BAS: Nivel de batería del dispositivo
   - BLP: Consulta de presión sanguínea
   - CGMP: Control de glucosa en sangre
   - CSCP: Cadencia y velocidad en ciclismo
   - ESP: Sensor ambiental 
   - HRP: Consulta de ritmo cardiaco

