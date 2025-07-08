# Curso: Programando un Rover en Marte con Micro:bit y Cutebot

Este curso está diseñado para enseñar a estudiantes (nivel principiante a intermedio) los fundamentos de robótica y programación utilizando la placa **Micro:bit** y el robot **Cutebot** de ELECFREAKS, con una temática centrada en una misión de un rover en Marte. El curso cubre desde los conceptos básicos hasta un proyecto final donde se controla remotamente el rover y se reciben datos de telemetría en otra Micro:bit. Se abordan conceptos clave como autonomía, telemetría, sensores y control remoto, simulando una misión real en Marte.

---

## **Objetivos del curso**
1. Comprender los fundamentos de la placa Micro:bit y el robot Cutebot.
2. Aprender a programar movimientos, sensores y comunicación inalámbrica con MakeCode.
3. Diseñar un rover autónomo que simule una misión en Marte, incluyendo:
   - **Autonomía**: capacidad de navegar y evitar obstáculos.
   - **Telemetría**: recolección y transmisión de datos de sensores.
   - **Control remoto**: manejo del rover desde otra Micro:bit.
4. Desarrollar un proyecto final que integre todos los conceptos en un sistema funcional.

---

## **Requisitos previos**
- 2 placas Micro:bit (una para el rover y otra para el control remoto).
- Robot Cutebot (o Cutebot Pro para mayor precisión).
- Batería de litio recargable para Cutebot (o 3 pilas AAA).
- Computadora con acceso a [MakeCode](https://makecode.microbit.org/).
- Conexión USB para programar las Micro:bit.
- (Opcional) Accesorios como joystick:bit o cámara de IA para ampliaciones.

---

## **Estructura del curso**
El curso está dividido en **6 módulos**, diseñados para ser completados en sesiones de 1-2 horas cada una, dependiendo del nivel de los estudiantes. Cada módulo incluye teoría, práctica y un pequeño desafío.

### **Módulo 1: Introducción a Micro:bit y Cutebot**
**Objetivo**: Familiarizarse con la placa Micro:bit, el robot Cutebot y el entorno de programación MakeCode.

**Contenido**:
- **Micro:bit**: 
  - Componentes: matriz de LEDs 5x5, pulsadores A y B, acelerómetro, magnetómetro, sensor de luz, sensor de temperatura, Bluetooth, y (en V2) micrófono y altavoz.
  - Programación en MakeCode: bloques, JavaScript o Python.
- **Cutebot**:
  - Sensores: ultrasónico (distancia), seguimiento de líneas (2 o 4 IR en Pro), receptor IR, LEDs RGB, zumbador.
  - Actuadores: dos motores de alta velocidad (300 RPM, con encoders en Cutebot Pro).
  - Conexión con Micro:bit y alimentación.
- **Entorno MakeCode**:
  - Instalación de la extensión Cutebot: en MakeCode, ir a "Extensiones", buscar "Cutebot" y añadirla.
  - Primer programa: encender los LEDs RGB del Cutebot en rojo.

**Práctica**:
1. Conectar la Micro:bit al Cutebot.
2. Programar un bloque para que los LEDs RGB parpadeen en diferentes colores al presionar el botón A.
3. Mostrar un ícono de Marte (planeta) en la matriz de LEDs de la Micro:bit.

**Desafío**: Hacer que el zumbador emita un sonido al presionar el botón B, simulando una alerta de misión.

---

### **Módulo 2: Movimiento y control básico del Rover**
**Objetivo**: Programar movimientos básicos del Cutebot para simular un rover en Marte.

**Contenido**:
- **Motores del Cutebot**:
  - Bloques de MakeCode: "avanzar", "retroceder", "girar izquierda/derecha", "detener".
  - Control de velocidad (0-100%) y tiempo de movimiento.
- **Programación básica**:
  - Mover el rover hacia adelante durante 2 segundos a 50% de velocidad.
  - Girar 90° a la izquierda o derecha (usar encoders en Cutebot Pro para mayor precisión).
- **Conceptos de autonomía**:
  - Introducción a la navegación autónoma: ejecutar movimientos sin intervención humana.
  - Ejemplo: avanzar 40 cm y detenerse.

**Práctica**:
1. Programar el rover para avanzar 5 segundos, girar a la derecha y detenerse.
2. Ajustar la velocidad para simular un terreno marciano irregular (velocidad baja, 30-40%).
3. Usar la matriz de LEDs para mostrar una flecha indicando la dirección del movimiento.

**Desafío**: Crear un programa que haga que el rover trace un cuadrado (avanzar y girar 90° cuatro veces).

---

### **Módulo 3: Sensores para exploración en Marte**
**Objetivo**: Utilizar los sensores del Cutebot y la Micro:bit para recolectar datos del entorno marciano.

**Contenido**:
- **Sensores disponibles**:
  - **Sensor ultrasónico**: mide distancias (2-400 cm, precisión ±1.5 mm). Útil para detectar cráteres o rocas.
  - **Sensores de seguimiento de líneas (IR)**: detectar caminos predefinidos o bordes (simular senderos en Marte).
  - **Sensores de la Micro:bit**: acelerómetro (detectar inclinaciones del terreno), magnetómetro (orientación), sensor de luz (simular detección de luz solar), sensor de temperatura (clima marciano).
- **Programación de sensores**:
  - Leer la distancia con el sensor ultrasónico y mostrarla en la matriz de LEDs.
  - Usar sensores de línea para seguir un camino marcado.
- **Autonomía básica**:
  - Programar el rover para detenerse si detecta un obstáculo a menos de 10 cm.

**Práctica**:
1. Programar el rover para avanzar y detenerse si detecta un obstáculo a menos de 15 cm.
2. Mostrar la distancia medida en la matriz de LEDs (número o ícono).
3. Usar el sensor de seguimiento de líneas para que el rover siga una línea negra en un fondo blanco.

**Desafío**: Hacer que el rover evite un obstáculo girando a la derecha cuando detecte algo a menos de 10 cm y luego continúe avanzando.

---

### **Módulo 4: Comunicación inalámbrica y control remoto**
**Objetivo**: Configurar la comunicación por radio entre dos Micro:bit para controlar el rover remotamente.

**Contenido**:
- **Radio en Micro:bit**:
  - Configuración: establecer un grupo de radio (0-255) para conectar las placas.
  - Enviar y recibir cadenas de texto o números.
- **Control remoto**:
  - Usar una segunda Micro:bit como mando.
  - Asignar comandos: botón A (avanzar), B (girar derecha), A+B (girar izquierda).
- **Simulación de control marciano**:
  - Enviar comandos desde la "base en la Tierra" (segunda Micro:bit) al rover.
  - Mostrar confirmación de comandos en la matriz de LEDs del rover.

**Práctica**:
1. Configurar ambas Micro:bit en el mismo grupo de radio (ej., grupo 42).
2. Programar la Micro:bit del control para enviar:
   - "Av" al presionar A (avanzar 500 ms).
   - "Iz" al presionar A+B (girar izquierda 250 ms).
   - "De" al presionar B (girar derecha 250 ms).
3. Programar el rover para recibir y ejecutar los comandos, mostrando un ícono de check en la matriz de LEDs al recibirlos.

**Desafío**: Usar el acelerómetro de la Micro:bit del control para mover el rover inclinando el mando (inclinación adelante = avanzar, izquierda/derecha = girar).

---

### **Módulo 5: Telemetría y recolección de datos**
**Objetivo**: Implementar la recolección y transmisión de datos de sensores (telemetría) al control remoto.

**Contenido**:
- **Telemetría en misiones espaciales**:
  - Definición: envío de datos del entorno (distancia, temperatura, orientación) a una base de control.
  - Importancia en Marte: monitorear el terreno, clima y estado del rover.
- **Programación de telemetría**:
  - Enviar datos del sensor ultrasónico (distancia a obstáculos) y del sensor de temperatura al control remoto.
  - Mostrar los datos recibidos en la Micro:bit del control (matriz de LEDs o consola en MakeCode).
- **Autonomía avanzada**:
  - Combinar navegación autónoma con telemetría: el rover envía datos mientras evita obstáculos.

**Práctica**:
1. Programar el rover para enviar la distancia medida por el sensor ultrasónico cada vez que recibe un comando de movimiento.
2. Si la distancia es menor o igual a 10 cm, enviar un número (ej., distancia en cm) al control remoto.
3. En la Micro:bit del control, mostrar la distancia recibida en la matriz de LEDs o en la consola de MakeCode.

**Desafío**: Añadir el envío de datos de temperatura (de la Micro:bit) cada 5 segundos, simulando el monitoreo del clima marciano.

---

### **Módulo 6: Proyecto final - Rover Autónomo en Marte**
**Objetivo**: Integrar todos los conceptos en un proyecto funcional: un rover que navega autónomamente, evita obstáculos, recibe comandos remotos y envía telemetría.

**Descripción del proyecto**:
- **Escenario**: El Cutebot es un rover en Marte, explorando un terreno con cráteres y rocas. Una Micro:bit actúa como base de control en la "Tierra".
- **Funcionalidades**:
  1. **Autonomía**: El rover avanza y evita obstáculos (detenerse o girar si detecta algo a menos de 10 cm).
  2. **Control remoto**: La base de control envía comandos (avanzar, girar izquierda/derecha) usando botones o inclinación.
  3. **Telemetría**: El rover envía datos de distancia (sensor ultrasónico) y temperatura cada 5 segundos.
  4. **Visualización**: La base de control muestra los datos recibidos en la matriz de LEDs y (opcionalmente) en la consola de MakeCode.
- **Interfaz**: Mostrar un logotipo de la misión (Tierra y Marte) en la Micro:bit del rover al iniciar.

**Pasos**:
1. **Configuración inicial**:
   - Configurar ambas Micro:bit en el mismo grupo de radio.
   - Mostrar el logotipo de la misión en el rover al encenderse.
2. **Programación del rover**:
   - Avanzar a 40% de velocidad por defecto.
   - Detenerse y girar a la derecha si detecta un obstáculo a menos de 10 cm.
   - Recibir comandos remotos ("Av", "Iz", "De") y ejecutarlos.
   - Enviar datos de distancia y temperatura cada 5 segundos.
3. **Programación del control remoto**:
   - Enviar comandos con botones A, B, A+B.
   - Mostrar datos de telemetría recibidos (distancia y temperatura).
4. **Pruebas**:
   - Simular un terreno marciano con obstáculos (cajas, objetos pequeños).
   - Verificar que el rover evita obstáculos y responde a comandos.
   - Confirmar que los datos de telemetría llegan correctamente.

**Código de ejemplo (MakeCode)**:
- **Rover (Micro:bit 1)**:
  ```javascript
  radio.setGroup(42)
  basic.showIcon(IconNames.Chessboard) // Logotipo de misión
  basic.forever(function () {
      let distance = cutebot.ultrasonic(cutebot.SonarUnit.Centimeters)
      if (distance <= 10) {
          cutebot.stop()
          cutebot.motors(0, 40) // Girar derecha
          basic.pause(500)
      } else {
          cutebot.motors(40, 40) // Avanzar
      }
      radio.sendNumber(distance)
      radio.sendValue("temp", input.temperature())
      basic.pause(5000)
  })
  radio.onReceivedString(function (command) {
      if (command == "Av") {
          cutebot.motors(40, 40)
          basic.pause(500)
      } else if (command == "Iz") {
          cutebot.motors(-40, 40)
          basic.pause(250)
      } else if (command == "De") {
          cutebot.motors(40, -40)
          basic.pause(250)
      }
      cutebot.stop()
      basic.showIcon(IconNames.Yes)
  })
  ```
- **Control remoto (Micro:bit 2)**:
  ```javascript
  radio.setGroup(42)
  input.onButtonPressed(Button.A, function () {
      radio.sendString("Av")
  })
  input.onButtonPressed(Button.B, function () {
      radio.sendString("De")
  })
  input.onButtonPressed(Button.AB, function () {
      radio.sendString("Iz")
  })
  radio.onReceivedNumber(function (value) {
      basic.showNumber(value)
  })
  radio.onReceivedValue(function (name, value) {
      if (name == "temp") {
          serial.writeLine("Temp: " + value)
      }
  })
  ```

**Desafío final**: Añadir una funcionalidad extra, como usar el sensor de luz para detectar "tormentas de polvo" (baja luz) y enviar una alerta al control remoto.

---

## **Evaluación**
- **Participación**: Compleción de las prácticas y desafíos de cada módulo.
- **Proyecto final**:
  - Funcionalidad: ¿El rover evita obstáculos, responde a comandos y envía telemetría?
  - Creatividad: Uso de LEDs, zumbador o sensores adicionales para mejorar la experiencia.
  - Documentación: Breve informe (o presentación) explicando el diseño del rover y los datos recolectados.
- **Opcional**: Competencia entre equipos para navegar un circuito marciano con obstáculos.

---

## **Recursos adicionales**
- **Manuales**:
  - Manual de Programación Cutebot (incluido en algunos kits, en español e inglés).[](https://robotopia.es/kits-educativos/196-23-cutebot.html)[](https://xplora360.es/producto/cutebot-para-microbit/)
  - Tutoriales de MakeCode: [makecode.microbit.org](https://makecode.microbit.org/).
- **Videos**:
  - Unboxing y proyectos con Cutebot: [ELECFREAKS YouTube](https://www.youtube.com/@elecfreaks).
- **Extensiones**:
  - Añadir una cámara de IA para detectar señales o colores en el terreno marciano.[](https://createc3d.com/es/inicio/1435-smart-cutebot-robot-para-microbit-de-elecfreaks.html)
  - Usar joystick:bit para un control más intuitivo.[](https://robotopia.es/kits-educativos/196-23-cutebot.html)

---

## **Notas finales**
- El curso está diseñado para ser flexible, adaptándose a estudiantes de primaria (8+ años) o secundaria, ajustando la complejidad de la programación (bloques para principiantes, Python para avanzados).
- La temática de Marte motiva a los estudiantes al simular una misión real, integrando conceptos STEAM (ciencia, tecnología, ingeniería, arte y matemáticas).
- Para escuelas, se recomienda el "Pack Centros" de Cutebot para múltiples estudiantes.[](https://robotopia.es/kits-educativos/196-23-cutebot.html)
- Los datos de telemetría pueden exportarse a una hoja de cálculo para análisis avanzado, simulando una misión científica real.[](https://libros.catedu.es/books/talleres-de-robotica-y-pensamiento-computacional/page/microbit/export/html)

Este curso proporciona una base sólida en robótica y programación, con un enfoque práctico y motivador que simula una misión espacial realista. ¡Prepárate para explorar Marte con tu rover!