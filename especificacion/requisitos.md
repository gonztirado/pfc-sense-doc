# Requisitos

Como explicamos anteriormente, el objetivo del proyecto consiste en monitorizar los datos de temperatura de diferentes sensores tanto desde el terminal como de forma remota. 

Quedaría por identificar los diferentes actores que tienen que interacturar con la solución y los requisitos tanto funcionales como no funcionales.


## Actores

Tras la fase de análisis quedan identificados tres tipos de actores que van a hacer uso de la solución

- **Técnico**: Llevará la aplicación móvil instalada y acceso a los sensores. Se encargá de conectarse al sensor utilizado y monitorizar in situ los valores de temperatura.
- Supervisor
- Administrador


- Actores
    - Técnico
    - Supervisor
    - Administrador
- Requisitos funcionales
    - Consultar listado de sensores disponibles
    - Conectar con un sensor y monitorizar en aplicación valores de las temperaturas.
    - Configurar sensores: intervalos de refresco, calibración, etc
    - Monitorización remota de datos de los sensores
    - Configuración de refresco de las gráficas de monitorización
    - Configuración de alarmas por valores críticos en las mismas
    - Exportación de datos y backup
- Requisitos no funcionales
    - Usabilidad
    - Aspecto
    - Mantenimiento
    - Rendimiento
    - Integración
    - Persistencia
    - Documentación