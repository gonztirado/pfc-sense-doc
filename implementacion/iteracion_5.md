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

- API key de la cuenta de Ducksboard
- Intervalo de frecuencia de actualización para los widgets de valores
- Intervalo de frecuencia de actualización para los widgets de las gráficas
- Identificador del widgetID para los valores y las graficas de cada servicio GATT