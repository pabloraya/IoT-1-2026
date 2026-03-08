2.1 Requerimientos Funcionales

El sistema debe cumplir las siguientes funciones:

Detectar la distancia entre el sensor y un objeto.

Encender un LED cuando el objeto se encuentre a una distancia lejana.

Cambiar al segundo LED cuando el objeto se acerque.

Encender el tercer LED cuando el objeto esté muy cerca.

Apagar los demás LEDs cuando uno esté activo.

Mostrar la distancia detectada en el monitor serial.

2.2 Requerimientos No Funcionales

El sistema debe cumplir las siguientes características:

Bajo consumo de energía.

Fácil implementación en hardware.

Código modular usando programación orientada a objetos.

Fácil mantenimiento y modificación del software.

Tiempo de respuesta rápido en la detección de distancia.

3. Diseño del Sistema
3.1 Diagrama de Bloques

El sistema está compuesto por los siguientes bloques:

Sensor ultrasónico

Microcontrolador Arduino

Sistema de salida (LEDs indicadores)

Flujo del sistema:

Objeto → Sensor Ultrasónico → Arduino → LEDs Indicadores

El sensor mide la distancia y envía la información al Arduino, el cual procesa los datos y decide qué LED encender.

3.2 Diagrama de Circuito

El circuito está compuesto por:

1 Arduino Uno

1 sensor ultrasónico HC-SR04

3 LEDs

3 resistencias de 220Ω

Protoboard

Cables de conexión

Conexiones principales:

Sensor ultrasónico
Pin Sensor	Arduino
VCC	5V
GND	GND
TRIG	Pin 6
ECHO	Pin 7
LEDs
LED	Pin Arduino
LED 1	8
LED 2	9
LED 3	10

Cada LED está conectado en serie con una resistencia para limitar la corriente.

3.3 Diagrama de Arquitectura del Sistema

La arquitectura del sistema se compone de tres capas:

Capa de Hardware

Incluye todos los componentes físicos:

Arduino Uno

Sensor ultrasónico

LEDs

Resistencias

Protoboard

Capa de Control

Se encarga de procesar la información proveniente del sensor y ejecutar la lógica del sistema.

Capa de Salida

Muestra el resultado mediante los LEDs indicadores.

4. Diagramas Estructurales y de Comportamiento
4.1 Diagrama Estructural (Clases)

El software fue desarrollado utilizando programación orientada a objetos con las siguientes clases:

Clase SensorUltrasonico

medirDistancia()

Clase Led

encender()

apagar()

Clase Controlador

actualizarEstado()

4.2 Diagrama de Comportamiento (Flujo del sistema)

Proceso del sistema:

El sensor envía una señal ultrasónica.

La señal rebota en un objeto.

El sensor mide el tiempo de retorno.

Arduino calcula la distancia.

Según la distancia:

Distancia > 30 cm → LED 1

Distancia entre 15 y 30 cm → LED 2

Distancia < 15 cm → LED 3

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
> 30 cm	LED 1 encendido	Correcto
15 – 30 cm	LED 2 encendido	Correcto
< 15 cm	LED 3 encendido	Correcto

Las pruebas demostraron que el sistema responde correctamente a los cambios de distancia.

7. Resultados

El sistema logró detectar correctamente la distancia entre el sensor y el objeto.

Los LEDs funcionan como indicadores visuales claros que permiten identificar fácilmente la proximidad del objeto.

Además, el uso de programación orientada a objetos permitió desarrollar un código más organizado y modular.

8. Conclusiones

Se logró implementar un sistema funcional de detección de distancia utilizando Arduino.

El sensor ultrasónico permite medir distancias con buena precisión en rangos cortos.

La programación orientada a objetos facilita la organización del código y su mantenimiento.

Los LEDs permiten una visualización simple del estado del sistema.

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
