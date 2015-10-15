## Objetivo

Con el propósito descrito y una vez establecido la necesidad de solventar los impedimentos anteriormente descritos, algunos ingenieros han creado modelos de termógrafos inalámbricos que no requieren instalación y que, la recogida de datos y programación del mismo se realiza sin necesidad de cableado. Esto unido al uso de baterías y de protocolos de comunicación de bajo consumo como puede ser “ZigBee” (IEEE 802.15.4) o "Bluetooth LE" hacen que la autonomía de este tipo de dispositivos no sea un impedimento a la hora de crear una infraestructura para utilizarse en un entorno de producción real.

El problema de este tipo de soluciones es, a día de hoy, la extracción y monitorización de la temperatura de los termógrafos, y es que, aunque se pueda recoger de forma inalámbrica, no existe en el mercado una solución para monitorizar esta temperatura en tiempo real, sino que se observa a posteriori. En estas situaciones sólo se puede cerciorar que se ha roto la cadena de frío. Si esto sucede con productos muy sensibles a la temperatura sólo sirve para constatar que se ha echado a perder el producto en cuestión. Lo deseado sería actuar ante dicho evento, previniendo la pérdida del producto.

Por lo tanto el **objetivo** del proyecto consiste en desarrollar una solución de monitorización de termógrafos inalámbricos en tiempo real haciendo uso de dispositivos que se pueden encontrar actualmente en el mercado. Se buscará el tipo de termógrafo inalámbrico más conveniente y para recuperar y monitorizar la información se usará un *smartphone* que hará las veces de centralita de información. Además, se proporcionará una solución para la monitorización remota de la temperatura de los termógrafos a través de internet. La solución planteada no debe de suponer un alto coste de implantación, mantenimiento o reemplazo. Resumiendo, la solución propuesta debe cumplir las siguientes características:

- Ser fácil de instalar e implantar.
- Integrable con cualquier sistema de gestión.
- Adaptarse para diferentes casos de uso.
- No suponer un alto coste.