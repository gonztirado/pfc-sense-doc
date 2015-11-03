# 5.2. Iteraciones

Como hemos comentado en apartado anterior, vamos a enfocar el desarrollo en iteraciones acotadas, donde cada uno de ellas desarrollará uno de los requerimientos del proyecto. Así que lo primero que haremos será organizar cada iteración con su requerimiento y el número de versión de la aplicación asociada. En la Tabla 5.2.1 podemos observar como quedaría:

| Iteración | Versión | Requerimiento                                        |   
| --------- | ------- | ---------------------------------------------------- |
| 1         | 0.1.0   | Consultar listado de sensores                        |
| 2         | 0.2.0   | Monitorizar los valores de las temperaturas in situ  | 
| 3         | 0.3.0   | Configurar sensores                                  | 
| 4         | 0.4.0   | Monitorización remota de los valores de los sensores | 
| 5         | 0.5.0   | Configuración de dashboard de monitorización         | 
| 6         | 0.6.0   | Consulta y exportación de datos históricos           |
| 7         | 1.0.0   | Revisión de aplicación y últimas mejoras             |
###### *Tabla 5.2.1: Iteraciones a realizar previstas*

En cada iteración definiremos una serie de tareas de menor tamaño que contemplen los pasos que tenemos que dar para llegar a cumplir el requerimiento. Para ello nos apoyaremos en una pizarra Kanban donde incluiremos tarjetas con cada una de las tareas a realizar. El flujo por el que pasarán las diferentes tareas será "Por hacer", "En progreso", "En revisión" y "Hecho" tal y como se muestra en la Figura 5.2.1.

Además, para guardar un registro de las iteraciones realizadas utilizaremos JIRA, donde comentaremos como se ha implementado cada de las tareas y el código asociado a la misma. JIRA nos proporciona también la posibilidad de tener una pizarra de planificación para el proyecto, la usaremos también para poder visualizar en cualquier momento el estado de la iteración.

![](./imagenes/pizarra_planificacion.jpg)
###### *Figura 5.2.1: Pizarra usada para la gestión de tareas*

