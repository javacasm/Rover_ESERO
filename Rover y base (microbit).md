
# Proyecto STEAM: Rover Marciano con Micro:bit y Cutebot usando MicroPython

![[Rover_marciano_steampunk.png]]
## Motivación

Este proyecto STEAM simula una misión marciana con un rover basado en el ELECFREAKS Cutebot, controlado por un micro:bit, y una base de control con otro micro:bit, ambos comunicándose vía radio. La integración de dos micro:bits permite emular un sistema real de exploración espacial, donde el rover recolecta y envía datos (telemetría) y la base los visualiza y envía comandos. Este enfoque fomenta habilidades interdisciplinarias:

- **Ciencia**: Analizar datos como temperatura, orientación y luminosidad para simular estudios marcianos.
- **Tecnología**: Programar en MicroPython para gestionar comunicación y control.
- **Ingeniería**: Configurar el Cutebot para operar en un entorno simulado.
- **Arte**: Diseñar una estética inspirada en rovers reales, con visualización creativa de datos en la base.
- **Matemáticas**: Procesar datos de sensores (ej., calibrar brújula, calcular distancias).

El proyecto motiva a los estudiantes a explorar la exploración espacial, comprendiendo cómo los rovers reales transmiten datos a la Tierra y reciben comandos, mientras desarrollan habilidades de programación y trabajo en equipo.

## Explicación

El sistema consta de dos componentes:

1. **Rover (Cutebot + micro:bit)**: Equipado con sensores para recolectar datos (temperatura, orientación, luminosidad, distancia) y enviarlos a la base vía radio. Responde a comandos de movimiento (adelante, atrás, giros).
2. **Base (micro:bit)**: Recibe datos del rover, los muestra en su pantalla LED 5x5, y envía comandos de movimiento mediante botones o gestos (inclinación).

- **Comunicación**: Los micro:bits usan el módulo de radio integrado (2.4 GHz) para intercambio bidireccional de datos.
- **Telemetría**:
    - **Temperatura**: Sensor integrado del micro:bit.
    - **Intensidad de señal**: Valor RSSI de la señal de radio.
    - **Orientación**: Brújula integrada para dirección (grados).
    - **Luminosidad**: Sensor de luz del micro:bit.
    - **Distancia**: Sensor ultrasónico del Cutebot para detectar obstáculos.
- **Control**: La base envía comandos ("F" para adelante, "B" para atrás, "L" para izquierda, "R" para derecha, "S" para detenerse) usando botones A/B o inclinación.
- **Visualización**: La base muestra datos en la pantalla LED, alternando entre temperatura, orientación, luminosidad, distancia y RSSI.


## Componentes Necesarios

- **Rover**:
    - ELECFREAKS Cutebot (incluye sensor ultrasónico y de línea).
    - BBC micro:bit V2 (recomendado por sensor de temperatura más preciso).
    - 3 baterías AAA o batería de litio (Cutebot Pro).
    - Cable USB para programar.
- **Base**:
    - BBC micro:bit V2.
    - Cable USB para programar.
- **Otros**:
    - Computadora con editor MicroPython (ej., Mu Editor o Thonny).
    - Materiales para terreno simulado (arena, rocas, cinta negra).
    - Opcional: LEGO o adhesivos para decorar el rover.
- **Software**:
    - [Thonny](https://thonny.org) para MicroPython.
    - Biblioteca Cutebot para MicroPython ([https://github.com/elecfreaks/pxt-cutebot](https://github.com/elecfreaks/pxt-cutebot)).

## Código

### Código del Rover (Cutebot + micro:bit)

```python
from microbit import * import radio import cutebot

# Configurar radio
radio.on()  
radio.config(group=1, power=7)

cutebot = cutebot.Cutebot()

# Función para obtener datos de sensores
def get_telemetry():  
	temp = temperature()  
	light = display.read_light_level()  
	compass = compass.heading()  
	distance = cutebot.get_distance()  
	return {"temp": temp, "light": light, "compass": compass, "distance": distance}

# Función para ejecutar comandos de movimiento
def move_rover(command):  
	if command == "F":  
		cutebot.motors(50, 50) # Adelante  
	elif command == "B":  
		cutebot.motors(-50, -50) # Atrás  
	elif command == "L":  
		cutebot.motors(-50, 50) # Izquierda  
	elif command == "R":  
		cutebot.motors(50, -50) # Derecha  
	elif command == "S":  
		cutebot.motors(0, 0) # Detener

# Bucle principal

while True:  
	# Enviar telemetría  
	telemetry = get_telemetry()  
	rssi = radio.get_rssi()  
	telemetry["rssi"] = rssi  
	radio.send(str(telemetry)) # Enviar datos como cadena

# Recibir comandos
	incoming = radio.receive()
	if incoming:
	    move_rover(incoming)

	# Mostrar estado en LEDs (opcional)
	if telemetry["distance"] < 20:
	    display.show(Image.NO)  # Obstáculo cercano
	else:
	    display.show(Image.YES)

	sleep(500)  # Actualizar cada 0.5 segundos
```


### Código de la Base (micro:bit)

```python
from microbit import *
import radio

# Configurar radio
radio.on()
radio.config(group=1, power=7)

# Variables para alternar datos mostrados
current_display = 0
last_button_press = running_time()

def display_data(data):
    global current_display
    if current_display == 0:
        display.scroll("T:" + str(data["temp"]) + "C")
    elif current_display == 1:
        display.scroll("L:" + str(data["light"]))
    elif current_display == 2:
        display.scroll("C:" + str(data["compass"]))
    elif current_display == 3:
        display.scroll("D:" + str(data["distance"]) + "cm")
    elif current_display == 4:
        display.scroll("R:" + str(data["rssi"]) + "dBm")

# Bucle principal
while True:
    # Recibir telemetría
    incoming = radio.receive()
    if incoming:
        try:
            data = eval(incoming)  # Convertir cadena a diccionario
            display_data(data)
        except:
            display.scroll("Error")

    # Cambiar dato mostrado con botón A
    if button_a.was_pressed() and running_time() - last_button_press > 500:
        current_display = (current_display + 1) % 5
        last_button_press = running_time()

    # Enviar comandos con botones o inclinación
    if button_b.is_pressed():
        radio.send("F")  # Adelante
    elif accelerometer.get_y() > 500:
        radio.send("B")  # Atrás
    elif accelerometer.get_x() < -500:
        radio.send("L")  # Izquierda
    elif accelerometer.get_x() > 500:
        radio.send("R")  # Derecha
    else:
        radio.send("S")  # Detener
    
    sleep(200)  # Actualizar cada 0.2 segundos
```

### Notas sobre el Código
- **Rover**:
  - Usa la biblioteca `cutebot` para controlar motores y sensores.
  - Envía un diccionario con telemetría (temperatura, luz, brújula, distancia, RSSI) cada 0.5 segundos.
  - Ejecuta comandos recibidos ("F", "B", "L", "R", "S").
  - Muestra un ícono en la pantalla LED si detecta obstáculos cercanos (<20 cm).
- **Base**:
  - Recibe y parsea la telemetría como un diccionario.
  - Alterna entre mostrar temperatura, luz, orientación, distancia y RSSI con el botón A.
  - Usa el botón B para avanzar y el acelerómetro para otros movimientos.
  - Actualiza datos cada 0.2 segundos para una respuesta rápida.
- **Configuración**:
  - Descarga el firmware MicroPython para micro:bit: https://microbit.org/get-started/user-guide/micropython/.
  - Instala la biblioteca Cutebot en el editor (copiar archivos al micro:bit).
  - Asegúrate de que ambos micro:bits usen el mismo grupo de radio (`group=1`).

## Posibles Ampliaciones

1. **Brazo robótico**: Agregar un servo al Cutebot para simular recolección de muestras, controlado desde la base.
2. **Cámara simulada**: Usar LEDs RGB del Cutebot para indicar captura de imágenes, enviando un "estado" adicional a la base.
3. Cámara IA: detecta objetos predefinidos
4. **Rutas predefinidas**: Programar el Cutebot para seguir una línea (usando sensores de línea) de forma autónoma.
5. **Almacenamiento de datos**: Guardar telemetría en la base usando una tarjeta SD (con un módulo externo).
6. **Interfaz avanzada**: Conectar a la micro:bit base una pantalla para visualización de los datos.
7. **Terreno interactivo**: Crear un terreno con sensores (ej., presión) que el rover detecte y transmita.
8. **Sonidos marcianos**: Usar el buzzer del Cutebot para emitir sonidos basados en eventos (ej., detección de obstáculos).

## Implementación

- **Materiales**: Ver lista en "Componentes Necesarios".
- **Tiempo**: 6-8 semanas (investigación: 1 semana, configuración: 1 semana, programación: 2 semanas, pruebas: 1-2 semanas, presentación: 1 semana).
- **Terreno**: Caja con arena, rocas y cinta negra para simular Marte.
- **Evaluación**:
  - Funcionalidad: Comunicación bidireccional, precisión de telemetría, control de movimiento.
  - Creatividad: Diseño del rover y visualización en la base.
  - Documentación: Informe de pruebas y reflexión STEAM.
- **Beneficios**: Aprender MicroPython, comunicación inalámbrica, y conceptos de exploración espacial, con un sistema accesible y modular.

Este proyecto combina la simplicidad del Cutebot y micro:bit con la complejidad de un sistema de control remoto, ofreciendo una experiencia STEAM inmersiva y práctica.

