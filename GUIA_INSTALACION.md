# Guía de Descarga, Instalación y Configuración

Documentación del proyecto: [LEEME en Español](LEEME_ES.md) | [English Version of this Guide](INSTALLATION_GUIDE.md)

---

## Índice

* [1. Requisitos Previos](#1-requisitos-previos)
* [2. Emparejar el Mando por Bluetooth](#2-emparejar-el-mando-por-bluetooth)
* [3. Instalación del Paquete APK](#3-instalacion-del-paquete-apk)
* [4. Primer Inicio y Copia de la ISO Legal](#4-primer-inicio-y-copia-de-la-iso-legal)
* [5. Configuración en el Visor y Controles](#5-configuracion-en-el-visor-y-controles)
* [6. Solución de Problemas Frecuentes](#6-solucion-de-problemas-frecuentes)

---

## 1. Requisitos Previos

Antes de comenzar, asegúrate de contar con los siguientes elementos:

1. **Visor Meta Quest:** Compatible con Meta Quest 2, Meta Quest 3, Meta Quest 3S o Meta Quest Pro con el Modo Desarrollador activado.
2. **Cable de conexión:** Cable USB-C de datos para conectar el visor al ordenador.
3. **Software de carga lateral:** SideQuest instalado en tu ordenador (método gráfico recomendado) o las herramientas oficiales de Android Debug Bridge (ADB).
4. **Mando inalámbrico Bluetooth:** Un mando compatible emparejado directamente al visor:
   * Sony PlayStation 4 (DualShock 4) o PlayStation 5 (DualSense).
   * Microsoft Xbox Wireless Controller (versiones con Bluetooth).
   * Nintendo Switch Pro Controller.
   * Mandos Bluetooth universales con estándar HID (8BitDo, iPega, Gamesir, etc.).
5. **Copia legal de Pikmin para Nintendo GameCube (archivo ISO):**
   * Pikmin USA (Revisión 1) o Pikmin Europa (PAL Multi-5: Español, Inglés, Francés, Alemán, Italiano).
   * Aviso legal: Este proyecto no incluye ni distribuye ningún archivo de ROM, música o gráficos protegidos por derechos de autor.

---

## 2. Emparejar el Mando por Bluetooth

Para controlar el juego, el mando debe estar vinculado directamente al sistema operativo del visor (Meta Horizon OS):

1. Enciende tu visor Meta Quest y colócatelo.
2. Abre el **Menú Universal** y selecciona el icono de **Ajustes** (engranaje).
3. Entra en el apartado **Dispositivos**.
4. Haz clic en **Bluetooth** y pulsa sobre el botón **Emparejar nuevo dispositivo**.
5. Pon tu mando en modo de sincronización:
   * **PlayStation 4 / 5:** Mantén presionados al mismo tiempo los botones `Share / Create` y el botón central `PS` hasta que la barra de luz parpadee rápidamente.
   * **Xbox:** Enciende el mando con el botón Xbox y mantén presionado el botón circular pequeño de emparejamiento en el borde superior frontal hasta que el logo parpadee rápidamente.
   * **Nintendo Switch Pro:** Mantén presionado el botón pequeño de emparejamiento situado junto al puerto de carga USB-C hasta que las luces inferiores comiencen a correr de lado a lado.
6. En la pantalla de tu visor aparecerá el mando en la lista de dispositivos disponibles. Selecciónalo y confirma la vinculación.

---

## 3. Instalación del Paquete APK

Descarga el archivo `OpenNectar-Quest-v1.0.apk` desde la carpeta `dist/` o desde el apartado de Releases en el repositorio de GitHub.

### Opción A: Mediante SideQuest (Recomendado)

1. Conecta tu Meta Quest al ordenador mediante el cable USB-C.
2. Abre el programa SideQuest en tu ordenador y confirma que en la esquina superior izquierda aparezca el punto verde de conexión activa.
3. En la barra superior derecha de SideQuest, haz clic en el icono cuadrado con una flecha hacia abajo ("Install APK file from folder on computer").
4. Busca y selecciona el archivo `OpenNectar-Quest-v1.0.apk`.
5. SideQuest mostrará una notificación verde en la parte inferior cuando la instalación haya finalizado con éxito ("All tasks completed successfully").

### Opción B: Mediante consola de comandos ADB

Si prefieres usar la terminal de comandos:

```bash
adb devices
adb install -r dist/OpenNectar-Quest-v1.0.apk
```

---

## 4. Primer Inicio y Copia de la ISO Legal

1. Colócate el visor.
2. Abre la **Biblioteca de aplicaciones** (icono de la cuadrícula de nueve puntos en la barra inferior).
3. En el selector de categorías situado en la esquina superior derecha, cambia de "Todas" a **Orígenes desconocidos**.
4. Haz clic sobre **Open Nectar** para abrirlo.
5. Al ejecutarse por primera vez, la aplicación comprobará que faltan los archivos del juego y abrirá el instalador guiado en pantalla.
6. El instalador indicará la ruta de la carpeta interna donde debes depositar tu archivo `.iso` de GameCube.
7. Conecta el visor al ordenador mediante el cable USB:
   * Puedes usar la herramienta de transferencia de archivos de SideQuest (icono de carpeta en la barra superior) o el explorador de archivos de Windows.
   * Copia tu archivo ISO legal en la ruta indicada por la pantalla del instalador.
8. Una vez transferida la ISO, presiona el botón de confirmación en la pantalla del visor para iniciar la extracción.
9. El proceso tardará aproximadamente entre 1 y 2 minutos en descomprimir todos los assets originales localmente en la memoria del visor. Al terminar, el juego se iniciará de forma automática.

---

## 5. Configuración en el Visor y Controles

* **Ajuste de la ventana espacial:** Con los mandos táctiles del visor o con el seguimiento de manos, puedes agarrar la barra blanca situada debajo de la ventana de Open Nectar para acercarla, alejarla, cambiar su tamaño o activar el modo de pantalla curva panorámica.
* **Auto-enfoque del mando (Active-Pad Focus):** Al presionar cualquier botón o mover cualquier stick en tu mando Bluetooth emparejado, el juego detectará la entrada de inmediato y asumirá el control del Jugador 1 en tiempo real.
* **Menú de reasignación de botones:** Para personalizar la función de cada botón:
  * Pulsa el botón `Share` (PlayStation), `Back / View` (Xbox) o `Minus` (Switch Pro).
  * También puedes hacer clic sobre el icono de engranaje en la barra de herramientas de la ventana.
  * Selecciona cualquier acción y presiona el botón que desees asignarle.

---

## 6. Solución de Problemas Frecuentes

* **El mando está emparejado pero el juego no responde:**
  * Pulsa un botón de acción principal (Cruz en PlayStation o A en Xbox) para activar el auto-enfoque dinámico.
  * Deja los mandos táctiles de Meta Quest sobre una mesa para que sus sensores de puntero no le quiten el foco a la ventana.
* **Aviso de error en el acceso al almacenamiento:**
  * En el visor, abre Ajustes -> Aplicaciones -> Aplicaciones instaladas -> Open Nectar -> Permisos, y comprueba que tenga activado el permiso de acceso a archivos y almacenamiento.
* **La ISO no es reconocida por el instalador:**
  * Asegúrate de que la copia pertenezca a una versión compatible (Pikmin NTSC-USA Revisión 1 o Pikmin PAL Europa Multi-5). Si tu copia está comprimida en formatos como `.rvz` o `.ciso`, conviértela previamente a `.iso` sin comprimir.
