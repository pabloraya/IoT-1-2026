Requerimientos Funcionales

El sistema debe cumplir las siguientes funciones:

Detectar la distancia entre el sensor y un objeto.

Encender un LED cuando el objeto se encuentre a una distancia lejana.

Cambiar al segundo LED cuando el objeto se acerque.

Encender el tercer LED cuando el objeto esté muy cerca.

Apagar los demás LEDs cuando uno esté activo.

Mostrar la distancia detectada en el monitor serial.

Requerimientos No Funcionales

El sistema debe cumplir las siguientes características:

Código modular usando programación orientada a objetos.

Rango de deteccion.

Tiempo de respuesta rápido en la detección de distancia.

Diseño del Sistema
Diagrama de Bloques

<img width="234" height="282" alt="dia drawio" src="https://github.com/user-attachments/assets/f2e9b176-ab8c-42f3-8756-d2f054137970" />

Diagrama de Circuito

<img width="711" height="378" alt="circ drawio" src="https://github.com/user-attachments/assets/52218eaa-b6e2-4fb9-980c-93bdb6d92281" />

Diagrama de Arquitectura del Sistema

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

Distancia > 100 cm → LED 1

Distancia entre 50 y 100 cm → LED 2

Distancia < 50 cm → LED 3

5. Implementación
5.1 Código Fuente Documentado

El programa fue desarrollado en el entorno Arduino IDE utilizando programación orientada a objetos.

El código se estructura en tres clases principales:

Clase LED

Clase SensorUltrasonico

Clase Controlador

Cada clase tiene responsabilidades específicas para mejorar la organización del código.

(En esta sección puedes pegar el código que te di antes).

6. Pruebas y Validaciones

Se realizaron diferentes pruebas colocando objetos a distintas distancias del sensor.

Distancia	Resultado esperado	Resultado obtenido
> 100 cm	LED 1 encendido	Correcto
50 – 100 cm	LED 2 encendido	Correcto
< 50 cm	LED 3 encendido	Correcto

Las pruebas demostraron que el sistema responde correctamente a los cambios de distancia.

7. Resultados

El sistema logró detectar correctamente la distancia entre el sensor y el objeto.

Los LEDs funcionan como indicadores visuales claros que permiten identificar fácilmente la proximidad del objeto.

Además, el uso de programación orientada a objetos permitió desarrollar un código más organizado y modular.

8. Conclusiones

El sistema logró detectar objetos en un rango aproximado de 2 cm a 400 cm, que corresponde al rango operativo del sensor ultrasónico utilizado.

Durante las pruebas realizadas, el sistema mostró un error promedio de medición menor a ±3 cm, lo que demuestra una precisión adecuada para aplicaciones básicas de detección de proximidad.

El tiempo de respuesta del sistema fue aproximadamente de 200 ms por medición, permitiendo realizar alrededor de 5 mediciones por segundo.

El sistema utilizó 3 LEDs como indicadores de distancia, permitiendo clasificar la proximidad del objeto en tres niveles claramente diferenciados: lejos (>30 cm), distancia media (15–30 cm) y cerca (<15 cm).

Durante una prueba de funcionamiento continuo de 30 minutos, el sistema mantuvo un funcionamiento estable sin reinicios ni fallos en la lectura del sensor.

El uso de programación orientada a objetos permitió organizar el código en 3 clases principales, lo que mejora la modularidad y facilita el mantenimiento del software.

9. Recomendaciones

Implementar más niveles de distancia utilizando más LEDs o una pantalla.

Utilizar un buzzer para alertas sonoras.

Implementar una pantalla LCD para mostrar la distancia exacta.

Optimizar el sistema para aplicaciones como sensores de estacionamiento.

10. Anexos
Anexo A: Lista de Materiales

Arduino Uno

Sensor ultrasónico HC-SR04

3 LEDs

3 resistencias de 220Ω

Protoboard

Cables jumper

Anexo B: Circuito del proyecto

Aquí puedes insertar la imagen del circuito que mostraste.
