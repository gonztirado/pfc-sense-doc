# Termógrafos

El siguiente paso en la investigación de tecnologías a utilizar consiste en encontrar un sensor apropiado para consultar la temperatura. 


## Protocolos de comunicación inalámbrica

El primer paso consiste en determinar que tecnología inalámbrica vamos a utilizar en la conectividad con lo sensores, vamos a realizar una comparativa de los diferentes protocolos existentes para determinar la elección del sensor.

### Wifi (802.11 a/b/g/n)
 - Disponible en todos los terminales móviles.
 - Mantener el canal de comunicación wifi con un sensor consume bastante energía.
 - Además, si se mantiene el canal abierto con un canal no podríamos conectarnos a nuestra red local para conectarnos a internet
 - Los sensores con conectividad Wifi está más enfocados para que envíen directamente ellos la temperatura a un servicio web propio sin contar con un smartphone. Tiene el inconveniente de que no podríamos consultar la temperatura del sensor si perdemos cobertura de datos móviles.

### Zigbee
 - Se trata de un protocolo de bajo consumo.
 - Utiliza una topología en red de malla para que los sensores se comuniquen entre sí.
 - Se pueden construir sensores con muy poca electrónica.
 - Bajo coste de los mismos
 - Tiene la desventaja de que existen muy pocos smartphones que incluyan este protocolo. Existen soluciones para dotar a cualquier telefóno de comunicación Zigbee, como bases acopladas o tarjetas SD con zigbee pero incrementan bastante el coste de la solución

### Bluetooth Low Energy
 - Disponible en todos los terminales móviles.
 - Consumo de energía en modo inactivo ultra bajo
 - Capacidad de durabilidad en las baterías de tipo botón durante años 
 - Menor coste de implementación
 - Interoperabilidad entre múltiples proveedores
 - Rango de alcance mejorado
 
| Plataforma        | Lenguaje nativo           | Bluetooh LE   | Cuota 2015 | Curva de aprendizaje |
| ----------------- | ------------------------- | ------------- | ---------- | -------------------- |
| **iOS**           |  Objetive C, Swift        | Si (OS 5+)    | 18.30%     | Alta                 |
| **Android**       |  Java                     | Si (OS 4.3+)  | 78.00%     | Baja                 |
| **Windows Phone** |  C#, Visual Basic.NET     | Si (OS 8.1+)  | 2.70%      | Media                |
| **BlackBerry 10** |  C/C++, Qt/Cascades       | Si (OS 10.0+) | 0.30%      | Baja                 |
| **Híbrido HTML5** |  HTML5, CSS3 y Javascript | con plugins   | 100%       | Media                |
###### *Tabla 1: Comparativa de protocolos de comunicación inalámbrica*