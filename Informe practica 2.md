 Sistema Distribuido IoT con Sensor Ultrasónico y Control de LEDs

 1. Requerimientos Funcionales y No Funcionales

 Requerimientos Funcionales

*  El sistema debe medir la distancia utilizando un sensor ultrasónico.
*  El objeto sensor debe enviar los datos al servidor mediante TCP.
*  El servidor debe procesar la información recibida.
*  El servidor debe determinar el intervalo de distancia.
*  El servidor debe enviar comandos al actuador.
*  El actuador debe encender LEDs según la instrucción recibida.

 Requerimientos No Funcionales 

*  El tiempo de respuesta del sistema debe ser menor a **2 segundos**.
*  La precisión del sensor debe tener un error máximo de **±3 cm**.
*  El sistema debe operar en una red WiFi IEEE 802.11.
*  La comunicación debe tener una tasa de éxito mayor al **95%**.
*  El sistema debe funcionar de manera continua durante al menos **30 minutos sin fallos**.

 2. Diseño del Sistema

El sistema está compuesto por tres elementos principales:

* Objeto sensor (ESP32 + HC-SR04)
* Servidor central (PC con Python)
* Objeto actuador (ESP32 + LEDs)

El flujo de datos es:

Sensor → Servidor → Actuador

 3. Diagrama de Bloques
![d bloques](https://github.com/user-attachments/assets/4fd8af93-e750-466c-b7c5-32a12769332d)
 4. Diagrama de Circuito

![d ciarcuito corregido](https://github.com/user-attachments/assets/99ac929b-c73c-45e7-9491-387e80aeb402)

 5. Diagrama de Arquitectura del Sistema

El sistema sigue una arquitectura cliente-servidor:

* Cliente 1: Sensor
* Cliente 2: Actuador
* Servidor: PC (control central)

Comunicación mediante TCP sobre WiFi.

![d arqui](https://github.com/user-attachments/assets/32ccc18f-e4af-4bc3-886b-7c23ff05f205)

 6. Especificación del Protocolo de Aplicación

El ![protocolo](https://github.com/user-attachments/assets/0cedce4f-1781-4e65-99c4-48c8e4964d34)

sistema utiliza el protocolo **TCP sobre WiFi (IEEE 802.11)** con mensajes en formato JSON.

 Sensor → Servidor

```json
{ "type": "PUT", "distance": 64 }
```


 Servidor → Actuador

```json
{ "type": "PUT", "led": "orange", "action": "blink" }
```

 Intervalos definidos

* 0: 0–50 cm → LED 1
* 1: 50–100 cm → LED 2
* 2: >100 cm → LED 3

 7. Diagramas Estructurales y de Comportamiento

* Diagrama de clases (POO)

  ![poo](https://github.com/user-attachments/assets/f2b73135-ff00-459a-a445-99a43581638c)

* Diagrama de secuencia (protocolo)

  ![secuencia](https://github.com/user-attachments/assets/ca46cd73-afd9-453a-8491-833573089234)

* Diagrama de flujo del algoritmo

![flujo corregido](https://github.com/user-attachments/assets/ae36c73f-c166-4251-afe1-31d173fc4e45)


8. Implementación

Tecnologías utilizadas

* ESP32 (microcontrolador)
* Lenguaje C++ (Arduino)
* Python (servidor)
* WiFi (comunicación)

 Estructura del sistema

* sensor.ino → código del sensor
* actuador.ino → código del actuador
* servidor.py → código del servidor

 9. Código Fuente Documentado

El código se encuentra en el repositorio organizado en tres módulos:

* Codigo Sensor P2 (https://github.com/pabloraya/IoT-1-2026/blob/main/Codigo%20sensor%20P2)
* Codigo Actuador P2 (https://github.com/pabloraya/IoT-1-2026/blob/main/Codigo%20actuador%20P2)
* Codigo Server P2 (https://github.com/pabloraya/IoT-1-2026/blob/main/Codigo%20server%20P2)

 10. Pruebas y Validaciones

 11. Resultados

 12. Conclusiones
El proyecto no pudo completarse debido a problemas de conexión del ESP32 con la red WiFi; sin embargo, se desarrolló correctamente la lógica del sistema y se identificaron factores clave que afectan la implementación de soluciones IoT en entornos reales.

13. Recomendaciones

* Implementar manejo de errores en la comunicación.
* Optimizar el consumo energético de los dispositivos.
* Utilizar protocolos más avanzados como MQTT en futuras versiones.
* Añadir interfaz gráfica para monitoreo en tiempo real.
* Probar previamente la conectividad antes de integrar todo el sistema.

14. Anexos


