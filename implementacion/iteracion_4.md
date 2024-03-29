# 5.6. Iteración 4: Monitorización remota de los valores de los sensores

Como ya comentamos en la elección de herramientas del Capítulo 3, vamos a utilizar la plataforma web Ducksboard para la monitorización web de los datos de los sensores de temperatura. Esta plataforma permite la creación de paneles de monitorización de gráficas a través de una API para enviar información desde tu propia aplicación. Haremos uso de esta API para modificar los valores de las gráficas que creemos, para ello, las tareas que tendremos que realizar son las definidas en la Tabla 5.6.1.

| Tarea | Descripción |
| -- | -- |
| 4.1 | Configuración de gráficas en Ducksboard |
| 4.2 | Push de datos de sensores al dashboard |
##### *Tabla 5.6.1: Tareas de la iteración 4* 


## 5.6.1. Configuración de gráficas en Ducksboard

Para ceñirnos al análisis que del diseño del panel de monitorización web que definimos en el Capítulo 4, crearemos una gráfica con los valores actuales por cada perfil GATT de los sensores y una gráfica de lineas para ir almacenando los valores históricos de los diferentes sensores. El resultado del panel creado se puede observar en la Figura 5.6.1.

![](./imagenes/ducksboard_empty.jpg)
##### *Figura 5.6.1: Diseño de panel en Ducksboard*

Cada una de estas gráficas tiene asociado un widgetID para hacer push a las mismas, lo que haremos será guardar estos identificadores en nuestro código y asignar un widgetID por defecto a los valores de cada perfil GATT como vemos en Código 5.6.1.

```java
private static final String DEFAULT_WIDGET_VALUE_TEMPERATURE = "730979";
private static final String DEFAULT_WIDGET_VALUE_TEMPERATURE_IR = "730980";
private static final String DEFAULT_WIDGET_VALUE_HUMIDITY = "730981";
private static final String DEFAULT_WIDGET_VALUE_BAROMETER = "730982";
private static final String DEFAULT_WIDGET_VALUE_LUXOMETER = "730983";
private static final String DEFAULT_WIDGET_GRAPHIC_TEMPERATURE = "730985";
private static final String DEFAULT_WIDGET_GRAPHIC_TEMPERATURE_IR = "730986";
private static final String DEFAULT_WIDGET_GRAPHIC_HUMIDITY = "730988";
private static final String DEFAULT_WIDGET_GRAPHIC_BAROMETER = "730989";
private static final String DEFAULT_WIDGET_GRAPHIC_LUXOMETER = "730990";
```
##### *Código 5.6.1: Identificadores de los widget por defecto en DucksboardController.java*


## 5.6.2. Push de datos de sensores al dashboard

Ya teniendo configurada la plataforma con los widgets que nosotros queremos mostrar y sus identificadores, el siguiente paso es implementar el controlador de envío de datos. Para ello crearemos un controlador ```DucksboardController``` con los métodos que vemos en la figura 5.6.2. Se puede apreciar que se hace uso de los modelos creados en la Iteración 2.

![](./imagenes/diagrama_ducksboard_controller.jpg)
##### *Figura 5.6.1: Diagrama de diseño de DucksboardController*

Para hacer push de los valores, hemos creado un método llamado ```pushDashboardRequest()``` en el que se hace la petición de envío de valores haciendo uso de la API que nos proporciona Ducksboard. La implementación de este método se aprecia en el Código 5.6.2. 

```java
private long pushDashboardRequest(final String widgetID, final String 
        jsonRequest, long lastPushTimestamp, long pushInterval) {
    long currentTime = System.currentTimeMillis();
    long nextPutAllowed = lastPushTimestamp + pushInterval;

    if ((currentTime >= nextPutAllowed) 
            && (_settings != null) 
            && (_settings.getApiKey() != null) 
            && !_settings.getApiKey().isEmpty()) {
            
        final String apiKey = _settings.getApiKey();
        Thread sendThread = new Thread(new Runnable() {
            @Override
            public void run() {
                try {
                    String url = API_PUSH_URL + widgetID;
                    OkHttpClient httpClient = new OkHttpClient();
                    RequestBody body = RequestBody.create(JSON, jsonRequest);
                    Request request = new Request.Builder()
                            .url(url)
                            .post(body)
                            .header("Authorization", "Basic " + apiKey)
                            .build();

                    httpClient.newCall(request).execute();
                } catch (Exception e) {
                    e.printStackTrace();
                }
            }
        });
        sendThread.start();
        return currentTime;
    } else {
        return lastPushTimestamp;
    }
}
```
##### *Código 5.6.2: Push de valores a widgets en DucksboardController.java*


Para cada valor recuparado de los servicios GATT se intentará hacer un push al dashboard. Aunque, como se puede apreciar en el código 5.6.2, se han añadido parámetros de intervalos configurables para hacer push a cada widget para evitar hacer un abuso de la plataforma. Un ejemplo de envío push al panel para el valor de temperatura se puede observar en el Código 5.6.3.

```java
public void pushTemperatureData(TemperatureData sensorData) {
    if (_settings != null) {
        _lastPushTemperatureValue = pushData(
            sensorData, 
            _settings.getValueTemperatureWidgetID(), 
            _lastPushTemperatureValue, 
            _settings.getValuePushInterval()
        );
        
        _lastPushTemperatureGraphic = pushData(
            sensorData,
            _settings.getGraphicTemperatureWidgetID(), 
            _lastPushTemperatureGraphic, 
            _settings.getGraphicPushInterval()
        );
    }
}
```
##### *Código 5.6.3: Envio push de valor de perfil GATT en DucksboardController.java*