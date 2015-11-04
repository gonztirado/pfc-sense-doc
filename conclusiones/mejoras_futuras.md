# 8.3. Mejoras futuras

Considero que este proyecto tiene largo recorrido y que se pueden seguir realizando mejoras en el mismo. El mundo de los dispositivos Bluetooth está en auge y cada vez hay más variedad y con nuevas capacidades, así que se puede seguir investigando para añadir sacar más casos de uso que puedan llegar a ser útiles. También han quedado algunas funcionalidades en el tintero que más adelante se pueden ir incorporando, algunas de ellas son:

- Programación de alertas en el dispositivo cuando los sensores alcancen ciertos umbrales críticos.
- Captura de posición GPS para adjuntar en la toma de temperaturas. Esto permitiría crear informes sobre mapas con rutas geoposicionadas para, por ejemplo, monitorizar rutas de camiones refrigerados.
- Búsqueda de sensores perdidos aprovechando la capacidad que tienen los mismos de usarse como balizas de localización.
- Exportación a diferentes formatos, ya es posible exportar a JSON desde Parse. Pero estaría bien poder exportar también a Excel, CSV, y XML, por ejemplo.
- Experimentar con otros sensores de otros fabricantes como el sensor de control de plantas de Parrot.
- Probar integración con otro tipo de dispositivos Bluetooth, como las balizas de localización, monitores de ritmo cardiaco o de control de glucosa en sangre.

- Mejoras opcionales:
    - Alertas programables cuando se alcancen umbrales críticos
	- Captura de posición GPS para adjuntar en la toma de temperaturas
	- Búsqueda de sensor perdido aprovechando la capacidad de usar como iBeacon
	- Exportación a diferentes formatos (Excel, CVS, JSON, XML, etc)
- Mejoras opcionales
	- Visualización de rutas con las tomas de temperaturas geoposicionadas en [cartodb.com](http://cartodb.com/)
	- Dashboard web con monitorización de datos en tiempo real usando [ducksboard.com](https://ducksboard.com)
	- Integración con [spark](https://www.spark.io/)