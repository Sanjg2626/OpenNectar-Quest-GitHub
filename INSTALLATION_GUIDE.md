# Download, Installation, and Setup Guide

Project documentation: [English README](README.md) | [Versión en Español de esta Guía](GUIA_INSTALACION.md)

---

## Table of Contents

* [1. Prerequisites](#1-prerequisites)
* [2. Bluetooth Gamepad Pairing](#2-bluetooth-gamepad-pairing)
* [3. Installing the APK Package](#3-installing-the-apk-package)
* [4. First Launch and Providing the GameCube ISO](#4-first-launch-and-providing-the-gamecube-iso)
* [5. Spatial Window Configuration and Controls](#5-spatial-window-configuration-and-controls)
* [6. Troubleshooting](#6-troubleshooting)

---

## 1. Prerequisites

Before beginning the installation, ensure you have the following items ready:

1. **Meta Quest Headset:** Meta Quest 2, Meta Quest 3, Meta Quest 3S, or Meta Quest Pro with Developer Mode enabled.
2. **Connection Cable:** USB-C data cable to connect your headset to your computer.
3. **Sideloading Utility:** SideQuest installed on your computer (recommended visual method) or official Android Debug Bridge (ADB) tools.
4. **Bluetooth Gamepad:** A compatible controller paired directly to the headset:
   * Sony PlayStation 4 (DualShock 4) or PlayStation 5 (DualSense).
   * Microsoft Xbox Wireless Controller (Bluetooth-capable model).
   * Nintendo Switch Pro Controller.
   * Standard Bluetooth HID wireless gamepad (8BitDo, iPega, Gamesir, etc.).
5. **Legally Obtained Pikmin GameCube Disc Image (ISO):**
   * Pikmin USA (Revision 1) or Pikmin Europe (PAL Multi-5: English, French, German, Spanish, Italian).
   * Legal Notice: This project distributes zero proprietary game ROMs, textures, or copyrighted audio files.

---

## 2. Bluetooth Gamepad Pairing

To control the game, the gamepad must be paired directly to the Meta Horizon OS system settings:

1. Turn on your Meta Quest headset and put it on.
2. Open the **Universal Menu** and click the **Settings** gear icon.
3. Navigate to **Devices**.
4. Select **Bluetooth** and click the **Pair new device** button.
5. Place your gamepad into sync/pairing mode:
   * **PlayStation 4 / 5:** Press and hold down the `Share / Create` button and the center `PS` button simultaneously until the light bar flashes rapidly.
   * **Xbox:** Turn on the controller using the Xbox button, then press and hold the small circular pairing button on the top edge until the Xbox logo blinks rapidly.
   * **Nintendo Switch Pro:** Press and hold the small circular pairing button next to the USB-C charging port until the bottom indicator LEDs cycle back and forth.
6. Look at your headset screen, select your controller from the detected devices list, and confirm pairing.

---

## 3. Installing the APK Package

Download `OpenNectar-Quest-v1.0.apk` from the `dist/` folder or from the Releases tab on GitHub.

### Method A: Using SideQuest (Recommended)

1. Connect your Meta Quest to your PC using the USB-C cable.
2. Open the SideQuest application on your PC and verify the top-left connection circle is green.
3. In the upper-right utility toolbar of SideQuest, click the square icon with a downward-pointing arrow ("Install APK file from folder on computer").
4. Locate and select `OpenNectar-Quest-v1.0.apk`.
5. SideQuest will show an installation progress notification. Wait until it displays "All tasks completed successfully".

### Method B: Using ADB Command Line

If you prefer terminal commands:

```bash
adb devices
adb install -r dist/OpenNectar-Quest-v1.0.apk
```

---

## 4. First Launch and Providing the GameCube ISO

1. Put on your Meta Quest headset.
2. Open the **App Library** (the nine-dot grid icon on the bottom dock).
3. In the top-right filter dropdown, change the selection from "All" to **Unknown Sources**.
4. Click on **Open Nectar** to launch it.
5. On the first run, the application will detect that the required game assets are missing and display the built-in setup wizard.
6. The setup screen will state the exact directory path where your GameCube `.iso` image must be placed.
7. Connect the headset to your computer via USB:
   * Use SideQuest's built-in file explorer (the folder icon in the top toolbar) or Windows File Explorer.
   * Transfer your legal `.iso` file into the folder indicated on screen.
8. Once the ISO is copied, click the on-screen confirmation button in the headset to start unpacking.
9. The built-in extraction process takes 1 to 2 minutes to decompress the assets directly into headset storage. When finished, Pikmin will launch automatically.

---

## 5. Spatial Window Configuration and Controls

* **Spatial Window Placement:** Using your VR Touch controllers or hand tracking, grab the pill-shaped bar beneath the Open Nectar window to reposition it, scale the panel size, or toggle between flat and curved panoramic viewing modes.
* **Dynamic Active-Pad Focus:** As soon as you push an analog stick or press any button on your paired Bluetooth gamepad, the engine immediately assigns it to Player 1.
* **In-Game Button Remapping:** To adjust your button layout:
  * Press `Share` (PlayStation), `Back / View` (Xbox), or `Minus` (Switch Pro).
  * Alternatively, click the gear icon on the window toolbar.
  * Select any action and press your chosen button to reassign it.

---

## 6. Troubleshooting

* **Controller is paired but does not respond in game:**
  * Press a primary face button (Cross on PlayStation or A on Xbox) to claim active-pad focus.
  * Set the Meta Quest Touch controllers down on a flat surface so their tracking pointers do not steal window focus.
* **Storage access permission error:**
  * In the headset, navigate to Settings -> Apps -> Installed Apps -> Open Nectar -> Permissions, and ensure storage and file access is enabled.
* **ISO not recognized by the setup utility:**
  * Ensure your disc image matches a supported release (Pikmin NTSC-USA Revision 1 or Pikmin PAL Europe Multi-5). If your file is in a compressed format such as `.rvz` or `.ciso`, convert it back to standard uncompressed `.iso` format first.
