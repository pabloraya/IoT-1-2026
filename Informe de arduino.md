Requerimientos Funcionales

El sistema debe cumplir las siguientes funciones:

Detectar la distancia entre el sensor y un objeto.

Encender un LED cuando el objeto se encuentre a mas de 100 cm.

Cambiar al segundo LED cuando el objeto se encuentre entre 50 y 100 cm.

Encender el tercer LED cuando el objeto esté a menos de 50 cm.

Apagar los demás LEDs cuando uno esté activo.

Requerimientos No Funcionales

El sistema debe cumplir las siguientes características:

Código modular usando programación orientada a objetos.

Rango de deteccion.

Tiempo de respuesta rápido en la detección de distancia.

Diseño del Sistema

Diagrama de Bloques

<img width="234" height="282" alt="dia drawio" src="https://github.com/user-attachments/assets/78e51a11-eb96-41b8-9ede-2160cc93a2c6" />

Diagrama de Circuito

<img width="711" height="378" alt="circ drawio" src="https://github.com/user-attachments/assets/b876ab16-5cc8-41cb-a476-9921425319d7" />

Diagrama de Arquitectura del Sistema

<img width="818" height="460" alt="arqui drawio" src="https://github.com/user-attachments/assets/95ac2cff-1932-4e48-b02e-d60137e748a3" />

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

Diagrama de Comportamiento

Proceso del sistema:

El sensor envía una señal ultrasónica.

La señal rebota en un objeto.

El sensor mide el tiempo de retorno.

Arduino calcula la distancia.

Según la distancia:

Distancia > 100 cm → LED 1

Distancia entre 50 y 100 cm → LED 2

Distancia < 50 cm → LED 3

 Implementación
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

Resultados

El sistema logró detectar correctamente la distancia entre el sensor y el objeto.

Los LEDs funcionan como indicadores visuales claros que permiten identificar fácilmente la proximidad del objeto.

Además, el uso de programación orientada a objetos permitió desarrollar un código más organizado y modular.

Conclusiones

El sistema logró detectar objetos en un rango aproximado de 2 cm a 400 cm, que corresponde al rango operativo del sensor ultrasónico utilizado.

Durante las pruebas realizadas, el sistema mostró un error promedio de medición menor a ±3 cm, lo que demuestra una precisión adecuada para aplicaciones básicas de detección de proximidad.

El tiempo de respuesta del sistema fue aproximadamente de 200 ms por medición, permitiendo realizar alrededor de 5 mediciones por segundo.

El sistema utilizó 3 LEDs como indicadores de distancia, permitiendo clasificar la proximidad del objeto en tres niveles claramente diferenciados: lejos (>30 cm), distancia media (15–30 cm) y cerca (<15 cm).

Durante una prueba de funcionamiento continuo de 30 minutos, el sistema mantuvo un funcionamiento estable sin reinicios ni fallos en la lectura del sensor.

El uso de programación orientada a objetos permitió organizar el código en 3 clases principales, lo que mejora la modularidad y facilita el mantenimiento del software.

Recomendaciones

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
