# Eagle Customizer

By **Twin Eagle Studio** · Version 2.1.1 · Windows 10/11 · Ubuntu 24.04+

An app for inspecting and customizing your mouse, keyboard, headphones, speakers,
microphones and touchpad.

## Install
- **Ubuntu:** `sudo apt install ./eaglecustomizer_2.1.1_amd64.deb` (Python and Qt are bundled
  inside the .deb), then log out and log back in.
- **Windows:** run `EagleCustomizer-Setup-2.1.1.exe`, or use the portable `EagleCustomizer.exe`.

## Features
- **Mouse** — remap up to 12 buttons (clicks, wheel, tilt, side and extra buttons) to any of the
  52 built-in actions. The left button is locked so the mouse always stays usable. System
  settings too: pointer speed, acceleration, scrolling and left-handed mode.
- **Keyboard** — remap any key on a live keyboard picture, plus key-repeat delay and speed. The
  numpad is drawn only when the device actually reports numpad keys, and each device has its own
  **Show numpad** switch.
- **Audio** — headphones, speakers and microphones: volume, mute, default device and a test sound.
- **Touchpad** — pointer speed, tap to click, natural and two-finger scrolling, disable while
  typing (Ubuntu/GNOME only; Windows has no touchpad settings page).
- **Theme** — follows the system light/dark theme, or you can pin light or dark.
- **Tray** — remapping keeps working with the window closed; toggle it from the tray menu.

## Settings and logs
Settings are stored in `config.json`, and errors in `error.log`:
- **Ubuntu:** `~/.config/eaglecustomizer/`
- **Windows:** `%APPDATA%\EagleCustomizer\`

`error.log` holds errors only — no mouse or keyboard data is ever written to it. It is capped at
256 KB and rolls over to `error.log.1`.

## Troubleshooting
- **No devices found on Ubuntu:** the udev rules need a session restart — log out and log back in
  (or reboot) after installing.
- **Something isn't working:** check `error.log` at the path above, and attach it when you send
  feedback.

## Privacy
Eagle Customizer never sends or stores your mouse/keyboard input. The only network use is the
**update check** (it reads `version.json` from the website, once a day). Turning off
Menu → *Check for updates automatically* stops that too.
