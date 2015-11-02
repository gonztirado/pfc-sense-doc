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

Al conectarnos al servidor GATT nos devuelve una instancia de un objeto ```BluetoothGatt``` con el cual podremos hacer uso y conectarnos como cliente. El parámetro de tipo ```BluetoothGattCallback``` es usado para recuperar resultados por parte del cliente, como son el estado de la conexión así como más operaciones GATT de los clientes.

Para hacer la implementación crearemos un ```Service``` llamado ```BluetoothLeService``` que interactuará con nuestra ```Activity```. El servicio tendrá la siguiente forma:

```
// A service that interacts with the BLE device via the Android BLE API.
public class BluetoothLeService extends Service {
    private final static String TAG = BluetoothLeService.class.getSimpleName();

    private BluetoothManager mBluetoothManager;
    private BluetoothAdapter mBluetoothAdapter;
    private String mBluetoothDeviceAddress;
    private BluetoothGatt mBluetoothGatt;
    private int mConnectionState = STATE_DISCONNECTED;

    private static final int STATE_DISCONNECTED = 0;
    private static final int STATE_CONNECTING = 1;
    private static final int STATE_CONNECTED = 2;

    public final static String ACTION_GATT_CONNECTED =
            "com.celulabs.pfcsense.ble.common.ACTION_GATT_CONNECTED";
    public final static String ACTION_GATT_DISCONNECTED =
            "com.celulabs.pfcsense.ble.common.ACTION_GATT_DISCONNECTED";
    public final static String ACTION_GATT_SERVICES_DISCOVERED =
            "com.celulabs.pfcsense.ble.common.ACTION_GATT_SERVICES_DISCOVERED";
    public final static String ACTION_DATA_NOTIFY =
            "com.celulabs.pfcsense.ble.common.ACTION_DATA_NOTIFY";
    public final static String EXTRA_DATA = 
            "com.celulabs.pfcsense.ble.common.EXTRA_DATA";
    public final static String EXTRA_UUID = 
            "com.celulabs.pfcsense.ble.common.EXTRA_UUID";
    public final static String EXTRA_STATUS = 
            "com.celulabs.pfcsense.ble.common.EXTRA_STATUS";
    public final static String EXTRA_ADDRESS = 
            "com.celulabs.pfcsense.ble.common.EXTRA_ADDRESS";
    
    // Various callback methods defined by the BLE API.
    private final BluetoothGattCallback mGattCallback =
            new BluetoothGattCallback() {
        @Override
        public void onConnectionStateChange(BluetoothGatt gatt, int status,
                int newState) {
            String intentAction;
            if (newState == BluetoothProfile.STATE_CONNECTED) {
                intentAction = ACTION_GATT_CONNECTED;
                mConnectionState = STATE_CONNECTED;
                broadcastUpdate(intentAction);
                Log.i(TAG, "Connected to GATT server.");
                Log.i(TAG, "Attempting to start service discovery:" +
                        mBluetoothGatt.discoverServices());

            } else if (newState == BluetoothProfile.STATE_DISCONNECTED) {
                intentAction = ACTION_GATT_DISCONNECTED;
                mConnectionState = STATE_DISCONNECTED;
                Log.i(TAG, "Disconnected from GATT server.");
                broadcastUpdate(intentAction);
            }
        }

        @Override
        // New services discovered
        public void onServicesDiscovered(BluetoothGatt gatt, int status) {
            if (status == BluetoothGatt.GATT_SUCCESS) {
                broadcastUpdate(ACTION_GATT_SERVICES_DISCOVERED);
            } else {
                Log.w(TAG, "onServicesDiscovered received: " + status);
            }
        }

        @Override
        // Result of a characteristic read operation
        public void onCharacteristicRead(BluetoothGatt gatt,
                BluetoothGattCharacteristic characteristic,
                int status) {
            if (status == BluetoothGatt.GATT_SUCCESS) {
                broadcastUpdate(ACTION_DATA_NOTIFY, characteristic);
            }
        }
     ...
    };
...
}
```

Cuando un determinado *callback* es accionado, este llama a su método apropiado ```broadcastUpdate()``` que lanza la acción que le determinemos. Por ejemplo, nosotros propagaremos las acciones de conexión y desconexión, cuando descubramos un nuevo servicio y cuando nos llegue el valor de una característica:

```
private void broadcastUpdate(final String action, final String address,
    final int status) {
	final Intent intent = new Intent(action);
	intent.putExtra(EXTRA_ADDRESS, address);
	intent.putExtra(EXTRA_STATUS, status);
	sendBroadcast(intent);
}

private void broadcastUpdate(final String action,
    final BluetoothGattCharacteristic characteristic, final int status) {
	final Intent intent = new Intent(action);
	intent.putExtra(EXTRA_UUID, characteristic.getUuid().toString());
	intent.putExtra(EXTRA_DATA, characteristic.getValue());
	intent.putExtra(EXTRA_STATUS, status);
	sendBroadcast(intent);
}
```

## 5.4.2. Filtrar los perfiles GATT que nos interesan y extraer sus valores

Ya hemos conseguido conectarnos a un sensor y recuperar los valores de sus características, ahora nos quedaría recuperar esos valores y el tipo de característica enviada y quedarnos solo con la de aquellos perfiles GATT que nos interese. En nuestro caso los perfiles que nos interesan son:

- Temperatura ambiental
- Temperatura por infrarojos (IR)
- Barómetro
- Luxómetro
- Humedad

Para consultar los UUID de los servicios que nos interesan hemos consultado la documentación que nos ofrece Texas Instruments acerca de los perfiles GATT de su dispositivo Sensor Tag, podemos ver un ejemplo de la documentación para el sensor de temperatura en la Figura 5.4.1.

![](./imagenes/gatt_commands_temperature.jpg)
##### *Figura 5.4.1: UUIDs de los servicios GATT de Temperatura*

Crearemos un controlador para cada perfil para controlar lo

![](./imagenes/diagrama_clase_gatt_profiles.jpg)
##### *Figura 5.4.1: Diagrama de clases para los controladores de perfiles GATT*
