# 5.7. Iteración 5: Configuración de dashboard de monitorización

Ya tenemos el dashboard de monitorización creado, pero este tiene un problema, y es que actualmente todos los sensores con los que nos conectemos enviarán la información de temperaturas al mismo panel. Por lo tanto, es necesario crear un entorno remoto, en el cual el administrador pueda configurar un panel para cada sensor dado de alta y así el supervisor pueda convenientemente visualizar aquellos datos de todos los sensores que necesite según sean sus necesidades particulares.

| Tarea | Descripción |
| -- | -- |
| 5.1 | Creación de modelo de configuración de Ducksboard |
| 5.2 | Consulta de configuración en aplicación móvil |
| 5.3 | Configuración de dashboards personalizados para un supervisor |
##### *Tabla 5.7.1: Tareas de la iteración 5* 

## 5.7.1. Creación de modelo de configuración de Ducksboard

El modelo que necesitamos crear para la configuración del panel para que sea totalmente configurable por el administrador necesita de los siguientes valores:

- Identificador del sensor configurado
- API key de la cuenta de Ducksboard
- Intervalo de frecuencia de actualización para los widgets de valores
- Intervalo de frecuencia de actualización para los widgets de las gráficas
- Identificador del widgetID para los valores y las graficas de cada servicio GATT

Por lo tanto, el diseño del modelo tendría la forma que se observa en la Figura 5.7.1.

![](./imagenes/diagrama_clase_ducksboard_settings.jpg)
##### *Figura 5.7.1: Diagrama del modelo de DucksboardSettings*

Este modelo tiene que tener su correspondencia en un entorno web configurable por el administrador. Para ello, haremos uso de la plataforma de Parse para su creación. La creación de modelos en Parse es muy sencillo, basta con ir a la sección *Data* y seleccionar la opción *+ Add Class*, entonces aparecerá un dialogo en el que indicaremos que se trata de una clase *Custom* con el nombre ```DucksboardSettings``` tal y como se muestra en la Figura 5.7.2.

![](./imagenes/parse_ducksboard_settings.jpg)
##### *Figura 5.7.2: Creación en Parse de la clase DucksboardSettings*

Posteriormente, sólo hará falta ir añadiendo columnas a la tabla con el nombre y tipo que elijamos según nos vayan haciendo falta. Para ello seleccionaremos la opción *+ Col* del panel de Parse y nos aparecerá un dialogo muy fácil de configurar, como se puede apreciar en la Figura 5.7.3 para la creación de la columna ```apiKey```. Tendremos que repetir este proceso hasta completar el resto de columnas necesarias según indica el modelo que se ve en la Figura 5.7.1.

![](./imagenes/parse_ducksboard_settings_column.jpg)
##### *Figura 5.7.3: Creación en columnas de la clase DucksboardSettings*

Una vez creada la clase, el administrador puede rellenar los datos del sensor configurado con los valores recuperados del panel que desee desee configurar. Esta configuración servirá para que la consulte la aplicación móvil y envíe los push de monitorización al panel adecuado.


## 5.7.2. Consulta de configuración en aplicación móvil

Para recuperar desde la aplicación móvil la configuración creada en Parse es necesario previamente hacer una serie de configuraciones en la aplicación. Lo primero es añadir una serie de permisos en nuestro archivo ```AndroidManifest.xml``` tal y como se ve en el Código 5.7.1. Esto nos proveerá los permisos necesarios para poder hacer uso de internet para la recuperación de la configuración.

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```
##### *Código 5.7.1: Configuración de uso de Parse en AndroidManifest.xml*



## 5.7.3. Configuración de dashboards personalizados para un supervisor