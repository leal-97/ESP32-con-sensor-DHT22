# ESP32-con-sensor-DHT22
## Práctica de Tarjeta ESP32 con sensor DHT22 para monitoreo de temperatura y humedad
En este repositorio muestraré como programar una tarjeta ESP32 utillizando un sensor DHT22 para monitorear humedad y temperatura del entorno.
## ESP32
Es un microcontrolador revolucionario que se ha vuelto esencial en la tecnología moderna. Es un sistema en chip (SoC) de bajo costo y bajo consumo de energía con una combinación de capacidades Wi-Fi y Bluetooth. 

1.	**30 Pines de E/S:** Ofrece una amplia variedad de pines para la conexión de sensores, actuadores y otros dispositivos.
2.	**Alimentación:** Puede ser alimentado a través de un puerto MicroUSB o mediante otros métodos de suministro de energía.
3.	**Wi-Fi y Bluetooth Integrados:** Facilita la conectividad inalámbrica para la comunicación y el control remoto.
4.	**Capacidades de Programación:** Se puede programar utilizando el entorno de desarrollo de Arduino o herramientas específicas de Espressif.
Aplicaciones Comunes:
1.	**Proyectos de IoT (Internet de las Cosas):** Ideal para dispositivos conectados a la red que requieren comunicación inalámbrica.
2.	**Sistemas Embebidos:** Puede ser utilizado en sistemas embebidos para controlar y monitorear dispositivos.
3.	**Desarrollo de Prototipos:** Ampliamente utilizado en el desarrollo de prototipos debido a su facilidad de programación y su capacidad de conexión a una variedad de dispositivos.

## Sensor DHT22
El DHT22 es un sensor digital de humedad y temperatura que ofrece mediciones precisas y de alta calidad. Está compuesto por un pequeño circuito integrado y un sensor capacitivo de humedad y temperatura. 
Es ampliamente utilizado en aplicaciones que requieren un monitoreo preciso del entorno.
Características Principales:
-	**Medición de Humedad y Temperatura:** Proporciona mediciones digitales de humedad relativa y temperatura ambiente.
- **Bajo Consumo de Energía:** Opera con un bajo consumo de energía, lo que lo hace adecuado para aplicaciones con restricciones de energía.
- **Tiempo de Respuesta Rápido:** Proporciona mediciones actualizadas en intervalos cortos de tiempo.

 Aplicaciones Comunes:

- Sistemas de monitoreo de clima interior y exterior.
- Proyectos de automatización del hogar.
- Dispositivos de control ambiental y climatización.

## Material
- https://wokwi.com/
- ESP32
- DHT22

## Instrucciones:
- **1.- Entrar al siguiente enlace:** https://wokwi.com/
- **2-. Seleccionar la tarjeta ESP32**

![]( https://github.com/leal-97/ESP32-con-sensor-DHT22/blob/main/esp32kd.jpeg )
  
- **3.- Bajar el cursor hasta starter templates y seleccionar ESP32 una vez más**

![]( https://github.com/leal-97/ESP32-con-sensor-DHT22/blob/main/starter.jpeg )


- **4.- En el cuadro de programación borrar el código default y pegar este:**

```
 #include "DHTesp.h"

const int DHT_PIN = 15; // Pin de conexión del sensor
DHTesp dhtSensor; // Instancia del sensor

void setup() {

  Serial.begin(115200); // Inicialización del puerto serie
  dhtSensor.setup(DHT_PIN, DHTesp::DHT22); // Configura el sensor DHT22 en el pin especificado
}

void loop() {
  
  TempAndHumidity data = dhtSensor.getTempAndHumidity(); // Obtiene datos de temperatura y humedad
  Serial.println("Temp: " + String(data.temperature, 1) + "°C"); // Muestra la temperatura
  Serial.println("Humidity: " + String(data.humidity, 1) + "%"); // Muestra la humedad
  Serial.println("---"); // Separador de lecturas
  delay(1000); // Espera 1 segundo antes de tomar otra lectura
}

```

- **5.- En la sección de library manager buscar las siguientes librerías y agregarlas:**
- LiquidCristal IC2
- DHT sensor library for ESPx

![]( https://github.com/leal-97/ESP32-con-sensor-DHT22/blob/main/libreria.jpeg )


- 6.- Seleccionar el sensor en la parte de Simulacion con el botón **+** y buscar **DHT22**, **LCDI2C**. Agregar y conectar de la siguiente manera.

![]( https://github.com/leal-97/ESP32-con-sensor-DHT22/blob/main/conexion.jpeg )


## Instrucción de operación:
- Correr el simulador
- Manipular los valores del sensor para observar los resultados de la medición arrojados

## Resultados

![]( https://github.com/leal-97/ESP32-con-sensor-DHT22/blob/main/resultado.jpeg )

## Referencias

- ESP32 30 Pines. (s.f.). Transtronix. https://transtronix.com.mx/productos/esp32-30-pines/?srsltid=AfmBOoo9Q1Vc1XVCLC0ZsFSZCIyZ97hdDYoH6Qf2gwDvs2M-5pUDvXv5
- Sensor de humedad y temperatura DHT22. (s.f.). Transtronix. https://transtronix.com.mx/productos/sensor-de-humedad-y-temperatura-dht22/?srsltid=AfmBOoo2GcDGu0hr44E75_ZvkYeEb_3f_b8i974KTgGTsq6kfgWZMjGH

## Créditos
Desarrollado por: **Ing. Mecánico Eduardo Leal**

- https://github.com/leal-97
