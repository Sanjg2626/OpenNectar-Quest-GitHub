# Open Nectar: Meta Quest Native Port (Horizon OS)

Language: English | [Versión en Español](LEEME_ES.md) | [Installation Guide](INSTALLATION_GUIDE.md)

---

## Overview

Open Nectar for Meta Quest is an experimental, native C++ port of Pikmin (Nintendo GameCube, 2001) designed to execute directly on Meta Horizon OS (Meta Quest 2, Meta Quest 3, Meta Quest 3S, and Meta Quest Pro).

Unlike conventional configurations that rely on emulation layers (such as Dolphin), this port compiles the reverse-engineered GameCube engine logic directly into native ARM64 machine code. It renders inside a high-resolution 2D spatial window in Horizon OS with full hardware-accelerated OpenGL ES 3.0 graphics.

---

## Key Features

* Native 64-bit Execution: Recompiled natively for ARM64 (Qualcomm Snapdragon XR2 Gen 1 and Snapdragon XR2 Gen 2 architectures). Zero virtualization overhead, low thermals, and minimal battery consumption.
* Horizon OS Volumetric Window: Operates as a floating spatial panel that can be resized, repositioned, curved, and anchored in physical space via Passthrough or inside virtual Horizon environments.
* Universal Bluetooth Gamepad Support:
  * Sony PlayStation 4 (DualShock 4) and PlayStation 5 (DualSense).
  * Microsoft Xbox Wireless Controllers (Xbox One, Xbox Series X/S, Elite).
  * Nintendo Switch Pro Controller and Joy-Cons.
  * Generic Bluetooth HID gamepads (8BitDo, iPega, Gamesir, etc.).
* Dynamic Active-Pad Focus: Any connected controller receiving button or stick input immediately assumes control of Player 1 in real time.
* Hardware Conflict Elimination: Internal Horizon OS Touch VR tracking peripherals (vendor ID 0x2833) are automatically filtered out from gamepad slot allocation, preventing input hijacking.
* In-Game Remapping Interface: Accessible at any time via Share, Select, or Minus buttons (or the gear icon) to customize every action.
* Ultra-Low Input Latency: Render loops synchronize directly with Horizon OS SurfaceFlinger and Choreographer presentation pacing.
* Graphical Enhancements: 16x anisotropic filtering, anti-aliasing, dynamic shadows, and optional per-pixel lighting.
* Performance: Solid 60 FPS on Quest 2; selectable 60, 90, or 120 FPS modes on Quest 3 and Quest 3S.

---

## Distribution Package

The `dist/` directory provides everything needed to run or integrate this port:

* `dist/OpenNectar-Quest-v1.0.apk`: Ready-to-install standalone application package. Complies fully with copyright law by omitting all copyrighted Nintendo assets, ROMs, textures, and music.
* `dist/open_nectar_quest_gamepad.patch`: Clean Git diff containing the Horizon OS gamepad detection and active-pad focus enhancements for `pc_window.cpp`.

For detailed installation and setup instructions, refer to [INSTALLATION_GUIDE.md](INSTALLATION_GUIDE.md).

---

## Default Controls

| Action | PlayStation Controller | Xbox Controller | Nintendo Switch Pro |
| :--- | :---: | :---: | :---: |
| Pluck / Throw Pikmin / Confirm | Cross | A | B |
| Whistle (Hold) / Cancel | Circle | B | A |
| Disband Squad | Square | X | Y |
| Lie Down / Switch Pikmin | Triangle | Y | X |
| Move Olimar | Left Analog Stick | Left Analog Stick | Left Analog Stick |
| Swarm / Formation Control (C-Stick) | Right Analog Stick | Right Analog Stick | Right Analog Stick |
| Camera Align | L1 | LB | L |
| Camera Zoom / Radar | R1 | RB | R |
| Analog Triggers | L2 / R2 | LT / RT | ZL / ZR |
| Pause Menu | Options | Start / Menu | Plus |
| Settings / Remap Menu | Share | Back / View | Minus |

---

## Credits and Acknowledgments

* Open Nectar Team: Creators and maintainers of the original native PC and Android port layer for Pikmin.
* projectPiki / pikmin decompilation team: Reverse engineering initiative that reconstructed the GameCube C++ codebase.
* Simple DirectMedia Layer (SDL2): Cross-platform audio, windowing, and input subsystem maintained by Sam Lantinga and the SDL development community.
* Meta Platforms / Horizon OS Team: Android XR platform specifications and spatial windowing APIs.
* stb_image (Sean Barrett) and bcdec (Krzysztof Narkowicz): Permissive libraries utilized for texture decompression and image handling.
* Dolphin Emulator Project: Invaluable technical documentation regarding Nintendo GameCube system architecture and GX subsystems.
* Nintendo Co., Ltd. and Shigeru Miyamoto: Original creators and copyright holders of Pikmin (2001).
* AI Assistance Disclosure: Technical analysis, code adaptation, and debugging assistance for this Meta Quest port was performed with the assistance of the Gemini 3.8 Flash model, with all code, architecture decisions, and implementation fully reviewed, tested, and verified by humans.

---

## Legal Disclaimer

This is a non-profit, educational fan project developed exclusively for hardware preservation and research purposes. It is not affiliated with, endorsed by, or associated in any way with Nintendo Co., Ltd. Pikmin and Nintendo GameCube are registered trademarks of Nintendo.
