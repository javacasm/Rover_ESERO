# Proyecto STEAM: Rover Marciano


![[proyecto_rover_steam.png]]
## Motivación

Un proyecto STEAM (Ciencia, Tecnología, Ingeniería, Arte y Matemáticas) sobre un Rover marciano fomenta el aprendizaje interdisciplinario al simular una misión espacial real. Este proyecto inspira a los estudiantes a explorar conceptos de ingeniería, programación, física y trabajo en equipo, mientras desarrollan creatividad al diseñar un rover que podría explorar Marte. Los objetivos de aprendizaje incluyen:

- **Ciencia**: Comprender las condiciones de Marte (gravedad, terreno, atmósfera) y cómo afectan el diseño del rover.
- **Tecnología**: Programar el rover para realizar tareas específicas, como moverse o recolectar datos.
- **Ingeniería**: Diseñar y construir un prototipo funcional que resista terrenos irregulares.
- **Arte**: Crear un diseño visualmente atractivo y funcional, con posibles elementos narrativos o de presentación.
- **Matemáticas**: Calcular trayectorias, distancias, o consumo energético del rover.

El proyecto también motiva a los estudiantes a imaginar cómo la exploración espacial contribuye al avance científico, como el estudio de la geología marciana, la búsqueda de agua o la preparación para futuras misiones humanas.

## Características del Rover

El rover debe ser un modelo funcional a pequeña escala con las siguientes características clave:

1. **Movilidad**: Capacidad para moverse en un terreno simulado (arena, rocas pequeñas) usando ruedas o un sistema similar.
2. **Control**: Programable para moverse en direcciones específicas (adelante, atrás, giros) mediante un microcontrolador (ej., Arduino, Raspberry Pi).
3. **Sensores**: Incorporar al menos un sensor (ej., ultrasonido para evitar obstáculos, o sensor de luz para simular detección de condiciones ambientales).
4. **Estructura robusta**: Construido con materiales ligeros pero resistentes (plástico, madera balsa, o piezas impresas en 3D).
5. **Estética**: Diseño inspirado en rovers reales como Perseverance o Curiosity, con elementos creativos que reflejen la identidad del equipo.
6. **Energía**: Alimentado por batería recargable o paneles solares simulados (LEDs para demostración).
7. **Funcionalidad adicional**: Opcional, como un brazo robótico para recolectar muestras o una cámara para simular captura de imágenes.

## Fases del Proyecto

### Fase 1: Investigación y Planificación (1-2 semanas)

- **Objetivo**: Comprender el contexto científico y técnico del proyecto.
- **Actividades**:
    - Investigar rovers reales (ej., Curiosity, Perseverance) y sus misiones en Marte.
    - Analizar las condiciones de Marte: gravedad (3.71 m/s²), terreno rocoso, temperaturas extremas.
    - Definir las funciones del rover (ej., explorar, evitar obstáculos, recolectar datos).
    - Formar equipos y asignar roles: ingeniero, programador, diseñador, científico.
- **Entregable**: Informe breve con objetivos del rover y un esquema del diseño inicial.

### Fase 2: Diseño (1-2 semanas)

- **Objetivo**: Crear un plano detallado del rover.
- **Actividades**:
    - Diseñar la estructura del rover (bocetos en papel o software CAD como Tinkercad).
    - Elegir materiales (ej., piezas LEGO, cartón, componentes electrónicos).
    - Seleccionar un microcontrolador y sensores (ej., Arduino con sensor ultrasónico HC-SR04).
    - Planificar el sistema de energía (baterías o paneles solares simulados).
    - Diseñar la estética del rover (colores, formas, inspiración en Marte).
- **Entregable**: Plano detallado del rover (dibujo o modelo 3D) y lista de materiales.

### Fase 3: Construcción (2-3 semanas)

- **Objetivo**: Construir un prototipo funcional.
- **Actividades**:
    - Ensamblar el chasis y las ruedas (usar kits de robótica o materiales reciclados).
    - Instalar el microcontrolador y conectar sensores/motores.
    - Probar conexiones eléctricas y asegurar estabilidad estructural.
    - Incorporar elementos artísticos (pintura, decoraciones).
- **Entregable**: Prototipo físico del rover.

### Fase 4: Programación (1-2 semanas)

- **Objetivo**: Programar el rover para realizar tareas básicas.
- **Actividades**:
    - Escribir código para controlar el movimiento (ej., avanzar, girar, detenerse).
    - Programar sensores (ej., evitar obstáculos con sensor ultrasónico).
    - Probar el rover en un terreno simulado (caja con arena y rocas).
    - Ajustar el código según los resultados de las pruebas.
- **Ejemplo de código (Arduino)**:
- 
```arduino
#define TRIG_PIN 9 
#define ECHO_PIN 10 
#define MOTOR_LEFT 5 
#define MOTOR_RIGHT 6

void setup() {  
	pinMode(TRIG_PIN, OUTPUT);  
	pinMode(ECHO_PIN, INPUT);  
	pinMode(MOTOR_LEFT, OUTPUT);  
	pinMode(MOTOR_RIGHT, OUTPUT);  
	Serial.begin(9600);  
}

void loop() {  
	long duration, distance;  
	digitalWrite(TRIG_PIN, LOW);  
	delayMicroseconds(2);  
	digitalWrite(TRIG_PIN, HIGH);  
	delayMicroseconds(10);  
	digitalWrite(TRIG_PIN, LOW);
	
	duration = pulseIn(ECHO_PIN, HIGH);  
	distance = duration * 0.034 / 2;
	
	if (distance < 20) {  
		digitalWrite(MOTOR_LEFT, LOW);  
		digitalWrite(MOTOR_RIGHT, LOW);  
	} else {  
		digitalWrite(MOTOR_LEFT, HIGH);  
		digitalWrite(MOTOR_RIGHT, HIGH);  
	}  
delay(100);  
}
```



# Proyecto STEAM: Rover Marciano

## Motivación
Un proyecto STEAM (Ciencia, Tecnología, Ingeniería, Arte y Matemáticas) sobre un Rover marciano fomenta el aprendizaje interdisciplinario al simular una misión espacial real. Este proyecto inspira a los estudiantes a explorar conceptos de ingeniería, programación, física y trabajo en equipo, mientras desarrollan creatividad al diseñar un rover que podría explorar Marte. Los objetivos de aprendizaje incluyen:

- **Ciencia**: Comprender las condiciones de Marte (gravedad, terreno, atmósfera) y cómo afectan el diseño del rover.
- **Tecnología**: Programar el rover para realizar tareas específicas, como moverse o recolectar datos.
- **Ingeniería**: Diseñar y construir un prototipo funcional que resista terrenos irregulares.
- **Arte**: Crear un diseño visualmente atractivo y funcional, con posibles elementos narrativos o de presentación.
- **Matemáticas**: Calcular trayectorias, distancias, o consumo energético del rover.

El proyecto también motiva a los estudiantes a imaginar cómo la exploración espacial contribuye al avance científico, como el estudio de la geología marciana, la búsqueda de agua o la preparación para futuras misiones humanas.

## Características del Rover
El rover debe ser un modelo funcional a pequeña escala con las siguientes características clave:
1. **Movilidad**: Capacidad para moverse en un terreno simulado (arena, rocas pequeñas) usando ruedas o un sistema similar.
2. **Control**: Programable para moverse en direcciones específicas (adelante, atrás, giros) mediante un microcontrolador (ej., Arduino, Raspberry Pi).
3. **Sensores**: Incorporar al menos un sensor (ej., ultrasonido para evitar obstáculos, o sensor de luz para simular detección de condiciones ambientales).
4. **Estructura robusta**: Construido con materiales ligeros pero resistentes (plástico, madera balsa, o piezas impresas en 3D).
5. **Estética**: Diseño inspirado en rovers reales como Perseverance o Curiosity, con elementos creativos que reflejen la identidad del equipo.
6. **Energía**: Alimentado por batería recargable o paneles solares simulados (LEDs para demostración).
7. **Funcionalidad adicional**: Opcional, como un brazo robótico para recolectar muestras o una cámara para simular captura de imágenes.

## Fases del Proyecto

### Fase 1: Investigación y Planificación (1-2 semanas)
- **Objetivo**: Comprender el contexto científico y técnico del proyecto.
- **Actividades**:
  - Investigar rovers reales (ej., Curiosity, Perseverance) y sus misiones en Marte.
  - Analizar las condiciones de Marte: gravedad (3.71 m/s²), terreno rocoso, temperaturas extremas.
  - Definir las funciones del rover (ej., explorar, evitar obstáculos, recolectar datos).
  - Formar equipos y asignar roles: ingeniero, programador, diseñador, científico.
- **Entregable**: Informe breve con objetivos del rover y un esquema del diseño inicial.

### Fase 2: Diseño (1-2 semanas)
- **Objetivo**: Crear un plano detallado del rover.
- **Actividades**:
  - Diseñar la estructura del rover (bocetos en papel o software CAD como Tinkercad).
  - Elegir materiales (ej., piezas LEGO, cartón, componentes electrónicos).
  - Seleccionar un microcontrolador y sensores (ej., Arduino con sensor ultrasónico HC-SR04).
  - Planificar el sistema de energía (baterías o paneles solares simulados).
  - Diseñar la estética del rover (colores, formas, inspiración en Marte).
- **Entregable**: Plano detallado del rover (dibujo o modelo 3D) y lista de materiales.

### Fase 3: Construcción (2-3 semanas)
- **Objetivo**: Construir un prototipo funcional.
- **Actividades**:
  - Ensamblar el chasis y las ruedas (usar kits de robótica o materiales reciclados).
  - Instalar el microcontrolador y conectar sensores/motores.
  - Probar conexiones eléctricas y asegurar estabilidad estructural.
  - Incorporar elementos artísticos (pintura, decoraciones).
- **Entregable**: Prototipo físico del rover.

### Fase 4: Programación (1-2 semanas)
- **Objetivo**: Programar el rover para realizar tareas básicas.
- **Actividades**:
  - Escribir código para controlar el movimiento (ej., avanzar, girar, detenerse).
  - Programar sensores (ej., evitar obstáculos con sensor ultrasónico).
  - Probar el rover en un terreno simulado (caja con arena y rocas).
  - Ajustar el código según los resultados de las pruebas.
- **Ejemplo de código (Arduino)**:

```C++
#define TRIG_PIN 9
#define ECHO_PIN 10
#define MOTOR_LEFT 5
#define MOTOR_RIGHT 6

void setup() {
  pinMode(TRIG_PIN, OUTPUT);
  pinMode(ECHO_PIN, INPUT);
  pinMode(MOTOR_LEFT, OUTPUT);
  pinMode(MOTOR_RIGHT, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  long duration, distance;
  digitalWrite(TRIG_PIN, LOW);
  delayMicroseconds(2);
  digitalWrite(TRIG_PIN, HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIG_PIN, LOW);
  
  duration = pulseIn(ECHO_PIN, HIGH);
  distance = duration * 0.034 / 2;
  
  if (distance < 20) {
    digitalWrite(MOTOR_LEFT, LOW);
    digitalWrite(MOTOR_RIGHT, LOW);
  } else {
    digitalWrite(MOTOR_LEFT, HIGH);
    digitalWrite(MOTOR_RIGHT, HIGH);
  }
  delay(100);
}
```

- **Entregable**: Código funcional y pruebas iniciales del rover.

### Fase 5: Pruebas y Optimización (1-2 semanas)
- **Objetivo**: Asegurar que el rover funcione en un entorno simulado.
- **Actividades**:
  - Crear un terreno de prueba que simule Marte (arena, rocas, pendientes).
  - Probar el rover en diferentes escenarios (movilidad, detección de obstáculos).
  - Ajustar el diseño o código según fallos detectados.
  - Documentar los resultados (éxitos, problemas, soluciones).
- **Entregable**: Informe de pruebas con video o fotos del rover en acción.

### Fase 6: Presentación y Reflexión (1 semana)
- **Objetivo**: Compartir el proyecto y reflexionar sobre el aprendizaje.
- **Actividades**:
  - Preparar una presentación (diapositivas, video, o demostración en vivo).
  - Explicar el diseño, las funciones del rover y los retos superados.
  - Reflexionar sobre los aprendizajes en ciencia, tecnología, ingeniería, arte y matemáticas.
  - Responder preguntas de una audiencia (compañeros, profesores, o jueces).
- **Entregable**: Presentación final y reflexión escrita grupal.

## Cómo Realizar el Proyecto
1. **Materiales sugeridos**:
   - Microcontrolador: Arduino Uno o Raspberry Pi.
   - Sensores: Ultrasónico (HC-SR04), infrarrojos, o de luz.
   - Motores: Motores DC con driver (L298N).
   - Chasis: Kits de robótica, LEGO, o materiales reciclados.
   - Software: Arduino IDE, Python (para Raspberry Pi), o Scratch (para principiantes).
   - Otros: Baterías, cables, herramientas (destornilladores, soldador).
2. **Espacio de trabajo**: Aula o laboratorio con acceso a herramientas y computadoras.
3. **Tiempo estimado**: 7-12 semanas, dependiendo de la profundidad del proyecto.
4. **Evaluación**:
   - Funcionalidad del rover (movilidad, sensores, robustez).
   - Creatividad en el diseño y presentación.
   - Colaboración en equipo y documentación del proceso.
   - Reflexión sobre aprendizajes STEAM.

## Beneficios Educativos
- **Habilidades técnicas**: Programación, diseño mecánico, uso de sensores.
- **Resolución de problemas**: Identificar y solucionar fallos en el diseño o código.
- **Trabajo en equipo**: Coordinación entre roles (ingeniero, programador, diseñador).
- **Conexión con el mundo real**: Entender la importancia de la exploración espacial y su impacto en la ciencia.

Este proyecto no solo enseña conceptos STEAM, sino que también despierta curiosidad por la exploración espacial y prepara a los estudiantes para desafíos tecnológicos del futuro.

