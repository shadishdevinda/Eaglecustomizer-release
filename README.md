# Eagle Customizer

**Mouse, keyboard, headphones, speakers, microphone and touchpad customizer for Ubuntu and Windows.**

By [Twin Eagle Studio](https://eaglecustomizer.vercel.app) · Current version: **2.1.0**

This repository hosts the ready-to-install downloads. The application source code is not public.

---

## Download

| Platform | File | Size |
|---|---|---|
| Ubuntu 24.04+ (64-bit) | `eaglecustomizer_2.1.0_amd64.deb` | 35 MB |
| Windows 10/11 (64-bit) | `EagleCustomizer-Setup-2.1.0.exe` | *coming soon* |

Get them from the [**Releases**](../../releases/latest) page.

A full user guide in Sinhala is included: **Eagle-Customizer-Guide-Sinhala.pdf**

---

## What it does

- Detects connected mice, keyboards, headphones, speakers, microphones and touchpads automatically (USB, Bluetooth, built-in).
- Remap any mouse button or key to one of **52 actions** — Copy, Paste, Screenshot, Volume, Browser tabs, Lock screen and more.
- Per-device settings on Ubuntu (each mouse can behave differently).
- Audio control: volume, mute, default device, test sound.
- System settings: pointer speed, natural scrolling, left-handed mode, key repeat.
- Device properties: Vendor ID, Product ID, battery %, connection type.
- Light / dark theme, system tray icon, optional start on login.

---

## Install on Ubuntu

**Requirements:** Ubuntu 24.04 LTS or newer, 64-bit Intel/AMD (amd64).

Python and Qt are bundled inside the package — you do not need to install them separately.

```bash
cd ~/Downloads
sudo apt install ./eaglecustomizer_2.1.0_amd64.deb
```

Then **log out and log back in** (or restart). This activates the permission rule
that lets the app read your mouse and keyboard. Open **Eagle Customizer** from
your Apps menu.

> If the app shows a yellow "No permission" banner, you have not logged out and
> back in yet.

### Uninstall

```bash
sudo apt remove eaglecustomizer
rm -rf ~/.config/eaglecustomizer    # also delete your settings
```

---

## Install on Windows

Run `EagleCustomizer-Setup-2.1.0.exe`. No administrator password is needed — it
installs for your user account only.

Windows may show **"Windows protected your PC"** because the installer is not
signed with a commercial code-signing certificate. Choose **More info → Run
anyway**. Some antivirus tools may also flag the app, because remapping buttons
requires reading keyboard and mouse input.

---

## Verify your download

Every release includes `SHA256SUMS.txt`. Check that the file you downloaded is
the one published here:

```bash
sha256sum -c SHA256SUMS.txt --ignore-missing
```

Expected output: `eaglecustomizer_2.1.0_amd64.deb: OK`

On Windows (PowerShell):

```powershell
Get-FileHash .\eaglecustomizer_2.1.0_amd64.deb -Algorithm SHA256
```

Compare the result with the line in `SHA256SUMS.txt`.

---

## Privacy

Eagle Customizer does **not** send or store your mouse or keyboard input
anywhere. The only network request it makes is an update check: once a day it
reads a small `version.json` file from our website to see whether a newer
version exists. That request sends only standard connection information (your IP
address and an app identifier such as `EagleCustomizer/2.1.0 (Linux)`).

You can turn it off in the app menu: **Check for updates automatically**.

---

## Help and feedback

- Website: https://eaglecustomizer.vercel.app
- Feedback: https://eaglecustomizer.vercel.app/feedback

Please include your operating system version and what you were doing when the
problem happened.
