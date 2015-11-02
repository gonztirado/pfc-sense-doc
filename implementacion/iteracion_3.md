# 5.5. Iteración 3: Configurar sensores

Ya que hemos conseguido monitorizar los sensores, el siguiente paso sería poder configurarlos convenientemente, los sensores disponen de servicios para habilitar/deshabilitar un sensor en particular además de para configurar el periodo en el que se consultan los valores de los mismos. El poder configurar convenientemente estos sensores nos ayudará a ahorrar batería de los mismos para sólo hacer la consulta de aquellos que necesitemos y con la frecuencia que necesitemos. El desglose de las tareas para esta iteración se puede observar en la Tabla 5.5.1.

| Tarea | Descripción |
| -- | -- |
| 3.1 | Enviar configuración a los sensores |
| 3.2 | UI de configuración de sensores |
##### *Tabla 5.5.1: Tareas de la iteración 3* 


## 5.5.1 Enviar configuración a los sensores

```
/**
 * Enables or disables notification on a give characteristic.
 * 
 * @param characteristic
 *          Characteristic to act on.
 * @param enabled
 *          If true, enable notification. False otherwise.
 */
public int setCharacteristicNotification(
    BluetoothGattCharacteristic characteristic, boolean enable) {
    bleRequest req = new bleRequest();
    req.status = bleRequestStatus.not_queued;
    req.characteristic = characteristic;
    req.operation = bleRequestOperation.nsBlocking;
    req.notifyenable = enable;
    addRequestToQueue(req);
    boolean finished = false;
    while (!finished) {
        bleRequestStatus stat = pollForStatusofRequest(req);
        if (stat == bleRequestStatus.done) {
            finished = true;
            return 0;
        }
        else if (stat == bleRequestStatus.timeout) {
            finished = true;
            return -3;
        }
    }
    return -2;
}
```
##### *Código 5.5.1: Activación/Desactivación de una característica BluetoothLeService.java*

## 5.5.2 UI de configuración de sensores


Cuando detectamos desde la UI que se cambian el periodo de los sensores invocamos a nuestro ```GenericBluetoothProfile```, que es la clase de la que heredan todos los controladores de los diferentes perfiles GATT, que a su vez llama a nuestro ```BluetoothLeService``` ya preparado con los métodos para habilitar/deshabilitar un determinado perfil GATT o cambiar su periodo. Como los umbrales que nos da el fabricantes de periodos de actualización varían entre los 100 ms y los 2450 ms, los usaremos como límites en nuestro slider de configuración. En el Código 5.5.2 se detallan los métodos implementados para invocar estas actualizaciones de configuración.

```
public void onOffWasUpdated(boolean on) {
	Log.d("GenericBluetoothProfile","Config characteristic set to :" + on);
	if (on) {
		this.configureService();
		this.enableService();
		this.tRow.grayedOut(false);
	}
	else {
		this.deConfigureService();
		this.disableService();
		this.tRow.grayedOut(true);
	}
	
}

public void periodWasUpdated(int period) {
	if (period > 2450) period = 2450; 
	if (period < 100) period = 100;
	byte p = (byte)((period / 10) + 10);
	Log.d("GenericBluetoothProfile","Period characteristic set to :" + period);
   
    int error = mBTLeService.writeCharacteristic(this.periodC, p);
    if (error != 0) {
        if (this.periodC != null)
            printError("Sensor period failed: ",this.periodC,error);
    }
    
	this.tRow.periodLegend.setText("Periodo actualización (actualmente : " + period + "ms)");
}
```
##### *Código 5.5.2: Métodos de configuración de servicios GATT en GenericBluetoothProfile.java*