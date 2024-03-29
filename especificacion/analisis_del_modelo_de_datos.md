# 4.3. Análisis del modelo de datos

Tras analizar los requerimientos que tenemos de la aplicación llegamos a la conclusión de que principalmente el modelo se compondrá de las clases donde guardaremos los valores que nos devuelven los sensores. Por lo tanto, cada uno de estos valores estará asociado a un sensor, que a su vez estará asociado a un terminal tal y como se aprecia en la Figura 4.3.1. 

![](./imagenes/diagrama_clase_deviceinfo_sensorinfo.jpg)
###### *Figura 4.3.1: Diagramas de clase de DeviceInfo y SensorInfo*

Como los datos de sensores son de diferente tipo y queremos persistirlos en tablas separadas para su mejor análisis, diseñaremos una serie de objetos que heredaran de una clase común donde almacenaremos principalmente el valor que nos devuelve el sensor y la fecha en la que se tomó dicho valor. El diseño propuesto se puede observar en la Figura 4.3.2.

![Figura 2](./imagenes/diagrama_clase_sensordata.jpg)
###### *Figura 4.3.2: Diagramas de clase de SensorData y sus clases hijas*