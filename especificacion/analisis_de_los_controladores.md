# Análisis de los controladores

Ya teniendo el diseño de como va a ser el modelo de datos, el siguiente paso es diseñar qué controladores vamos a necesitar para el manejo de la aplicación y cuales van a ser utilidad.



![Figura 1](./imagenes/diagrama_sensordata_controller.JPG)
###### *Figura 1: Diagramas de clase del controlador de tratamiento de valores de los sensores*

Por un lado tenemos el controlador que se encarga de manejar cuando hemos recibido nuevos valores desde los sensores. Se encargará de procesarlos y llamar a los controladores de Parse y Ducksboard cuando corresponda.

![Figura 2](./imagenes/diagrama_parse_ducksboard_controller.JPG)
###### *Figura 2: Diagramas de clase de los controladores que se encargan de la configuración de Parse y del envío de datos al panel de Ducksboard*