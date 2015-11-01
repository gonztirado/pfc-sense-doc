# 5.4. Iteración 2: Monitorizar los valores de las temperaturas in situ

En esta primera iteración nos hemos propuesto poder consultar desde la aplicación móvil qué sensores hay disponibles para conectarse. Para ello, antes que nada será necesario estudiar cuales son las principales caracteristicas del protocolo Bluetooth LE para posteriormente crear una aplicación y configurarla para que permita escanear los sensores disponibles. Además, deberemos crear una interfaz acorde con el diseño de la UI analizada en el Capitulo 5. El desglose de las tareas que vamos a realizar podemos observarla en la Tabla 5.3.1.

| Tarea | Descripción |
| -- | -- |
| 2.1 | Conectar con un sensor y recuperar sus perfiles GATT |
| 2.2 | Filtrar los perfiles GATT que nos interesan y extraer sus valores |
| 2.3 | Crear controlador para añadir los valores de los sensores |
| 2.4 | UI que muestre los valores actuales y las gráficas |
##### *Tabla 5.3.1: Tareas de la iteración 1* 