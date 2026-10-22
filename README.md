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

## Set the website links (before a public release)
Set **`WEBSITE_URL`** in `eaglecustomizer/branding.py` — that is the only required change. Then:
- **Send feedback** → `WEBSITE_URL/feedback`
- **Check for updates** → `WEBSITE_URL/version.json`
- **Download** → `WEBSITE_URL/download`

If you need different links, set `FEEDBACK_URL` / `UPDATE_URL` directly.

## Build
- Windows (**from GitHub**): `git tag vx.y.z && git push origin vx.y.z` →
  `.github/workflows/windows-build.yml` builds both `.exe` files and uploads them to the
  release repo. For a test build, use *Run workflow* on the Actions tab. Setup: **RELEASING.md**.
- Windows (manually): `build_windows.bat` (Python 3.11+, Inno Setup 6 optional)
- Ubuntu (release): `bash packaging/linux/build_deb_nuitka.sh` → `dist/eaglecustomizer_x.y.z_amd64.deb`
  Nuitka compiles the code into a native binary (no `.py` files in the package).
  The build runs inside a podman container (`ubuntu:22.04`) for glibc compatibility, so
  **podman is required**. Override the image with `BASE_IMAGE=ubuntu:24.04`.
- Ubuntu (dev only): `bash packaging/linux/build_deb.sh` → `dist/dev/..._all.deb` (small, ~150 KB)
  but it installs the code in readable form. Do not use this for public releases.
  (Releases go to `dist/`, dev builds to `dist/dev/` — they never mix.)
- Run from source: `python3 run.py` · demo: `python3 run.py --demo`

Dependencies for running from source are in `requirements.txt` (Linux) and
`requirements-windows.txt` (Windows).

After a build, `dist/` also contains `SHA256SUMS.txt` and `version.json`.
For the release procedure, see **RELEASING.md**.

## Files
| File | What it does |
|---|---|
| `eaglecustomizer/branding.py` | **App name, author, version, website / feedback / update links** |
| `eaglecustomizer/updates.py` | Update check, safe links (https + allowed hosts only) |
| `eaglecustomizer/main.py` | QApplication, single instance, `--demo` / `--background` |
| `eaglecustomizer/window.py` | Main window, sidebar, theme switch, feedback, menu, tray |
| `eaglecustomizer/pages.py` | Mouse / Keyboard / Audio / Touchpad pages |
| `eaglecustomizer/theme.py` | Light / dark colors, system theme detection, Qt stylesheet |
| `eaglecustomizer/art.py` | Device pictures and animations (cairo) |
| `eaglecustomizer/widgets.py` | Switch, theme selector, chips, action picker |
| `eaglecustomizer/actions.py` | The 52 actions, keyboard layout and numpad layout |
| `eaglecustomizer/qt.py` | PySide6 / PyQt6 compatibility (both the .exe and the .deb use PySide6) |
| `eaglecustomizer/backend_base.py` | Backend interface and backend selection |
| `eaglecustomizer/backend_*.py` | Linux / Windows / Demo backends |
| `eaglecustomizer/config.py` | The settings JSON file |
| `eaglecustomizer/log.py` | Error log (`error.log`), crash handler |
| `tools/release_info.py` | Version, checksums, version.json, Windows version info |
| `tools/make_icon.py` | Generates the app icon (PNG and ICO) |
| `tools/screenshots.py` | Real app screenshots for the guide (demo mode, offscreen) |
| `tools/build_guide.py` | Builds the Sinhala user and developer guide (PDF) |

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
