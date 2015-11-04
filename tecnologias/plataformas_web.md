# 3.3. Plataforma web

Una vez elegida la plataforma móvil y el termógrafo apropiado nos quedaría por decidir cual es la mejor solución para monitorizar de forma remota los datos que se recolectan de los sensores. Intentaremos buscar una solución que nos permita visualizar los datos enviados y que se muestre de forma gráfica el estado actual de los sensores. 

Existen una inmensidad de tecnologías y maneras para desarrollar una aplicación web para monitorizar los datos de temperatura. Se estuvieron barajando varias posibilidades incluida la de hacer la aplicación web desde cero, pero la verdad, que este tipo de aplicación con gestión de tablas CRUD creo que no suponía el verdadero reto de este proyecto y se decidió por usar varios servicios que ya gestionan esta parte de forma genérica y adaptarlo para el propósito de esta aplicación.

El servicio elegido para la parte de almacen de datos será **Parse** y para mostrar la monitorización en tiempo real será **Ducksboard**. A continuación se explicará brevemente las caracteristicas de ambas plataformas.

### Parse
- Se trata de un *backend as a service*.
- Tiene capa de acceso y persistencia en base de datos.
- Almacenamiento de ficheros.
- Gestión de usuarios y permisos de accesos.
- Servicio de mensajería push.
- Acceso a los datos a través de api REST.
- *Hosting* de aplicaciones web
- Capa de análisis de la aplicación.
- Gestión y reportes de error.
- SDK para para smartphones Android, iPhone y Windows Phone.
- Buena documentación de la plataforma.
- Gran comunidad de usuarios.

### Ducksboard
- Se trata de un *dashboard as a service*.
- Da la posibilidad de mostrar gráficas de servicios de terceros.
- Permite crear gráficas personalizadas con datos propios.
- Api REST para push de datos a las diferentes gráficas.
- Gráficas animadas y visualmente atractivas.
- Modo TV para mostrar las gráficas en pantalla completa.
- Buena documentación de los servicios.