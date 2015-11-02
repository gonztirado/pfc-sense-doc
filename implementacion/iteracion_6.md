# 5.8. Iteración 6: Consulta y exportación de datos históricos

Para el envío de datos haremos uso de la plataforma web de Parse. Como ya configuramos la aplicación para hacer uso de su SDK, sólo nos quedará configurar y actualizar el controlador para enviar también los valores que vayan tomando los diferentes valores de los perfiles GATT. Posteriormente explicaremos como consultar estos datos en la plataforma web y como hacer copia de seguridad de los mismos. Todas estas tareas están desglosadas en la Tabla 5.8.1.

| Tarea | Descripción |
| -- | -- |
| 6.1 | Envío de datos de sensores desde aplicación móvil|
| 6.2 | Consulta y filtrado de datos|
| 6.3 | Creación de copias de seguridad|
##### *Tabla 5.8.1: Tareas de la iteración 6* 

## 5.8.1. Envío de datos de sensores desde aplicación móvil

Cómo ya tenemos el SDK de Parse totalmente configurado, para guardar los datos de los sensores sólo hará falta registrar en ParseController las subclases que queremos utilizar como se puede observar en el Código 5.8.1. Además, todas estas clases las haremos que hereden de ```ParseObject``` para que la aplicación funcione correctamente.

```java
private void registerSubclasses() {
    ParseObject.registerSubclass(DeviceInfo.class);
    ParseObject.registerSubclass(SensorInfo.class);
    ParseObject.registerSubclass(SensorData.class);
    ParseObject.registerSubclass(TemperatureData.class);
    ParseObject.registerSubclass(TemperatureIRData.class);
    ParseObject.registerSubclass(BarometerData.class);
    ParseObject.registerSubclass(HumidityData.class);
    ParseObject.registerSubclass(LuxometerData.class);
    ParseObject.registerSubclass(DucksboardSettings.class);
}
```
##### *Código 5.8.1: Registros de clases del modelo en ParseController.java*

Para persistir los objetos en la plataforma web, sólo tendremos que invocar al método ```saveInBackground()``` que ahora disponen las clases del modelo por heredar de ```ParseObject```


## 5.8.2. Consulta y filtrado de datos








## 5.8.3. Creación de copias de seguridad

