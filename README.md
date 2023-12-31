# 1er-Parcial-SPD

## 📋 Documentación. 
***
![Imagen no encontrada](./images/ArduinoTinkercad.jpg "Tinkercad")

 
## Proyecto:

![Imagen no encontrada](./images/proyecto.jpg "Parcial Nº1 SPD - UTN")

## Descripción.  
Es un proyecto que incluye diversos componentes, tales como la placa Arduino, botones, interruptor deslizante (switch), motor de corriente continua, sensores de temperatura y de luz ambiental, entre otros.


- **Funcionamiento del sistema:** se implementa un algoritmo que permite que el usuario elija una temperatura y cuando esta es menor a la capturada por el sensor, se encienda el motor. Además, si la luz ambiental supera determinado nivel, el motor aumentara su velocidad.
   
- **Interfaz de usuario:** 3 botones, uno para subir, otro para bajar y otro para
reiniciar el display, 1 interruptor deslizante para elegir la opcion de contar numeros primos (que a su vez detiene el motor).


## 🔗 Links.
***
```Enlace del proyecto en Tinkercad.```

- [Proyecto](https://www.tinkercad.com/things/0J0lJDcWFl8)
- [Proyecto con 4ta modificacion](https://www.tinkercad.com/things/lEXtqGn8QLB)

```Enlace al código del programa.```

- [Código](https://github.com/camilagargiulo/1er-Parcial-SPD/blob/main/codigo.txt)
- [Código 4ta modificacion](https://github.com/camilagargiulo/1er-Parcial-SPD/blob/main/codigo_4Parte.txt)

## COMPONENTES: 

### _MOTOR DE CORRIENTE CONTINUA._

- El motor de corriente continua, denominado también motor de corriente directa, motor CC o motor DC, es una máquina que convierte energía eléctrica en energía mecánica, provocando un movimiento rotatorio, gracias a la acción de un campo magnético.
Existe en Arduino una restricción adicional en cuanto a la potencia, ya que la suma de todas las corrientes de salida en un momento determinado no puede superar los 300mA.
Esta potencia es suficiente para encender un LED, un pequeño servomotor de 9g, o encender algún sensor, pero no es suficiente para alimentar cargas mayores. Si queremos mover una carga superior, como un motor de corriente continua, tendremos que emplear una etapa de amplificación como un transistor BJT. No es recomendable conectar directamente el motor al Arduino ya que puede afectar su durabilidad. 
- #TRANSISTOR:  Puede ser trabajado como un amplificador o un interruptor. En este caso nos sirve como un amplificador para regular la velocidad del motor.
La base me permite controlar el flujo de corriente, es la que recibe la corriente y la regula como tal, funciona como un botón, cuando recibe alimentación se abre y permite pasar la corriente. El colector es el que muestra todo el proceso de amplificación. El emisor se conecta al negativo. El pin PWM permite manejar un rango entre 0 y 255, conecto la base a ese pin y lo configuro como una salida, en la cual voy a controlar el funcionamiento del motor.

### _SENSOR DE TEMPERATURA._

- Un sensor de temperatura Arduino es un dispositivo que se utiliza para medir la temperatura del entorno circundante y convertirla en una señal eléctrica que puede ser interpretada por una placa de desarrollo Arduino. Es un sensor que nos dará valores analógicos de temperatura, convirtiendo la temperatura en un voltaje análogo. En el proyecto se incorpora el sensor de temperatura “TMP36”. 

### Integración en el proyecto.
Los componentes se integraron al proyecto de manera que el motor inicia su trabajo cuando el sensor de temperatura envía una señal al Arduino que es traducida en grados a través de una función map(), y luego comparada con la establecida por el usuario a través de los botones que manejan el contador. Podría asociarse al funcionamiento de un aire acondicionado, que se enciende cuando la temperatura difiere de la emitida por el control remoto y se apaga cuando se alcanza la misma (cuando coinciden). 

### _SENSOR DE LUZ AMBIENTAL O FOTOTRANSISTOR._

- Un sensor de luz ambiental en Arduino es un dispositivo que permite medir la intensidad de la luz en el entorno circundante. Este tipo de sensor convierte la cantidad de luz que recibe en una señal eléctrica que puede ser interpretada por la placa de desarrollo Arduino.
La conexión de un sensor de luz ambiental a una placa Arduino generalmente implica conectar los pines del sensor a los pines de entrada/salida analógicos o digitales de la placa. Luego, a través de la lectura de los valores del sensor, se puede ajustar la iluminación, activar o desactivar dispositivos en función de la luz presente en el entorno, o utilizar la información para crear proyectos interactivos y creativos

### Integración en el proyecto.
La utilización del sensor de luz ambiental se incorporó al proyecto de la siguiente manera: cuando el motor está encendido y la lectura de luz supera un determinado valor, el motor aumentará su velocidad. Al igual que con el sensor de temperatura, los valores se traducen en una función map() y luego se analizan en el código.

## CONCEPTOS CLAVE:

### _MULTIPLEXACION._

- La multiplexación es una técnica utilizada en telecomunicaciones y electrónica para transmitir múltiples señales o flujos de datos a través de un medio de transmisión compartido. Su propósito principal es maximizar la eficiencia del uso del ancho de banda y permitir la transmisión simultánea de múltiples señales a través de un canal de comunicación común.
En este proyecto la multiplexación se utiliza ya que tengo los mismos 7 segmentos para los dos displays, porque no alcanzan los pines del Arduino. Esta técnica me permite mostrar un numero de dos dígitos, mostrando primero la decena y luego la unidad, pero a una velocidad tan rápida que no es posible distinguir cuando esta apagado uno y prendido el otro. Es decir, se envían los bits de un display, lo prendo (cambio el común a LOW) y lo apago (cambio el común a HIGH) y repito lo mismo con el segundo.

### _FUNCION MAP._

- La función map en Arduino es una función que permite mapear o reescalar un valor de un rango a otro. Esta función es útil cuando se trabaja con valores de entrada que se encuentran en un rango específico y se necesita convertirlos a un rango diferente. Por ejemplo, si se tiene un sensor que produce valores entre 0 y 1023, pero se necesita mapear estos valores a un rango diferente, la función map puede realizar esta transformación de manera conveniente.

La sintaxis de la función es la siguiente:
 ~~~ C (Lenguaje del código)
map (valor, inicioRango1, finRango1, inicioRango2, finRango2);
~~~

***
##  **📚 Fuentes**

- [Tecnicatura Universitaria en Programación - UTN](http://www.sistemas-utnfra.com.ar/#/pages/carrera/tecnico-programacion/resumen)
- [Markdown-Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
- [Conexion Transistor](https://www.youtube.com/watch?v=fJKPeiwi0Pc)
- [Conexion Sensor de luz ambiental](https://www.youtube.com/watch?app=desktop&v=kv6r6HzJDqw)
***
 
