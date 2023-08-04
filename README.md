
# Guía de Configuración del CH552 para Programar en Arduino

La guía de configuración del CH552, pretende dar a conocer la forma de instalación y configuración del microcontrolador. El CH552 es un MCU de núcleo E8051 mejorado, compatible con el conjunto de instrucciones MCS51. Admite una frecuencia de reloj del sistema de hasta 16 MHz en el IDE ARDUINO. Tiene una ROM de memoria de programa de 16K incorporada, iRAM interna de 256 bytes y xRAM interna de 1K byte. Y xRAM admite acceso directo a memoria (DMA). Ademas viene incorporado ADC, detección de tecla táctil capacitiva, 3 temporizadores y captura de señal y PWM, 2 UART, SPI, controlador de dispositivo USB y transceptor de velocidad completa y otros módulos funcionales.


![Front image](/img/systemblockdiagram.png)


**Para mayor información consulte la pagina oficial  WCH**
>https://www.wch-ic.com/products/CH552.html

##  [Ch55xduino](https://github.com/DeqingSun/ch55xduino/tree/ch55xduino): Instalación

Ch55xduino es una API de programación similar a Arduino para CH55X, una familia de MCU USB MCS51 de bajo costo. El proyecto intenta eliminar la dificultad de configurar un entorno de compilación. El sistema mínimo solo requiere un chip, 2 condensadores de desacoplamiento y una resistencia pull-up opcional.

![Front image](/img/basic_mount.png)

La integración automática al IDE es compatible a través del Arduino Boards Manager. Esta es la Forma recomdendada por el desarrollador.

Inicie Arduino-IDE. En *Archivo->Preferencias*, pestaña *Configuración*, ingrese en el *"Gestor de URLs Adicionales de Tarjetas"* la siguiente URL:

> https://raw.githubusercontent.com/DeqingSun/ch55xduino/ch55xduino/package_ch55xduino_mcs51_index.json

* Abrir *Herramientas->Placa:...->Gestor de tarjetas*
* Encuentra Ch55xduino escribiendo 'ch' en la línea de búsqueda
* Haga clic en la entrada de la lista
* Haga clic en *Instalar*.

Ahora debería encontrar una nueva entrada *CH55x Boards* en la lista en
*Herramientas->Placa:...*

* Eligir la *Placa CH552* de la lista
* abrir el ejemplo estándar de Blink desde *Archivo->Ejemplos->01. Básico->Blink*
* Cambiar el número de pin en el ejemplo Blink. Por defecto el led encenderá en el pin 33, si tiene LED en P3_0, cambiar por el pin 30.
* compílalo presionando *Verificar*
* Si su placa nunca se usó con ch55xduino antes, debe hacer que el chip ch55x ingrese al modo de cargador de arranque. Debe desconectar el USB y apagar el ch55x, conectar la resistencia pull-up en la línea D+ (generalmente una resistencia de 10K entre D+ y 5V, controlada por un botón o pads adyacentes). Luego conectas USB. y presiona *Subir*. Además, un nuevo chip en blanco ingresará automáticamente al gestor de arranque.
* Si usó ch55xduino una vez y su código no bloquea el subsistema USB, simplemente puede presionar * Cargar *. Arduino y el firmware patearán el chip en el gestor de arranque automáticamente.
## Appendix

Any additional information goes here


## Acknowledgements

 - [Awesome Readme Templates](https://awesomeopensource.com/project/elangosundar/awesome-README-templates)
 - [Awesome README](https://github.com/matiassingers/awesome-readme)
 - [How to write a Good readme](https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project)


## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://katherineoelsner.com/)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/)
[![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/)

