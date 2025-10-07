# 🎮 Raspberry Pi-Powered Arcade Machine with RetroPie
## 🧑‍💻 Author

**Cagri Goksu Ustundag**  
IT Project Volunteer  
Digital Inclusion A.S.B.L.  
Luxembourg — September 2025  

A DIY arcade machine project using a **Raspberry Pi 3B+** and **RetroPie**, developed by **Cagri Goksu Ustundag** as part of a **Digital Inclusion A.S.B.L.** initiative.

## 🧩 Table of Contents

1. [Overview](#overview)  
2. [Hardware Components](#hardware-components)  
3. [SD Card Preparation](#sd-card-preparation)  
4. [Arcade Machine Setup](#arcade-machine-setup)  
5. [Configurations](#configurations)  
6. [License](#license)
   
## 🕹️ Overview

This project transforms a **Raspberry Pi** into a fully functional **arcade machine** powered by **RetroPie**.  
It covers hardware assembly, SD card setup, and emulator configuration for a smooth retro gaming experience.

## ⚙️ Hardware Components

| Component | Description |
|------------|-------------|
| **Raspberry Pi 3B+** | Main processing unit |
| **Screen (HDMI)** | Video output |
| **5V–3A Micro-USB Power Supply** | Power for the Raspberry Pi |
| **SD Card (≥ 32GB)** | Storage for RetroPie and game ROMs |
| **Input Devices** | Keyboard (for setup), Joystick, and 6 Arcade Buttons (Start, Select, A, B, X, Y) |
| **USB Encoder** | Connects joystick and buttons to Raspberry Pi |
| **Speaker (optional)** | 3.5mm or USB-powered audio output |

## 💾 SD Card Preparation
### 🪟 Windows

1. Download and install **[balenaEtcher](https://etcher.balena.io/)**.  
2. Insert the SD card.  
3. Select the RetroPie image file (`.img` or `.zip`).  
4. Select the target SD card.  
5. Click **Flash** and wait for completion.  

To **extract/backup** SD card images, use **Win32 Disk Imager**.

### 🐧 Linux

**To write image:**
```bash
sudo dd if=retropie.img of=/dev/sdX bs=4M status=progress conv=fsync
```

## 🧱 Arcade Machine Setup

### 1. Hardware Assembly
- Mount **joysticks** and **buttons** in a comfortable layout.  
- Connect buttons and joystick to **USB encoder** (joystick: 5-pin; buttons: 3-pin).  
- Plug the encoder into the Raspberry Pi via USB.

### 2. Connecting to Raspberry Pi
- Connect display (HDMI).  
- Insert the prepared SD card.  
- Attach keyboard and optional speaker.  
- Power on the Raspberry Pi via micro-USB.  

🧠 **Tip:** USB ports on Raspberry Pi 3B+ have priority order:  
`Left-top → Left-bottom → Right-top → Right-bottom`.

## ⚙️ Configurations
### 🎹 Keyboard Mapping

| Function | Key |
|-----------|-----|
| D-Pad | Arrow Keys |
| Start | Enter |
| Select | Right Shift |
| A | X |
| B | Z |
| X | S |
| Y | A |
| Left Shoulder | Q |
| Right Shoulder | W |
| Hotkey | Left Ctrl |

**Useful shortcuts:**
- `Hotkey + Enter`: Exit to EmulationStation  
- `F4`: Open terminal  

### 🕹️ Joystick & Button Mapping

| Function | Control |
|-----------|----------|
| D-Pad | Joystick directions |
| Start | Start button |
| Select | Select button |
| A/B/X/Y | Corresponding buttons |
| Hotkey | *(skip setting; disables in-game menu access)* |

### 🎮 Emulator UI Settings

To set a game to launch automatically on startup:

1. Exit any game (`Left Ctrl + Enter`).  
2. Press `F4` to open terminal.  
3. Edit startup script:
   ```bash
   cd /opt/retropie/configs/all/
   nano autostart.sh
   ```
4. Modify the following line:
   ```bash
    "nes" "$HOME/RetroPie/roms/nes/game_name.nes"
   ```
5. Save and exit (`Ctrl + O, Enter, Ctrl + X`).

6. Reboot:
   ```bash
    sudo reboot
   ```
