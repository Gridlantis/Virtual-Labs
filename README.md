# Virtual Labs — downloads

Installers for **Virtual Labs**, a desktop app for running virtual machines
from ISO files, Docker containers, and screen connections to other computers
on your network.

**→ [Download the latest release](https://github.com/Gridlockes/Virtual-Labs/releases/latest)**

Or straight from the site, which always points at the current release:

| Platform | Link |
| --- | --- |
| Linux | [gridlantis.org/download/virtual-labs/linux](https://gridlantis.org/download/virtual-labs/linux) |
| Windows | [gridlantis.org/download/virtual-labs/windows](https://gridlantis.org/download/virtual-labs/windows) |
| macOS | [gridlantis.org/download/virtual-labs/macos](https://gridlantis.org/download/virtual-labs/macos) |

More about the app: **[gridlantis.org/virtual-labs](https://gridlantis.org/virtual-labs)**

## This repository holds releases only

There is no source code here. It exists so the installers can be downloaded
without a GitHub account — release assets on a private repository require a
token, which would mean the website could not link to them.

## Verifying a download

Every release includes `SHA256SUMS`. Check your file against it before running
it:

```sh
sha256sum -c SHA256SUMS --ignore-missing     # Linux
shasum -a 256 -c SHA256SUMS --ignore-missing # macOS
```

```powershell
Get-FileHash .\Virtual-Labs-windows-x64-setup.exe -Algorithm SHA256
```

## These builds are not code-signed

Signing certificates cost money per year, and this app is free. So:

- **Windows** — SmartScreen will warn on first run. Choose *More info* →
  *Run anyway*.
- **macOS** — Gatekeeper will refuse it on first open. Right-click the app →
  *Open*, then confirm.
- **Linux** — AppImages need the executable bit: `chmod +x Virtual-Labs-linux-x86_64.AppImage`.

This is why the checksums matter: they are what tells you the file is the one
that was published.

## What it needs from your computer

| Feature | Needs |
| --- | --- |
| Virtual machines | QEMU (`qemu-system-x86_64`, `qemu-img`), plus OVMF for UEFI guests |
| Containers | Docker Engine, or Docker Desktop |
| Sharing this screen | `x11vnc`, or `wayvnc` on a Wayland session |

The app's **System** tab lists every one of these, whether it found it, and
the exact command to install what is missing.

---

© Gridlantis · [gridlantis.org](https://gridlantis.org)
