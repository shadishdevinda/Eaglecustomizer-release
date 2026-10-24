# 🦅 Eagle Customizer — Official Releases

[![Version](https://img.shields.io/badge/version-2.2.0-blue.svg)](https://github.com/shadishdevinda/eaglecustomizer-release/releases)
[![Rust](https://img.shields.io/badge/built%20with-Rust-orange.svg)](https://www.rust-lang.org/)
[![GUI](https://img.shields.io/badge/GUI-Slint%20Native-6f42c1.svg)](https://slint.dev/)
[![License](https://img.shields.io/badge/license-Proprietary-lightgrey.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20(Ubuntu)-success.svg)]()

Official binary release repository for **Eagle Customizer** by **Twin Eagle Studio**. Here you will find official compiled installers, standalone executables, Debian packages, and verification checksums for every stable release.

🌐 **Official Website**: [https://eaglecustomizer.vercel.app](https://eaglecustomizer.vercel.app)  
📂 **Source Code Repository**: [shadishdevinda/EagleCustomizer](https://github.com/shadishdevinda/EagleCustomizer)

---

## 📖 Overview

**Eagle Customizer** is an ultra-lightweight, high-performance peripheral management and remapping application designed for power users, gamers, and developers. Built from the ground up in **100% pure Rust** with a modern **Slint native GUI**, it delivers instant responsiveness with virtually zero system overhead.

### ⚡ Why Pure Rust?
- **Ultra-Low Memory Footprint**: The background remapping daemon (`eaglecustomizerd`) consumes only **~2.8 MB of RAM** and ~0% CPU.
- **Zero Heavy Dependencies**: Completely free of Python, Qt, PyInstaller, or Electron runtimes.
- **Instant Launch**: Starts up in milliseconds using a native software/hardware-rendered Slint UI.
- **Background Persistence**: Closing the window detaches the GUI completely while keeping your hardware remappings active in the background.

---

## ✨ Features

- **🖱️ Mouse Customization**: Remap up to 12 physical buttons (Left, Right, Middle, Wheel Up/Down, Wheel Tilt Left/Right, Side Buttons 1–5) to any of the 52 built-in system and media actions. Left-click is locked by design to prevent accidental lockout. Includes pointer speed, acceleration profile, natural scrolling, and left-handed mode.
- **⌨️ Keyboard Remapping**: Full interactive visual keyboard remapping. Dynamically inspects physical layout and supports per-device Numpad toggling. Includes key-repeat speed and repeat delay controls.
- **🎧 Audio Device Management**: Inspect connected headphones, speakers, and microphones. Adjust volume levels (up to 150%), toggle mute, change default playback/recording sinks, and test audio playback.
- **👆 Touchpad Controls**: Touchpad speed, tap-to-click, two-finger scrolling, natural scrolling, and automatic disable-while-typing.
- **🎨 System Theme Follow**: Seamlessly follows system Dark/Light mode and native accent colors (including GNOME 47+ accents), or allows manual theme pinning.

---

## 📦 Downloads (v2.2.0)

| OS / Platform | Package File | Description | Download |
| :--- | :--- | :--- | :--- |
| **Windows 10 / 11 (64-bit)** | `EagleCustomizer-Setup-2.2.0.exe` | Setup Wizard (Inno Setup) | [Download](https://github.com/shadishdevinda/eaglecustomizer-release/releases/latest) |
| **Windows 10 / 11 (64-bit)** | `EagleCustomizer.exe` | Portable Standalone Executable | [Download](https://github.com/shadishdevinda/eaglecustomizer-release/releases/latest) |
| **Ubuntu / Debian (amd64)** | `eaglecustomizer_2.2.0_amd64.deb` | Native `.deb` Package (~5 MB) | [Download](https://github.com/shadishdevinda/eaglecustomizer-release/releases/latest) |
| **All Platforms** | `SHA256SUMS.txt` | Cryptographic Checksums | [Download](https://github.com/shadishdevinda/eaglecustomizer-release/releases/latest) |

---

## 📥 Installation Instructions

### 🪟 Windows (Windows 10 / 11 64-bit)

#### Method 1: Installer Setup Wizard (Recommended)
1. Download **`EagleCustomizer-Setup-2.2.0.exe`**.
2. Double-click the downloaded setup file.
3. Follow the wizard prompts (select optional desktop shortcut or start-on-boot).
4. Launch **Eagle Customizer** from your Desktop shortcut or Start Menu.

#### Method 2: Portable Standalone Executable
1. Download **`EagleCustomizer.exe`**.
2. Move it to your desired folder (e.g. `C:\Tools\EagleCustomizer\`).
3. Double-click to run directly. No installation or registry changes required.

---

### 🐧 Linux (Ubuntu / Debian / Linux Mint / Pop!_OS)

1. Download **`eaglecustomizer_2.2.0_amd64.deb`**.
2. Open terminal in the download directory and run:
   ```bash
   sudo apt update
   sudo apt install ./eaglecustomizer_2.2.0_amd64.deb
   ```
3. **Important (First Time Setup)**:  
   Log out of your Linux desktop and log back in (or reboot) so the newly installed `udev` rules take effect and grant your user permissions to access `/dev/input` and `/dev/uinput` devices.
4. Launch the app from your application launcher (search **Eagle Customizer**) or execute:
   ```bash
   eaglecustomizer


## 🗑️ Uninstallation Instructions

### 🪟 Windows
1. Open **Windows Settings** (`Win + I`) → **Apps** → **Installed Apps** (or Control Panel → **Programs and Features**).
2. Find **Eagle Customizer** in the list.
3. Click the three dots (`...`) and click **Uninstall**.
4. The uninstaller will cleanly remove all installed binaries and shortcuts.

### 🐧 Linux (Ubuntu / Debian)
To remove the application and background daemon:
```bash
sudo apt remove eaglecustomizer
```

To remove all configuration files and error logs created by the user:
```bash
rm -rf ~/.config/eaglecustomizer
```

---

## 🔐 Checksum Verification

To verify that your downloaded file has not been corrupted or altered, check its SHA-256 hash against `SHA256SUMS.txt`:

### On Linux:
```bash
sha256sum -c SHA256SUMS.txt
```
*(Should output `... OK` for each matched file)*

### On Windows (PowerShell):
```powershell
Get-FileHash .\EagleCustomizer-Setup-2.2.0.exe -Algorithm SHA256
Get-FileHash .\EagleCustomizer.exe -Algorithm SHA256
```
Compare the output string with the hash in `SHA256SUMS.txt`.

---

## ⚙️ Configuration Files & Log Locations

Eagle Customizer stores device mappings and application configurations in an atomic JSON file:

- **Linux Settings**: `~/.config/eaglecustomizer/config.json`
- **Linux Error Log**: `~/.config/eaglecustomizer/error.log`
- **Windows Settings**: `%USERPROFILE%\.config\eaglecustomizer\config.json`
- **Windows Error Log**: `%USERPROFILE%\.config\eaglecustomizer\error.log`

---

## 💬 Feedback & Community

- 🌐 **Project Home**: [https://eaglecustomizer.vercel.app](https://eaglecustomizer.vercel.app)
- 📝 **Feedback & Feature Requests**: [Submit Feedback](https://eaglecustomizer.vercel.app/feedback)
- 🐛 **Report a Bug**: [GitHub Issues](https://github.com/shadishdevinda/EagleCustomizer/issues)

---

*Copyright © 2026 Twin Eagle Studio. All rights reserved.*
```