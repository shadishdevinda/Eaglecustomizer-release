# 🦅 Eagle Customizer — Official Releases

[![Version](https://img.shields.io/badge/version-1.0.12-blue.svg)](https://github.com/shadishdevinda/eaglecustomizer-release/releases/latest)
[![Rust](https://img.shields.io/badge/built%20with-Rust-orange.svg)](https://www.rust-lang.org/)
[![GUI](https://img.shields.io/badge/GUI-Slint%20Native-6f42c1.svg)](https://slint.dev/)
[![License](https://img.shields.io/badge/license-Proprietary-lightgrey.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20(Ubuntu)-success.svg)]()

Official binary release repository for **Eagle Customizer** by **Twin Eagle Studio**. Here you will find the portable Windows executable, the Debian package, and verification checksums for every stable release.

🌐 **Official Website**: [https://www.eaglecustomizer.com](https://www.eaglecustomizer.com)  
🛍️ **Microsoft Store**: [Eagle Customizer](https://apps.microsoft.com/detail/9N72CM5ZV3N5)

> This file is updated automatically with every release. Latest version: **1.0.12** (2026-10-30).

---

## 📖 Overview

**Eagle Customizer** is a lightweight peripheral management and remapping application. It is written in **pure Rust** with a native **Slint GUI**, so it starts instantly and uses very little memory and CPU.

- **No heavy runtimes**: no Python, Qt, Electron or .NET.
- **Works in the background**: close the window and your button mappings keep working (tray icon on Windows, a small background service on Linux).

---

## ✨ Features

- **🖱️ Mouse Customization**: Remap mouse buttons and the wheel to any of the built-in system and media actions. Left-click is locked by design to prevent accidental lockout. Includes pointer speed, acceleration, natural scrolling, and left-handed mode.
- **⌨️ Keyboard Remapping**: Visual keyboard remapping with per-device Numpad toggling, plus key-repeat speed and delay.
- **🎧 Audio Device Management**: Headphones, speakers and microphones: volume, mute, default playback/recording device, and a test sound.
- **👆 Touchpad Controls**: Speed, tap-to-click, two-finger scrolling, natural scrolling, and disable-while-typing.
- **🎨 Theme Follow**: Follows the system dark/light mode and accent color, or pick a theme yourself.

**On Windows**, mappings apply to all connected mice / all connected keyboards at once, and only the 5 standard mouse buttons can be remapped (Windows does not report extra side buttons).

---

## 📦 Downloads (v1.0.12)

| OS / Platform | Package | Description | Download |
| :--- | :--- | :--- | :--- |
| **Windows 10 / 11** | Microsoft Store | Recommended - installs and updates automatically | [Get it from the Store](https://apps.microsoft.com/detail/9N72CM5ZV3N5) |
| **Windows 10 / 11 (64-bit)** | `EagleCustomizer.exe` | Portable executable (no install) | [Download](https://github.com/shadishdevinda/eaglecustomizer-release/releases/download/v1.0.12/EagleCustomizer.exe) |
| **Ubuntu 22.04+ / Debian (amd64)** | `eaglecustomizer_1.0.12_amd64.deb` | Native `.deb` package | [Download](https://github.com/shadishdevinda/eaglecustomizer-release/releases/download/v1.0.12/eaglecustomizer_1.0.12_amd64.deb) |
| **All** | `SHA256SUMS.txt` | Checksums | [Download](https://github.com/shadishdevinda/eaglecustomizer-release/releases/download/v1.0.12/SHA256SUMS.txt) |

---

## 📥 Installation

### 🪟 Windows 10 / 11

#### Microsoft Store (Recommended)
1. Open [Eagle Customizer in the Microsoft Store](https://apps.microsoft.com/detail/9N72CM5ZV3N5) and click **Get**.
2. Launch it from the Start Menu. The Store keeps it up to date.

#### Portable executable
1. Download **`EagleCustomizer.exe`**.
2. Move it to a folder of your choice (e.g. `C:\Tools\EagleCustomizer\`).
3. Double-click to run. Windows SmartScreen may warn about a new file: click **More info → Run anyway**.

Use only one of the two (Store or portable), not both.

---

### 🐧 Linux (Ubuntu / Debian / Linux Mint / Pop!_OS)

1. Download **`eaglecustomizer_1.0.12_amd64.deb`**.
2. Open a terminal in the download folder and run:
   ```bash
   sudo apt install ./eaglecustomizer_1.0.12_amd64.deb
   ```
3. **First time only**: log out and back in (or reboot) so the installed `udev` rules give your user access to `/dev/input` and `/dev/uinput`.
4. Launch **Eagle Customizer** from your application launcher, or run `eaglecustomizer`.

The app checks for new versions once a day and can update itself.

---

## 🗑️ Uninstallation

### 🪟 Windows
- **Store app**: Settings → Apps → Installed apps → **Eagle Customizer** → `...` → **Uninstall**.
- **Portable**: turn off *Start with computer* in the app, quit it from the tray icon, then delete `EagleCustomizer.exe`.

### 🐧 Linux
```bash
sudo apt remove eaglecustomizer
```

To also remove your settings and logs:
```bash
rm -rf ~/.config/eaglecustomizer
```

---

## 🔐 Checksum Verification

Check a download against `SHA256SUMS.txt`:

### Linux
```bash
sha256sum -c --ignore-missing SHA256SUMS.txt
```

### Windows (PowerShell)
```powershell
Get-FileHash .\EagleCustomizer.exe -Algorithm SHA256
```
Compare the output with the hash in `SHA256SUMS.txt`.

Checksums for v1.0.12:
```
b047df653f9e4d71a39ec2870c254189f958c30801a1688cafa6db8fdc129159  eaglecustomizer_1.0.12_amd64.deb
02dd1597dd7245ed1a82c562d43a382e2822cbbf489f11c39377ced909a3bab2  EagleCustomizer.exe
```

---

## ⚙️ Settings & Log Locations

- **Linux**: `~/.config/eaglecustomizer/config.json` and `error.log`
- **Windows**: `%USERPROFILE%\.config\eaglecustomizer\config.json` and `error.log`

---

## 💬 Feedback

- 🌐 **Website**: [https://www.eaglecustomizer.com](https://www.eaglecustomizer.com)
- 📝 **Feedback & feature requests**: [Submit Feedback](https://www.eaglecustomizer.com/feedback)

---

*Copyright © 2026 Twin Eagle Studio. All rights reserved.*
