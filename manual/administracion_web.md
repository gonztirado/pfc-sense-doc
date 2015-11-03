# 6.2. Administración web

Esta será la herramienta que use el usuario que tome el rol de administrador, con ella podrá  configurar las pizarras de monitorización, filtrar los datos de los sensores que necesite buscar, realizar copias de seguridad y hacer restauraciones de datos en el caso de que fuera necesario

## 6.2. Configuración de pizarras de monitorización

Cuando sea necesario **crear o editar una pizarra**, habrá que entrar en el entorno de Ducksboard y autenticarse con su usuario y password de administración. Una vez dentro de la plataforma, si se selecciona el menú de selección de panel de la derecha que se ve en la Figura 6.2.1 puede seleccionarse la opción 'Add a new dashboard'.

![](./imagenes/ducksboard_crear_dashboard.png)
##### *Figura 6.2.1: Crear nuevo dashboard en Ducksboard*

Una vez creado el panel, darle **acceso a los supervisores** es muy sencillo, basta con pulsar el icono de configuración que se ve arriba a la izquierda en la Figura 6.2.1 y seleccionar la opción "Preferences for this dashboard", una vez hecho esto aparecerá el popup que podemos ver en la Figura 6.2.2. Esta pantalla nos permite crear enlaces protegidos con password para cada supervisor que necesite visualizar el panel. Si se deseara bloquear el acceso para un supervisor, bastaría con seleccionar la opción 'Delete'.

![](./imagenes/ducksboard_configurar_supervisores.png)
##### *Figura 6.2.2: Configurar supervisores en Ducksboard*

Para añadir basta con pulsar el ícono de añadir que se encuentra en la botonera situada arriba a la izquierda del panel que se ve en la Figura 6.2.1. Una vez añadido, para configurarlo para que reciba los datos de un determinado sensor, pulsaremos sobre el widget y seleccionaremos la sección 'Data & API' que se ve en la Figura 6.2.3. Ahí podremos editar el valor del widgetID y seleccionar el identificador que estimemos oportuno.

![](./imagenes/ducksboard_configurar_widget.png)
##### *Figura 6.2.3: Configurar widget en Ducksboard*

Una vez seleccionado el widgetID necesitaremos asignarselo a un determinado sensor, para ello haremos uso de nuestro entorno de administración en Parse tal y como vemos en la Figura 6.2.4.

![](./imagenes/parse_configuracion_widget.PNG)
##### *Figura 6.2.4: Configuración de widget en Parse*

## 6.3. Filtros de datos