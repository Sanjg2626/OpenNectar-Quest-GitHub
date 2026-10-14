# Open Nectar: Port Nativo para Meta Quest (Horizon OS)

Idioma: [English Version](README.md) | Español | [Guía de Instalación Paso a Paso](GUIA_INSTALACION.md)

---

## Descripción General

Open Nectar para Meta Quest es un port nativo experimental en C++ de Pikmin (Nintendo GameCube, 2001) diseñado para ejecutarse directamente sobre Meta Horizon OS (Meta Quest 2, Meta Quest 3, Meta Quest 3S y Meta Quest Pro).

A diferencia de las configuraciones tradicionales basadas en emuladores como Dolphin, este port compila la lógica del motor de GameCube directamente a código máquina nativo ARM64. El juego se renderiza en una ventana espacial 2D de alta resolución dentro del entorno de Horizon OS con aceleración gráfica por hardware OpenGL ES 3.0.

---

## Características Principales

* Ejecución Nativa de 64 bits: Recompilado nativamente para arquitecturas ARM64 (Qualcomm Snapdragon XR2 Gen 1 y Snapdragon XR2 Gen 2). Cero sobrecarga de emulación, excelente estabilidad térmica y consumo reducido de batería.
* Ventana Espacial Horizon OS: Funciona como un panel espacial flotante que puede redimensionarse, reposicionarse, curvarse y anclarse en el entorno físico mediante Passthrough o en entornos virtuales de Horizon.
* Compatibilidad Universal con Mandos Bluetooth:
  * Sony PlayStation 4 (DualShock 4) y PlayStation 5 (DualSense).
  * Microsoft Xbox Wireless Controllers (Xbox One, Xbox Series X/S, Elite).
  * Nintendo Switch Pro Controller y Joy-Cons.
  * Mandos genéricos Bluetooth HID (8BitDo, iPega, Gamesir, etc.).
* Auto-enfoque Dinámico (Active-Pad Focus): Cualquier mando conectado que reciba pulsaciones de botones o movimiento de sticks asume inmediatamente el control del Jugador 1 en tiempo real.
* Eliminación de Conflictos de Hardware: Los dispositivos internos de seguimiento y mandos Touch VR de Horizon OS (vendor ID 0x2833) son excluidos del reparto de ranuras de gamepad, evitando que secuestren la entrada.
* Menú de Reasignación Integrado: Accesible en cualquier momento mediante los botones Share, Select o Minus (o mediante el icono de engranaje) para personalizar cada acción.
* Latencia Mínima de Entrada: Los bucles de presentación sincronizan directamente con SurfaceFlinger y Choreographer de Horizon OS.
* Mejoras Gráficas GX: Filtrado anisotrópico 16x, antialiasing, sombras dinámicas e iluminación por píxel opcional.
* Rendimiento: 60 FPS estables en Quest 2; modos seleccionables de 60, 90 o 120 FPS en Quest 3 y Quest 3S.

---

## Paquete de Distribución

El directorio `dist/` proporciona los elementos necesarios para utilizar o integrar este port:

* `dist/OpenNectar-Quest-v1.0.apk`: Paquete de aplicación precompilado listo para instalar. Cumple estrictamente con la legislación de propiedad intelectual al omitir cualquier archivo protegido por derechos de autor de Nintendo, datos de ROM, texturas o música comercial.
* `dist/open_nectar_quest_gamepad.patch`: Parche limpio en formato Git diff que contiene las mejoras de detección de mandos y auto-enfoque dinámico para Horizon OS en `pc_window.cpp`.

Para consultar el tutorial detallado de configuración e instalación, revisa el archivo [GUIA_INSTALACION.md](GUIA_INSTALACION.md).

---

## Controles Predeterminados

| Acción | Mando PlayStation | Mando Xbox | Nintendo Switch Pro |
| :--- | :---: | :---: | :---: |
| Arrancar / Lanzar Pikmin / Confirmar | Cruz | A | B |
| Silbato (Mantener) / Cancelar | Círculo | B | A |
| Disolver Grupo | Cuadrado | X | Y |
| Acostarse / Cambiar Color | Triángulo | Y | X |
| Mover a Olimar | Stick Analógico Izquierdo | Stick Analógico Izquierdo | Stick Analógico Izquierdo |
| Formación / Control de Pelotón (C-Stick) | Stick Analógico Derecho | Stick Analógico Derecho | Stick Analógico Derecho |
| Alinear Cámara | L1 | LB | L |
| Zoom de Cámara / Radar | R1 | RB | R |
| Gatillos Analógicos | L2 / R2 | LT / RT | ZL / ZR |
| Menú de Pausa | Options | Start / Menu | Plus |
| Menú de Ajustes / Reasignación | Share | Back / View | Minus |

---

## Créditos y Agradecimientos

* Open Nectar Team: Creadores y mantenedores de la capa original de port nativo para PC y Android de Pikmin.
* projectPiki / pikmin decompilation team: Proyecto de ingeniería inversa que reconstruyó el código fuente C++ del juego original de GameCube.
* Simple DirectMedia Layer (SDL2): Subsistema multiplataforma de audio, gestión de ventanas y entrada desarrollado por Sam Lantinga y la comunidad de SDL.
* Meta Platforms / Horizon OS Team: Especificaciones de plataforma Android XR y APIs de ventanas espaciales.
* stb_image (Sean Barrett) y bcdec (Krzysztof Narkowicz): Librerías de dominio público y licencias permisivas empleadas para la decodificación de texturas e imágenes.
* Dolphin Emulator Project: Documentación técnica indispensable acerca de la arquitectura de hardware de Nintendo GameCube y sus subsistemas GX.
* Nintendo Co., Ltd. y Shigeru Miyamoto: Creadores originales y titulares de los derechos de autor de Pikmin (2001).
* Declaración de Asistencia de IA: El análisis técnico, la adaptación del código y la depuración para este port en Meta Quest se realizaron con la asistencia del modelo Gemini 3.8 Flash, con todo el código, decisiones de arquitectura e implementación supervisados, revisados y verificados exhaustivamente por humanos.

---

## Descargo de Responsabilidad Legal

Este es un proyecto no comercial y educativo realizado por aficionados con fines exclusivos de preservación e investigación técnica. No está afiliado, respaldado ni asociado de ninguna manera con Nintendo Co., Ltd. Pikmin y Nintendo GameCube son marcas registradas de Nintendo.
