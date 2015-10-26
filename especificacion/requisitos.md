# Requisitos

Como explicamos anteriormente, el objetivo del proyecto consiste en monitorizar los datos de temperatura de diferentes sensores tanto desde el terminal como de forma remota. 

Quedaría por identificar los diferentes actores que tienen que interacturar con la solución y los requisitos tanto funcionales como no funcionales.


## Actores

Tras la fase de análisis quedan identificados tres tipos de actores que van a hacer uso de la solución

- **Técnico**: Llevará la aplicación móvil instalada y acceso a los sensores. Se encargá de conectarse al sensor utilizado y monitorizar in situ los valores de temperatura.
- **Supervisor**: Tendrá acceso al entorno de monitorización remota de los sensores para controlar en el momento que este estime conveniente que la temperatura está entre los márgenes de uso correcto.
- **Administrador**: Se encarga de configurar el entorno de configuración remota, configuración de alertas y realizará las tareas de exportación de datos y backup cuando sea necesario.


## Requisitos funcionales

- **Consultar listado de sensores**: Los técnicos podrán consultar el listado de sensores disponibles desde la aplicación móvil y elegir a cual se quieren conectar.
- **Monitorizar los valores de las temperaturas in situ**: Los técnicos tras conectarse a un sensor podrán monitorizar la temperatura de los mismos desde la aplicación móvil.
- **Configurar sensores**: Los técnicos podrán cambiar los intervalos de refresco de los diferentes sensores y calibrarlos si fuera necesario.
- **Monitorización remota de los valores de los sensores**: Los supervisores podrán monitorizar desde un panel web los datos en tiempo real de los diferentes sensores configurados.
- **Configuración de dashboard de monitorización**: Los administradores tendrán acceso a la configuración de los difentes *dashboards* y cambiar los valores de refresco de las gráficas y configurar alarmas sobre los valores críticos si así lo estimaran necesario.
- **Consulta y exportación de datos históricos**: Los administradores tendrán acceso a los datos enviados por los terminales por si hiciera falta analizarlos, exportarlos o realizar copias de seguridad de los mismos.
    

## Requisitos no funcionales

- **Usabilidad**: La aplicación ha de ser intuitiva para los usuarios, eliminando pasos innecesarios y minimizando las acciones necesarias para realizar las distintas operaciones.
- **Aspecto**: La interfaz de usuario debe tener un aspecto atractivo e intuitivo que facilite la labor a los usuarios.
- **Mantenimiento**: El código ha de estar bien estructurado y seguir un patrón de sangrado y comentado, además de tener una buena documentación, que faciliten su futuro mantenimiento.
- **Robustez**: La aplicación tiene que ser robusta ante posibles fallos. Los posibles fallos que pudieran ocurrir se trataran correctamente y se informará al usuario si se estimara oportuno.
- **Rendimiento**: La aplicación tiene que ir fluida y funcionar correctamente aunque hubiera conexiones lentas a acceso a datos móviles.
- **Integración**: La solución tiene que ser capaz de dotar de una capa de integración con servicios de terceros para ampliar las funcionalidades de la misma.
- **Persistencia**: La información de tratada en la aplicación debe ser persistida de modo que pueda recuperarse y analizarse a posteriori si fuera necesario.
- **Documentación**: Se incluirá un manual de usuario comprensible por cualquier usuario básico y un manual de instalación de la aplicación.