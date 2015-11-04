# 3.1. Plataformas móviles

En el mercado existen multitud de fabricantes e incontables modelos de *smarthphone* disponibles para el consumidor, pero no tanta diversidad de plataformas móviles para el desarrollo. Vamos a a realizar una introducción sobre las diferentes alternativas existentes y ver las características de cada una.

## 3.1.1. iOS
- Sistema operativo creado por *Apple* que fue lanzado en Junio de 2007 con el primer *iPhone*.
- Programación en *Objetive C* y *Swift*.
- Código fuente propietario.
- Sólo disponible en dispositivos de *Apple*: *iPhone*, *iPad* y *iPod Touch*.
- Soporte de *Bluetooth Low Energy* para dispositivos *iOS 5* en adelante.
- Cuota de mercado en 2015 del 18.3%.
- Curva de aprendizaje personal alta, ya que desconozco por completo el desarrollo en esta plataforma y además es necesario un ordenador *Mac* del que carezco.


## 3.1.2 Android
- Sistema operativo con kernel de *Linux* creado por *Google* que fue lanzado en Septiembre de 2008.
- Programación en *Java*.
- El código fuente es libre.
- Disponible en terminales de multitud de marcas como *Samsung*, *Sony*, *HTC*, *LG*, *Motorola*, *ASUS*, etc.
- Soporte de *Bluetooth Low Energy* a partir de la API 4.3 de *Android*.
- Cuota de mercado en 2015 del 78%.
- Curva de aprendizaje personal baja, ya que he desarrollado con anterioridad en *Java* y he realizado varias aplicaciones sencillas en esta plataforma.


## 3.1.3. Windows Phone
- Sistema operativo creado por *Microsoft* que fue lanzado en Noviembre de 2010.
- Programación en *C#* y *Visual Basic.NET*.
- El código fuente es propietario.
- Disponible en terminales de multitud de marcas como *Microsoft/Nokia*, *Acer*, *ASUS*, *Dell*, *HP*, *Lenovo*, *Toshiba*, etc.
- Soporte de Bluetooth Low Energy a partir de Windows Phone 8.1.
- Cuota de mercado en 2015 del 2.7%.
- Curva de aprendizaje personal media, no he desarrollado ninguna aplicación para Windows Phone con anterioridad pero si he utilizado Visual Studio.


## 3.1.4. BlackBerry 10
- Sistema Operativo creado por BlackBerry que fue lanzado en Enero de 2013.
- Programación nativa en C++ con Qt/Cascades, pero es compatible con aplicaciones Android realizadas en Java.
- El código fuente del sistema operativo es propietario pero de Qt es libre.
- Sólo disponible en terminales fabricados por BlackBerry.
- Soporte de Bluetooth Low Energy a partir de la versión 10.0.
- Cuota de mercado en 2015 del 0.3%.
- Curva de aprendizaje personal baja. Estoy muy familiarizado con la plataforma y he realizado ya multiples aplicaciones, de hecho mi terminal personal actualmente es una BlackBerry Z10.


## 3.1.5. Desarrollo Hibrido HTML5 
- Existen varios sistemas operativos con desarrollos en HTML 5 como Firefox OS, Sailfish OS. Pero también se puede desarrollar en las plataformas anteriores con frameworks híbridos como IONIC, Mobile Angular UI, Intel XDK, Appcelerator Titanium, Sencha Touch, Kendo UI, PhoneGap y Apache Cordova
- Programación en HTML5, CSS3 y Javascript
- El código fuente es libre.
- Disponible para todas las plataformas anteriores.
- Soporte de Bluetooth Low Energy no nativo y dependiente de extensiones de terceros mantenidas por la comunidad. 
- Cuota de mercado en sistemas operativos en 2015 inferior de 0.1% pero portable a todas las plataformas.
- Curva de aprendizaje personal media. Estoy familiarizado con el desarrollo web pero no he realizado una aplicación móvil completa con un framework html5.
 


| Plataforma        | Lenguaje nativo           | Bluetooh LE   | Cuota 2015 | Curva de aprendizaje |
| ----------------- | ------------------------- | ------------- | ---------- | -------------------- |
| **iOS**           |  Objetive C, Swift        | Si (OS 5+)    | 18.30%     | Alta                 |
| **Android**       |  Java                     | Si (OS 4.3+)  | 78.00%     | Baja                 |
| **Windows Phone** |  C#, Visual Basic.NET     | Si (OS 8.1+)  | 2.70%      | Media                |
| **BlackBerry 10** |  C/C++, Qt/Cascades       | Si (OS 10.0+) | 0.30%      | Baja                 |
| **Híbrido HTML5** |  HTML5, CSS3 y Javascript | con plugins   | 100%       | Media                |
###### *Tabla 1: Comparativa de plataformas móviles*


Una vez analizados las diferentes plataformas disponibles llegamos a la conclusión de que vamos a **desarrollar la aplicación en Android** ya que, aunque no es la plataforma en la que estoy más familiarizado, el aprendizaje de la misma no me va a resultar muy dificultoso ya que me manejo bien con Java. Por otra parte, también tiene soporte para conectarse con dispositivos Bluetooth Low Energy y es la plataforma lider en cuanto a ventas de terminales. Además, como BlackBerry 10 tiene soporte para aplicaciones Android, también debería funcionar la aplicación en esta plataforma.




