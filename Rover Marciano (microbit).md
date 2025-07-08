# Proyecto STEAM: Rover Marciano con micro:bit y Cutebot/Maqueen

![[Rover_marciano_manga.png]]


## Motivación

Este proyecto STEAM utiliza un robot como Cutebot o Maqueen, controlado por un micro:bit, para simular un Rover marciano, inspirando a los estudiantes a explorar ciencia, tecnología, ingeniería, arte y matemáticas. El contexto de una misión en Marte motiva el aprendizaje práctico y fomenta habilidades como programación, diseño y trabajo en equipo. Los objetivos incluyen:

- **Ciencia**: Entender las condiciones de Marte (terreno, gravedad) y su impacto en el rover.
- **Tecnología**: Programar el micro:bit para controlar el robot en tareas como navegación o detección de obstáculos.
- **Ingeniería**: Personalizar el Cutebot/Maqueen para simular un rover marciano funcional.
- **Arte**: Diseñar una estética inspirada en rovers reales (ej., Perseverance) con elementos creativos.
- **Matemáticas**: Calcular distancias, ángulos de giro o consumo energético.

El proyecto conecta con la exploración espacial, enseñando cómo los rovers recopilan datos sobre Marte y preparan futuras misiones humanas.

## Características del Rover

Usaremos un robot preensamblado como el ELECFREAKS Cutebot o DFRobot Maqueen, compatibles con micro:bit, con estas características adaptadas:

1. **Movilidad**: Dos motores DC para movimiento (adelante, atrás, giros) en terrenos simulados (arena, rocas).
2. **Control**: Programado vía micro:bit con MakeCode (bloques o JavaScript) para tareas autónomas o control remoto.
3. **Sensores**:
    - Sensor ultrasónico (HC-SR04) para evitar obstáculos.
    - Sensores de seguimiento de línea para navegar rutas predefinidas.
    - LEDs RGB y buzzer para simular luces y sonidos de un rover.
4. **Estructura**: Chasis preensamblado del Cutebot/Maqueen, personalizable con bloques LEGO o piezas impresas en 3D.
5. **Estética**: Decoración inspirada en rovers marcianos, usando pintura o adhesivos.
6. **Energía**: Alimentado por baterías AAA o una batería de litio (Cutebot Pro/Maqueen Plus).
7. **Extensiones opcionales**: Brazo mecánico (con servos) o cámara simulada (LEDs para representar captura de imágenes).

## Fases del Proyecto

### Fase 1: Investigación y Planificación (1 semana)

- **Objetivo**: Comprender el contexto y definir metas.
- **Actividades**:
    - Investigar rovers marcianos (Curiosity, Perseverance) y las condiciones de Marte.
    - Estudiar las capacidades de Cutebot/Maqueen (motores, sensores) y micro:bit.
    - Definir misiones (ej., seguir una ruta, evitar obstáculos, emitir señales).
    - Formar equipos con roles: programador, diseñador, científico.
- **Entregable**: Informe con objetivos y esquema del proyecto.

### Fase 2: Diseño (1 semana)

- **Objetivo**: Planificar la personalización del rover.
- **Actividades**:
    - Diseñar modificaciones al Cutebot/Maqueen (bocetos o Tinkercad).
    - Planificar la estética (colores, formas marcianas).
    - Decidir sensores a usar (ultrasónico, línea) y posibles extensiones (brazo, LEDs).
    - Listar materiales adicionales (LEGO, pintura, servos).
- **Entregable**: Plano del diseño y lista de materiales.

### Fase 3: Construcción y Configuración (1-2 semanas)

- **Objetivo**: Preparar el robot físico.
- **Actividades**:
    - Configurar el Cutebot/Maqueen (instalar micro:bit, conectar sensor ultrasónico).
    - Personalizar el chasis con decoraciones o extensiones (LEGO, piezas 3D).
    - Verificar conexiones (motores, sensores, LEDs, buzzer).
    - Probar el suministro de energía (baterías AAA o litio).
- **Entregable**: Rover físico personalizado.

### Fase 4: Programación (2 semanas)

- **Objetivo**: Programar el rover para misiones marcianas.
- **Actividades**:
    - Usar MakeCode (bloques o JavaScript) para programar el micro:bit.
    - Implementar funciones básicas: movimiento, detección de obstáculos, seguimiento de línea.
    - Probar en un terreno simulado (caja con arena/rocas).
    - Ajustar el código según pruebas.
- **Ejemplo de código (MakeCode JavaScript)**:

```javascript
let distance = 0 
basic.forever(function () { 
	distance = cutebot.getDistance() 
	if (distance < 20) { 
		cutebot.stopcar() 
		cutebot.setLed(cutebot.RgbLed.RGB_LED_LEFT, 255, 0, 0)
		cutebot.setLed(cutebot.RgbLed.RGB_LED_RIGHT, 255, 0, 0)
		music.playTone(262, music.beat(BeatFraction.Whole)) } 
	else { 
		cutebot.motors(50, 50) 
		cutebot.setLed(cutebot.RgbLed.RGB_LED_LEFT, 0, 255, 0) 
		cutebot.setLed(cutebot.RgbLed.RGB_LED_RIGHT, 0, 255, 0) } 
})
```



# Proyecto STEAM: Rover Marciano con micro:bit y Cutebot/Maqueen

## Motivación
Este proyecto STEAM utiliza un robot como Cutebot o Maqueen, controlado por un micro:bit, para simular un Rover marciano, inspirando a los estudiantes a explorar ciencia, tecnología, ingeniería, arte y matemáticas. El contexto de una misión en Marte motiva el aprendizaje práctico y fomenta habilidades como programación, diseño y trabajo en equipo. Los objetivos incluyen:

- **Ciencia**: Entender las condiciones de Marte (terreno, gravedad) y su impacto en el rover.
- **Tecnología**: Programar el micro:bit para controlar el robot en tareas como navegación o detección de obstáculos.
- **Ingeniería**: Personalizar el Cutebot/Maqueen para simular un rover marciano funcional.
- **Arte**: Diseñar una estética inspirada en rovers reales (ej., Perseverance) con elementos creativos.
- **Matemáticas**: Calcular distancias, ángulos de giro o consumo energético.

El proyecto conecta con la exploración espacial, enseñando cómo los rovers recopilan datos sobre Marte y preparan futuras misiones humanas.

## Características del Rover
Usaremos un robot preensamblado como el ELECFREAKS Cutebot o DFRobot Maqueen, compatibles con micro:bit, con estas características adaptadas:

1. **Movilidad**: Dos motores DC para movimiento (adelante, atrás, giros) en terrenos simulados (arena, rocas).
2. **Control**: Programado vía micro:bit con MakeCode (bloques o JavaScript) para tareas autónomas o control remoto.
3. **Sensores**:
   - Sensor ultrasónico (HC-SR04) para evitar obstáculos.
   - Sensores de seguimiento de línea para navegar rutas predefinidas.
   - LEDs RGB y buzzer para simular luces y sonidos de un rover.
4. **Estructura**: Chasis preensamblado del Cutebot/Maqueen, personalizable con bloques LEGO o piezas impresas en 3D.
5. **Estética**: Decoración inspirada en rovers marcianos, usando pintura o adhesivos.
6. **Energía**: Alimentado por baterías AAA o una batería de litio (Cutebot Pro/Maqueen Plus).
7. **Extensiones opcionales**: Brazo mecánico (con servos) o cámara simulada (LEDs para representar captura de imágenes).

## Fases del Proyecto

### Fase 1: Investigación y Planificación (1 semana)
- **Objetivo**: Comprender el contexto y definir metas.
- **Actividades**:
  - Investigar rovers marcianos (Curiosity, Perseverance) y las condiciones de Marte.
  - Estudiar las capacidades de Cutebot/Maqueen (motores, sensores) y micro:bit.
  - Definir misiones (ej., seguir una ruta, evitar obstáculos, emitir señales).
  - Formar equipos con roles: programador, diseñador, científico.
- **Entregable**: Informe con objetivos y esquema del proyecto.

### Fase 2: Diseño (1 semana)
- **Objetivo**: Planificar la personalización del rover.
- **Actividades**:
  - Diseñar modificaciones al Cutebot/Maqueen (bocetos o Tinkercad).
  - Planificar la estética (colores, formas marcianas).
  - Decidir sensores a usar (ultrasónico, línea) y posibles extensiones (brazo, LEDs).
  - Listar materiales adicionales (LEGO, pintura, servos).
- **Entregable**: Plano del diseño y lista de materiales.

### Fase 3: Construcción y Configuración (1-2 semanas)
- **Objetivo**: Preparar el robot físico.
- **Actividades**:
  - Configurar el Cutebot/Maqueen (instalar micro:bit, conectar sensor ultrasónico).
  - Personalizar el chasis con decoraciones o extensiones (LEGO, piezas 3D).
  - Verificar conexiones (motores, sensores, LEDs, buzzer).
  - Probar el suministro de energía (baterías AAA o litio).
- **Entregable**: Rover físico personalizado.

### Fase 4: Programación (2 semanas)
- **Objetivo**: Programar el rover para misiones marcianas.
- **Actividades**:
  - Usar MakeCode (bloques o JavaScript) para programar el micro:bit.
  - Implementar funciones básicas: movimiento, detección de obstáculos, seguimiento de línea.
  - Probar en un terreno simulado (caja con arena/rocas).
  - Ajustar el código según pruebas.
- **Ejemplo de código (MakeCode JavaScript)**:

let distance = 0
basic.forever(function () {
    distance = cutebot.getDistance()
    if (distance < 20) {
        cutebot.stopcar()
        cutebot.setLed(cutebot.RgbLed.RGB_LED_LEFT, 255, 0, 0)
        cutebot.setLed(cutebot.RgbLed.RGB_LED_RIGHT, 255, 0, 0)
        music.playTone(262, music.beat(BeatFraction.Whole))
    } else {
        cutebot.motors(50, 50)
        cutebot.setLed(cutebot.RgbLed.RGB_LED_LEFT, 0, 255, 0)
        cutebot.setLed(cutebot.RgbLed.RGB_LED_RIGHT, 0, 255, 0)
    }
})

- **Notas**:
  - Agregar la extensión “Cutebot” o “Maqueen” en MakeCode: https://github.com/elecfreaks/pxt-cutebot o https://github.com/DFRobot/pxt-DFRobot_Maqueen.
  - El simulador de MakeCode permite probar el código virtualmente.[](https://makecode.microbit.org/pkg/microsoft/microbit-robot)
- **Entregable**: Código funcional y pruebas iniciales.

### Fase 5: Pruebas y Optimización (1-2 semanas)
- **Objetivo**: Validar el rover en un entorno simulado.
- **Actividades**:
  - Crear un terreno marciano (arena, rocas, rutas con cinta negra para seguimiento de línea).
  - Probar misiones: navegar una ruta, evitar obstáculos, emitir señales (LEDs/buzzer).
  - Ajustar código o estructura según fallos (ej., mejorar estabilidad o precisión).
  - Documentar resultados.
- **Entregable**: Informe de pruebas con video/fotos.

### Fase 6: Presentación y Reflexión (1 semana)
- **Objetivo**: Compartir resultados y reflexionar.
- **Actividades**:
  - Preparar una presentación (diapositivas, demo en vivo).
  - Explicar el diseño, programación y retos superados.
  - Reflexionar sobre aprendizajes STEAM.
  - Responder preguntas de la audiencia.
- **Entregable**: Presentación y reflexión escrita.

## Cómo Realizar el Proyecto
1. **Materiales**:
   - Robot: ELECFREAKS Cutebot o DFRobot Maqueen (sin micro:bit).[](https://www.dfrobot.com/product-1783.html)[](https://www.kiwi-electronics.com/en/smart-cutebot-pro-11613)
   - Microcontrolador: BBC micro:bit V1 o V2.
   - Sensores: Ultrasónico (incluido en Cutebot/Maqueen), sensores de línea integrados.
   - Energía: 3 baterías AAA o batería de litio (Cutebot Pro/Maqueen Plus).
   - Otros: Cinta negra (rutas), arena/rocas, LEGO/pintura para personalización.
   - Software: MakeCode (https://makecode.microbit.org).
2. **Espacio**: Aula con computadoras y espacio para pruebas.
3. **Tiempo**: 6-9 semanas.
4. **Evaluación**:
   - Funcionalidad (movimiento, sensores, misiones).
   - Creatividad en diseño y presentación.
   - Colaboración y documentación.
   - Reflexión STEAM.

## Beneficios Educativos
- **Habilidades técnicas**: Programación en MakeCode, uso de sensores, personalización de robots.
- **Resolución de problemas**: Ajustar código/diseño ante fallos.
- **Trabajo en equipo**: Coordinación entre roles.
- **Conexión real**: Inspiración en misiones espaciales reales.

El uso de Cutebot/Maqueen simplifica la construcción, permitiendo centrarse en la programación y creatividad, mientras el micro:bit ofrece una plataforma accesible para aprender robótica en un contexto marciano emocionante.[](https://x.com/MaestroManuelPa/status/1932814892253257736)

