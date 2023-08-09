
# Guía de Configuración del CH552 para Programar en Arduino

La guía de configuración del CH552, pretende dar a conocer la configuración del microcontrolador en un entorno de facil uso. 

El CH552 es un MCU de núcleo E8051 mejorado, compatible con el conjunto de instrucciones MCS51. Admite una frecuencia de reloj de hasta 24 MHz. Tiene una ROM de memoria de programa de 16K incorporada, iRAM interna de 256 bytes y xRAM interna de 1K byte. Y xRAM admite acceso directo a memoria (DMA). Ademas viene incorporado con  ADC, detección de tecla táctil capacitiva, 3 temporizadores y captura de señal y PWM, 2 UART, SPI, controlador de dispositivo USB y transceptor de velocidad completa y otros módulos funcionales.


![systemblockdiagram](/img/systemblockdiagram.png)


**Para mayor información consulte la pagina oficial  WCH**
>https://www.wch-ic.com/products/CH552.html


## [Ch55xduino en Windows](https://github.com/DeqingSun/ch55xduino/tree/ch55xduino)
Para configurar el CH552 ya existen proyectos que integran y nos facilitan la configuración del microcontrolador, la API Ch55xduino para Arduino permite hacer uso de familia de MCU USB MCS51. El proyecto mencionado intenta eliminar la dificultad de configurar un entorno de compilación. El ![sistema mínimo solo requiere un chip](/hardware/CH552G Basic configuration.pdf), 2 condensadores de desacoplamiento y una resistencia pull-up opcional. 

![basic_mount](/img/basic_mount.png)

**Instalación**

La integración automática al IDE es compatible a través del Arduino Boards Manager. Esta es la forma recomdendada por el desarrollador.

Inicie Arduino-IDE. En *Archivo->Preferencias*, pestaña *Configuración*, ingrese en el *"Gestor de URLs Adicionales de Tarjetas"* la siguiente URL:

> https://raw.githubusercontent.com/DeqingSun/ch55xduino/ch55xduino/package_ch55xduino_mcs51_index.json

* Abrir *Herramientas->Placa:...->Gestor de tarjetas*
* Encuentra Ch55xduino escribiendo 'ch' en la línea de búsqueda
* Haga clic en la entrada de la lista
* Haga clic en *Instalar*.

Ahora debería encontrar una nueva entrada *CH55x Boards* en la lista en
*Herramientas->Placa:...*

* Eligir la *Placa CH552* de la lista
* Abrir el ejemplo estándar Blink desde *Archivo->Ejemplos->01. Básico->Blink*
* Por defecto el led se encuentra configurado en el pin 30, si el LED se configurado en otro puerto, cambiar por el pin coonfigurado reconectar para realizar la prueba.
* Compilar presionando *Verificar*
* Si su microcontrolador nunca se usó con ch55xduino antes, debe hacer que el chip ch552 ingrese al modo de BOOT(cargador de arranque). Este método consiste en desconectar el USB y apagar el ch552, conectar la resistencia pull-up en la línea D+ (generalmente una resistencia de 10K entre D+ y 5V, controlada por un botón o pads adyacentes).

![buttons_leds](/img/button_leds.png)

 Posteriormente conectar el USB. y presionar *Subir*. 

Tip: Un nuevo chip en blanco ingresará automáticamente al gestor de arranque.

* Si usó ch55xduino una vez y su código no bloquea el subsistema USB, simplemente puede presionar *Cargar*. Arduino y el firmware cargará el chip en el gestor de arranque automáticamente.


## Conexión con tarjeta [Dap Cat ](https://uelectronics.com/producto/dap-cat-debugger-programador-arm-interfaz-cmsis-dap/)
El DAP Cat programmer es un programador SWD para procesadores ARM Cortex, y hace uso del microcontrolador CH552G. En el caso de la configuración para su uso en modo tarjeta de prácticas se configura con los pasos mencionados, la placa ya contiene la conexion para el led en el pin 30. 

![dap cat](/img/dap-cat.png)

* El modo de trabajo es ingresando al modo de BOOT. 
* Posteriormente conectar el USB. y presionar *Subir*. 

## Consideraciones adicionales

### Controlador USB

Ch55xduino es compatible con los métodos de carga USB y Serial. Si el puerto USB del chip CH55x está conectado a una computadora directamente, se recomienda el método USB.

Existen situaciones en las que el IDE de Arduino no elije o permite elegir directamente el puerto serial, la recomendación hacer la prueba de correr el ejemplo en caso de algun error verificar que el controlador del dispositivo se encuentre instalado. 


### Controlador

La herramienta de carga actual puede usar el controlador [CH375](https://www.wch-ic.com/search?q=CH375&t=downloads) predeterminado y coexistir con la [WCHISPTool] oficial (http://www.wch.cn/downloads/WCHISPTool_Setup_exe.html), en caso de que el controlador presente problemas es recomendable cambiar la version del controlador a WinUSB o libusb-win32, mediante [Zadig](https://zadig.akeo.ie/).

![Imagen de CDC de Zadig](/img/driver.png)

Posteriormente instalar individualmente el controlador [CH375](https://www.wch-ic.com/downloads/CH372DRV_EXE.html).

## Prueba de soporte de versiones:

Arduino IDE versions 2.1.1 ,  versiones mayores  >=1.8.19 debería trabajar.

* Windows: Pruebas en Windows 11 y 10.
* Versión de CH55xduino 0.0.16 