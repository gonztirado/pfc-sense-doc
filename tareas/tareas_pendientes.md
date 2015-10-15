## Tareas a realizar ##

### Aplicación móvil ###
- App [BlackBerry 10](https://developer.blackberry.com/native/)
- Sensores Bluetooth LE. [SensorTag Texas Instruments CC2541](http://www.ti.com/tool/cc2541dk-sensor)
- Funcionalidad deseada
	- Monitorización de uno o varios sensores
	- Temperatura actual de cada sensor
	- Gráfica e histórico de temperaturas para cada sensor
	- Configuración de intervalos de captura de datos
	- Alertas programables cuando se alcancen umbrales críticos
	- Exportación de datos en diferentes formatos (Excel, CVS, JSON, XML, etc)
	- Envío de datos a servidor en la nube
- Mejoras opcionales:
	- Captura de posición GPS para adjuntar en la toma de temperaturas
	- Búsqueda de sensor perdido aprovechando la capacidad de usar como iBeacon
	- App [Android](http://developer.android.com/index.html)

### Servicios y backoffice en servidor ###
- Servidor [backbeam.io](http://backbeam.io/)
- Funcionalidad deseada
	- Backoffice para gestionar terminales y sensores
	- Servicio web para súbida de datos de temperatura
	- Visualización de datos
		- Tablas
		- Gráficas de temperatura: http://www.highcharts.com/
		- Informes
		- Exportación a diferentes formatos (Excel, CVS, JSON, XML, etc)
- Mejoras opcionales
	- Visualización de rutas con las tomas de temperaturas geoposicionadas en [cartodb.com](http://cartodb.com/)
	- Dashboard web con monitorización de datos en tiempo real usando [ducksboard.com](https://ducksboard.com)
	- Integración con [spark](https://www.spark.io/)

### Memoria ###
- Introducción
- Objetivo
- Historia del proyecto
	- Prototipo de sensor bluetooth
	- Prototipo de app BlackBerry java
	- Uso de sensor Zigbee (Blubug)
	- Integración con transmobile
- Tecnologías utilizadas
	- BlackBerry 10 / Android
	- Bluetooth 4.0 Low Energy
	- GPS
	- iBeacon
	- Cloud services
		- backbeam
		- cartodb
		- ducksboard
		- spark
- Tecnologías alternativas
	- Plataformas móviles
		- Android
		- iPhone
		- Windows Phone
	- Protocolos de transmisión inalámbricos
		- Zigbee
- Metodologías ágiles
	- Extreme programming (xP)
	- Scrum / Kanban
	- TDD / Integración continua
- Herramientas
	- Momentics IDE
	- Sourcetree
	- JIRA
	- Git / Bitbucket
	- Markdown / Gitbook
- Planificiación
	- Sprints
- Diseño de app móvil
- Diseño de backoffice
- Análisis de implementación móvil
- Análisis de implementación backoffice
- Diagramas de flujo y modelo de datos
- Glosario de términos
- Bibliografía




