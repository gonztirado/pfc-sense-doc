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
 
| Protocolo        | Bajo consumo | Bajo coste  | Topologia en malla | Disponible en terminales |
| ---------------- | ------------ | ----------- | ------------------ | ------------------------ |
| **Wifi**         | No           | Si          | No                 | Si                       |
| **Zigbee**       | Si           | Si*         | Si                 | No                       |
| **Bluetooth LE** | Si           | Si          | No                 | Si                       | 
###### *Tabla 1: Comparativa de protocolos de comunicación inalámbrica*

Analizadas las diferentes tecnologías inalámbricas disponibles llegamos a la conclusión de que vamos a utilizar **Bluetooth Low Energy** ya que cumple las características que buscamos: bajo consumo, bajo coste y ya disponible en la mayoría de terminales del mercado sacados al mercado en el último año. Aunque no dispone de forma nativa de topología en malla para la comunicación entre sí de diferentes sensores, existen soluciones de fabricantes que ya lo proporcionan. De todas formas esta característica inicialmente no nos va a ser necesaria para el desarrollo de la solución.

## Sensores Bluetooth LE

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
 
| Protocolo        | Bajo consumo | Bajo coste  | Topologia en malla | Disponible en terminales |
| ---------------- | ------------ | ----------- | ------------------ | ------------------------ |
| **Wifi**         | No           | Si          | No                 | Si                       |
| **Zigbee**       | Si           | Si*         | Si                 | No                       |
| **Bluetooth LE** | Si           | Si          | No                 | Si                       | 
###### *Tabla 1: Comparativa de protocolos de comunicación inalámbrica*

Analizadas las diferentes tecnologías inalámbricas disponibles llegamos a la conclusión de que vamos a utilizar **Bluetooth Low Energy** ya que cumple las características que buscamos: bajo consumo, bajo coste y ya disponible en la mayoría de terminales del mercado sacados al mercado en el último año. Aunque no dispone de forma nativa de topología en malla para la comunicación entre sí de diferentes sensores, existen soluciones de fabricantes que ya lo proporcionan. De todas formas esta característica inicialmente no nos va a ser necesaria para el desarrollo de la solución.