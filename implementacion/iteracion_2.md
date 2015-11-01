# 5.4. Iteración 2: Monitorizar los valores de las temperaturas in situ

Ya conseguimos listar los sensores disponibles, el siguiente paso será conectarnos con uno de ellos, recuperar sus perfiles GATT, filtrar los que no son necesarios para monitorizar la temperatura y crear una interfaz atractiva que muestre los valores actuales y una gráfica con las últimas temperaturas enviadas para poder visualizar de un vistazo si han ocurrido cambios en la misma. El desglose de las tareas que vamos a realizar podemos observarla en la Tabla 5.4.1.

| Tarea | Descripción |
| -- | -- |
| 2.1 | Conectar con un sensor y recuperar sus perfiles GATT |
| 2.2 | Filtrar los perfiles GATT que nos interesan y extraer sus valores |
| 2.3 | Crear controlador para añadir los valores de los sensores |
| 2.4 | UI que muestre los valores actuales y las gráficas |
##### *Tabla 5.4.1: Tareas de la iteración 2* 


## 5.4.1. Conectar con un sensor y recuperar sus perfiles GATT

El primer paso en la interacción con un dispositivo BLE es conectarnos a él, aunque, más específicamente, conectarnos al servidor GATT de el dispositivo. Para ello tendremos que hacer uso del método ```connectGatt()```:

```
mBluetoothGatt = device.connectGatt(this, false, mGattCallback);
```

Al conectarnos al servidor GATT nos devuelve una instancia de un objeto ```BluetoothGatt``` con el cual podremos hacer uso y conectarnos como cliente. El parámetro de tipo ```BluetoothGattCallback``` es usado para recuperar resultados por parte del cliente, como son el estado de la conexión así como más operaciones de los clientes GATT.