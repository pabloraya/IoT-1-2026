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
  <img width="500" height="230" alt="imagen" src="https://github.com/user-attachments/assets/7ceaa420-8194-4889-b212-1d310fca671c" />


* Diagrama de secuencia (protocolo)

  ![secuencia](https://github.com/user-attachments/assets/ca46cd73-afd9-453a-8491-833573089234)
  <img width="400" height="500" alt="imagen" src="https://github.com/user-attachments/assets/89e2394a-a22f-4805-8473-f4afae6156bd" />


* Diagrama de flujo del algoritmo

![flujo corregido](https://github.com/user-attachments/assets/ae36c73f-c166-4251-afe1-31d173fc4e45)
<img width="465" height="583" alt="imagen" src="https://github.com/user-attachments/assets/a922248a-4d8c-45dd-8c03-c6908e720a04" />



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
     
Con el propósito de identificar la causa de los problemas de conectividad en el sistema desarrollado, se llevaron a cabo una serie de pruebas controladas orientadas a evaluar el comportamiento del módulo ESP32 frente a diferentes configuraciones de red y parámetros de conexión. Estas pruebas incluyeron la verificación de conexión a redes institucionales, el uso de un hotspot móvil, la detección de redes disponibles, la validación de credenciales y el análisis de los estados de conexión. A través de este proceso se buscó aislar variables y determinar de manera precisa el origen de la falla en la comunicación WiFi.

Realizamos 6 pruebas en concreto que son:
Prueba 1: Conexión a red WiFi institucional
Prueba 2: Conexión a hotspot móvil (iPhone)
Prueba 3: Verificación de detección de redes WiFi
Prueba 4: Validación de credenciales
Prueba 5: Verificación de hardware y configuración
Prueba 6: Análisis del código de estado WiFi

A partir de las pruebas realizadas, no se obtuvieron resultados satisfactorios en cuanto a la conexión del ESP32 a la red WiFi, ya que en todos los escenarios evaluados la comunicación no logró establecerse correctamente. A pesar de haber verificado distintos factores como credenciales, tipo de red y configuración del dispositivo,como no se pudo realizar la coneccion a wifi satisfactoriamente, no se pudo realizar la validacion y funcionamiento correcto del prototipo.
 12. Resultados

 13. Conclusiones
El proyecto no pudo completarse debido a problemas de conexión del ESP32 con la red WiFi; sin embargo, se desarrolló correctamente la lógica del sistema y se identificaron factores clave que afectan la implementación de soluciones IoT en entornos reales.

14. Recomendaciones

* Implementar manejo de errores en la comunicación.
* Optimizar el consumo energético de los dispositivos.
* Utilizar protocolos más avanzados como MQTT en futuras versiones.
* Añadir interfaz gráfica para monitoreo en tiempo real.
* Probar previamente la conectividad antes de integrar todo el sistema.

14. Anexos
    Codigo Prueba de Wifi (Identificacion de redes)
<img width="629" height="408" alt="Captura de Pantalla 2026-04-08 a la(s) 17 35 23" src="https://github.com/user-attachments/assets/67954e12-7ba4-4889-a2a4-d18774cd597f" />

Codigo para validar coneccion a Wifi

#include <WiFi.h>

const char* ssid = "TU_WIFI";
const char* password = "TU_PASSWORD";

void setup() {
  Serial.begin(115200);

  WiFi.begin(ssid, password);

  Serial.print("Conectando a WiFi");

  int intentos = 0;

  while (WiFi.status() != WL_CONNECTED && intentos < 20) {
    delay(500);
    Serial.print(".");
    intentos++;
  }

  if (WiFi.status() == WL_CONNECTED) {
    Serial.println("\n✅ CONECTADO!");
    Serial.print("IP: ");
    Serial.println(WiFi.localIP());
  } else {
    Serial.println("\n❌ NO SE PUDO CONECTAR");
    Serial.print("Status: ");
    Serial.println(WiFi.status());
  }
}

void loop() {}

