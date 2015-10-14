# Introducción


## Descripción general

Vivimos en un mundo cada vez más conectado, la mayor parte de la población dispone actualmente de teléfonos inteligentes, tabletas, ordenadores... todos ellos conectados a internet. En un futuro próximo se unirán más dispositivos, lo que han los expertos han denominado el **Internet de las Cosas**. Próximamente convivirán entre nosotros multitud de aparatos conectados que compartirán información entre si. Una primera oleada de estos dispositivos son los llamados *wearables*, o aparatos que nos ponemos como si una prenda más de vestir se tratara. Pero hay más dispositivos por llegar, de todo tipo, que estarán conectados de forma autónoma, se comunicarán entre ellos y que suministrarán información a internet por si mismos.

Uno de estos dispositivos son los sensores de temperatura, o también denominados **termógrafos**. Un termógrafo es un instrumento de registro electrónico que monitoriza y reporta los diversos cambios en las condiciones del medio ambiente en el tiempo. Los termógrafos pueden medir temperatura, que unido a otro tipo de sensores nos permite obtener también humedad relativa, intensidad de la luz, voltaje, presión, golpes y otros. Debido a que son dispositivos autónomos, los termógrafos son convenientemente utilizados para verificar y controlar la calidad de la manipulación de cualquier producto durante su almacenamiento, transporte o distribución. Debido a que estos dispositivos no suelen necesitar ser conectados a una fuente de poder externa, éstos pueden viajar junto con sus productos mientras continuamente se registran los datos específicos que se necesitan recopilar.

En reconocimiento a la creciente demanda de una administración óptima de la **cadena de frío**, los ingenieros han desarrollado termógrafos miniaturizados, con batería, equipados con un pequeño microcontrolador, algún tipo de sistema de almacenamiento de datos y uno o varios sensores. Algunos termógrafos integran la información en una pequeña tira de papel, otros consisten en un pequeño dispositivo autónomo, mientras otros pueden necesitar incluso conectarse a un ordenador personal. Este tipo de soluciones, aunque funcionales, tienden a tener una serie de deficiencias:

- Para obtener la información del termógrafo es necesario conectarlo mediante cableado a un ordenador
- Suele ser necesario usar un software especializado para analizar, organizar e imprimir los datos
- Además, en todos estos tipos de dispositivos, para obtener la información del termógrafo es necesario conectarlo mediante cableado a un ordenador lo que implica de una instalación allí donde se requiere su uso, con el coste de mantenimiento que ello conlleva.


**// TODO mejorar legibilidad, añadir listas, negritas, etc para que no resulte pesada la lectura**

## Objetivo

Con el propósito descrito y una vez establecido la necesidad de solventar los impedimentos anteriormente descritos, algunos ingenieros han creado modelos de termógrafos inalámbricos que no requieren instalación y que, la recogida de datos y programación del mismo se realiza sin necesidad de cableado. Esto unido al uso de baterías y de protocolos de comunicación de bajo consumo como puede ser “ZigBee” (IEEE 802.15.4) o "Bluetooth LE" hacen que la autonomía de este tipo de dispositivos no sea un impedimento a la hora de crear una infraestructura para utilizarse en un entorno de producción real.

El problema de este tipo de soluciones es, a día de hoy, la extracción y monitorización de la temperatura de los termógrafos, y es que, aunque se pueda recoger de forma inalámbrica, no existe en el mercado una solución para monitorizar esta temperatura en tiempo real, sino que se observa a posteriori. En estas situaciones sólo se puede cerciorar que se ha roto la cadena de frío. Si esto sucede con productos muy sensibles a la temperatura sólo sirve para constatar que se ha echado a perder el producto en cuestión. Lo deseado sería actuar ante dicho evento, previniendo la pérdida del producto.

Por lo tanto el **objetivo** del proyecto consiste en desarrollar una solución de monitorización de termógrafos inalámbricos en tiempo real haciendo uso de dispositivos que se pueden encontrar actualmente en el mercado. Se buscará el tipo de termógrafo inalámbrico más conveniente y para recuperar y monitorizar la información se usará un *smartphone* que hará las veces de centralita de información. Además, se proporcionará una solución para la monitorización remota de la temperatura de los termógrafos a través de internet. La solución planteada no debe de suponer un alto coste de implantación, mantenimiento o reemplazo. Resumiendo, la solución propuesta debe cumplir las siguientes características:

- Ser fácil de instalar e implantar.
- Integrable con cualquier sistema de gestión.
- Adaptarse para diferentes casos de uso.
- No suponer un alto coste.


## Bibliografía

http://en.wikipedia.org/wiki/Wearable_computer

http://es.wikipedia.org/wiki/Internet_de_las_cosas

(Wikipedia, 2012) Wikipedia: Termógrafo,
 http://es.wikipedia.org/wiki/Term%C3%B3metro#Term.C3.B3grafo , 2012.

(Wikipedia, 2012) Wikipedia: Zigbee - Protocolo de comunicación de bajo consumo, http://es.wikipedia.org/wiki/ZigBee, 2012.

http://es.wikipedia.org/wiki/Bluetooth_de_baja_energ%C3%ADa

(Transporte Profesional, 2011) Exigencias de utilización de termógrafos para el transporte de ultracongelados,
http://www.transporteprofesional.es/actualidad/72-union-europea/2512-se-establecen-las-exigencias-de-utilizacion-de-termografos-para-el-transporte-de-ultracongelados.html, 2011.

(Tacograferos, 2011) Termógrafo,
http://tacograferos.blogspot.com.es/2011/03/termografo.html, 2011.

(Evidencia, 2012) ¿Que es un registrador de temperatura?, http://www.evidencia.biz/espanol/what-is/index.htm , 2012.
