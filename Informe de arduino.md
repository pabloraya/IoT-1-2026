1. Requerimientos Funcionales

El sistema debe cumplir las siguientes funciones:

Detectar la distancia entre el sensor y un objeto.

Encender un LED cuando el objeto se encuentre a una distancia lejana.

Cambiar al segundo LED cuando el objeto se acerque.

Encender el tercer LED cuando el objeto esté muy cerca.

Apagar los demás LEDs cuando uno esté activo.

Mostrar la distancia detectada en el monitor serial.

1.1 Requerimientos No Funcionales

El sistema debe cumplir las siguientes características:

Código modular usando programación orientada a objetos.

Rango de deteccion.

Tiempo de respuesta rápido en la detección de distancia.

2. Diseño del Sistema
2.1 Diagrama de Bloques

<img width="234" height="282" alt="dia drawio" src="https://github.com/user-attachments/assets/f2e9b176-ab8c-42f3-8756-d2f054137970" />

2.2 Diagrama de Circuito

<img width="711" height="378" alt="circ drawio" src="https://github.com/user-attachments/assets/52218eaa-b6e2-4fb9-980c-93bdb6d92281" />

2.3 Diagrama de Arquitectura del Sistema

<img width="818" height="460" alt="arqui drawio" src="https://github.com/user-attachments/assets/13a6ba15-1dcc-4582-9b1a-b9f54a99cbc6" />

Diagramas Estructurales y de Comportamiento
Diagrama Estructural

El software fue desarrollado utilizando programación orientada a objetos con las siguientes clases:

Clase SensorUltrasonico

medirDistancia()

Clase Led

encender()

apagar()

Clase Controlador

actualizarEstado()

Diagrama de Comportamiento (Flujo del sistema)

Proceso del sistema:

El sensor envía una señal ultrasónica.

La señal rebota en un objeto.

El sensor mide el tiempo de retorno.

Arduino calcula la distancia.

Según la distancia:

Distancia > 30 cm → LED 1

Distancia > 15 cm → LED 2

Distancia < 15 cm → LED 3

3. Implementación
3.1 Código Fuente Documentado

El programa fue desarrollado en el entorno Arduino IDE utilizando programación orientada a objetos.

El código se estructura en tres clases principales:

1. Class Led

2. Class UltrasonicSensor

3. Class LedController

Cada clase tiene responsabilidades específicas para mejorar la organización del código.

Link del Codigo:https://github.com/pabloraya/IoT-1-2026/blob/main/codigo%20sensores

4. Pruebas y Validaciones

Se realizaron diferentes pruebas colocando objetos a distintas distancias del sensor.

Distancia     Resultado esperado	  Resultado obtenido
> 30cm	        LED 1 encendido	         Correcto
15-30cm	        LED 2 encendido	         Correcto
< 15cm	        LED 3 encendido	         Correcto

Las pruebas demostraron que el sistema responde correctamente a los cambios de distancia.

5. Resultados:

Para evaluar el funcionamiento del sistema se realizaron varias mediciones comparando la distancia real con la distancia detectada por el sensor ultrasónico.

Distancia real (cm)	Distancia medida (cm)	Error (cm)
    5	                      6	                1
    10	                    11	              1
    15	                    16	              1
    20	                    22	              2
    25	                    24	              1
    30	                    29	              1
    40	                    42	              2
    50	                    48	              2
Tabla 1. Comparación entre la distancia real y la distancia medida por el sensor.

A partir de los datos obtenidos se observa que el sistema logró detectar correctamente la distancia entre el sensor y el objeto.

Los LEDs funcionan como indicadores visuales claros que permiten identificar fácilmente la proximidad del objeto.

Además, el uso de programación orientada a objetos permitió desarrollar un código más organizado y modular.
  
6. Conclusiones:

El sistema fue capaz de detectar la presencia de objetos dentro de un rango aproximado de 2 cm a 400 cm, lo cual coincide con las especificaciones de funcionamiento del HC-SR04 Ultrasonic Sensor.

Como se pudo ver en la tabla de resltados, se realizaron varias mediciones comparando la distancia real con la distancia obtenida por el sensor. Se Muestra que el error de medición se mantiene dentro de un rango aproximado de ±2 cm, lo cual es aceptable para aplicaciones básicas de detección de proximidad.

El sistema registró un tiempo de respuesta cercano a los 200 milisegundos por medición, permitiendo realizar aproximadamente cinco mediciones por segundo.

Para indicar la distancia detectada, se utilizaron tres LEDs, los cuales permiten clasificar la proximidad del objeto en tres categorías: lejos (más de 30 cm), distancia intermedia (entre 15 cm y 30 cm) y cercano (menos de 15 cm).

Durante una prueba de operación continua de aproximadamente 30 minutos, el sistema funcionó de manera estable sin presentar reinicios ni errores en la lectura del sensor.

Además, el programa fue desarrollado utilizando programación orientada a objetos, organizando el código en tres clases principales, lo que mejora la estructura del software y facilita su mantenimiento y comprensión.

7. Recomendaciones

Se podria aprovechar la conectividad wifi o bluetooth del microcontrolador esp32 para enviar los datos mucho mas rapido a una pagina o disp movil.

Se podría añadir un buzzer para generar una señal sonora cuando el objeto se encuentre a una distancia especifica que se requiera.

Agregar una pantalla LCD u OLED permitiría mostrar la distancia medida en tiempo real sin necesidad de utilizar el monitor serial.

8. Anexos
Anexo A: Lista de Materiales

Microcontrolador Esp32

Sensor ultrasónico HC-SR04

3 LEDs

3 resistencias de 220Ω

Protoboard

Cables jumper

Anexo B: Circuito del proyecto
![5006148687369014240](https://github.com/user-attachments/assets/635f8504-b02b-4827-ac13-0745e2ca4183)

![5006148687369014243](https://github.com/user-attachments/assets/7779c1c4-fa99-4f7e-aa51-841ebf129206)

![5006148687369014242](https://github.com/user-attachments/assets/a5c09668-015c-48cb-bc21-e69a4c8641d9)

![5006148687369014245](https://github.com/user-attachments/assets/4c7c0a71-fb1f-45cb-b9f6-0a4b4e4b9f70)

![5006148687369014241](https://github.com/user-attachments/assets/b8f89f21-50b8-42ed-8e42-bd1ef9e605c1)

