# 5.3. Iteracion 1: Consultar listado de sensores

En esta primera iteración nos hemos propuesto poder consultar desde la aplicación móvil qué sensores hay disponibles para conectarse. Para ello, antes que nada será necesario estudiar cuales son las principales caracteristicas del protocolo Bluetooth LE para posteriormente crear una aplicación y configurarla para que permita escanear los sensores disponibles. Además, deberemos crear una interfaz acorde con el diseño de la UI analizada en el Capitulo 5. El desglose de las tareas que vamos a realizar podemos observarla en la Tabla 5.3.1.

| Tarea | Descripción |
| -- | -- |
| 1.1 | Estudio del protocolo Bluetooth LE |
| 1.2 | Creación de proyecto para la aplicación en Android Studio |
| 1.3 | Configuración del proyecto para utilizar Bluetooth LE |
| 1.4 | Crear controlador para detectar dispositivos Bluetooth disponibles |
| 1.5 | Generar la interfaz del listado de dispositivos |
##### *Tabla 5.3.1: Tareas de la iteración 1* 


## 5.3.1 Estudio del protocolo Bluetooth LE

Al contrario que ocurría con el Bluetooth clásico, Bluetooth Low Energy está diseñado para proporcionar un significante bajo consumo energético. Android da soporte a este protocolo desde su versión 4.3, esto le permite comunicarse con sensores, monitores de ritmo cardiaco, dispositivos deportivos y muchos más. Algunos de los conceptos que hay que conocer sobre Bluetooth LE (BLE) son:

- **Generic Attribute Profile (GATT)**: el perfil GATT es una especificación general para el envío y la recepción de pequeñas piezas de datos también conocidas como "atributos" a través de una conexión BLE. Actualmente, todos los perfiles de comunicación actuales están basados en GATT. El consorcio Bluetooth tiene definidos multitud de perfiles GATT para diversos propósitos. Hay que tener en cuenta que un mismo dispositivo puede implementar varios de estos perfiles, algunos ejemplos de perfiles GATT son:
   - BAS: Nivel de batería del dispositivo
   - BLP: Consulta de presión sanguínea
   - CGMP: Control de glucosa en sangre
   - CSCP: Cadencia y velocidad en ciclismo
   - ESP: Sensor ambiental 
   - HRP: Consulta de ritmo cardiaco
    

- **Attribute Protocol (ATT)**:  También conocido como GATT/ATT. Se trata de los paquetes de comunicación usados en las comunicaciones BLE y están optimizados para usar el menor número de bytes posibles. Cada atributo está identificado de forma única por un Universally Unique Identifier (UUID) que está estandarizado en un formato de 128 bits. Los *atributos* transportados por ATT están formateados como *características* y *servicios*.

- **Característica**: una característica contiene un valor y además, opcionalmente, puede contener descriptores que describan el valor de la característica. Hay que pensar en una característica como un tipo o clase.

- **Descriptor**: Los descriptores son atributos que describen el valor de una característica. Por ejemplo, un descriptor puede contener una cadena descriptiva, el rango de aceptación de un valor, o la unidad de medida del valor que contiene la característica.

- **Servicio**: Un servicio es una colección de características. Por ejemplo, el servicio "Heart Rate Monitor" incluye características como "heart rate measurement", además de otras.

Resumiendo, podemos decir que un dispositivo Bluetooth LE puede implementar uno o varios perfiles GATT que a su vez este puede implementar uno o varios servicios, donde cada servicio puede contener una o varias características y que estas caracteristicas además de su valor puede contener ninguno o varios descriptores. Todo esto queda más claro si se observa mejor el esquema de la Figura 5.3.1.

![](./imagenes/gatt_profiles.png)
##### *Figura 5.3.1: Esquema de un perfil GATT* 


## 5.3.2 Creación de proyecto para la aplicación en Android Studio

Crear un proyecto con Android Studio no es ningún misterio. Dispone de asistentes de configuración muy intuitivos para la creación de nuevos proyecto, nosotros eligiremos el proyecto con una *Activity* en blanco como se puede observar en la Figura 5.3.2

![](./imagenes/android_studio_creacion_proyecto.jpg)
##### *Figura 5.3.2: Asistente de creación de proyecto en Android Studio* 

La estructura de un proyecto Android es muy sencilla como puede observarse en la Figura 5.3.3. Explicaremos brevemente sus partes más destacadas:

- **AndroidManifest.xml**: Es el fichero donde se especifica las características generales de una aplicación Android típica, como su nombre, su número de versión, la versión del SDK que utiliza, los permisos que necesita y las *Activitys* y los *Services* que lo componen.
- **java**: En esta carpeta se incluye todo el código de la aplicación
- **res**: En esta carpeta se encuentran los recursos, tales como los layouts de las interfaces gráficas, las imágenes, los archivos de traducciones, etc
- **assets**: Aquí se encuentran el resto de ficheros que puedan necesitarse para la aplicación, tales como páginas html para cargar la ayuda, o ficheros de bases de datos.

![](./imagenes/android_studio_estructura_proyecto.jpg)
##### *Figura 5.3.3: Estructura de proyecto Android* 
