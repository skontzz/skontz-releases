# Skontz Control System

**A Windows 10/11 control panel that shows what your PC is doing and changes Windows settings only when you ask, always with a way back.**

This repository only publishes the **official installers**. The source code is not published here. Download the latest
version from the [**Releases**](../../releases/latest) page.

> Skontz Control System is an independent project. It is not affiliated with, endorsed by or sponsored by Microsoft or any
> other company mentioned here. Use it at your own risk and keep backups of important files.

---

## What it does

Every function exists to answer one question: *"what does my PC do, and can I make it better without breaking it?"*
Each action tells you what it changes, how long it takes, what you lose, and whether you can undo it.

| Area | What it is for |
|---|---|
| **Dashboard** | A PC check-up (space, memory, security, startup, crashes, network) with a health score and one-click recommended actions. Reading is always safe: nothing changes until you confirm. |
| **Hardware Monitor** | Live CPU, GPU, memory, disk and network sensors, plus the full PC specification (board, BIOS, memory modules, disks). Export to CSV or text. |
| **Fresh install** | A guided wizard for a freshly installed Windows: apps, the recommended tweaks, extras, and a summary before anything runs. |
| **Windows / Mouse / Keyboard / GPU** | 235 reversible tweaks for performance, privacy, appearance, services, input and graphics, each with a plain-language explanation and the exact registry/service change it makes. |
| **Debloat** | Removes preinstalled apps and features you do not want (some cannot be undone: the app says so before you confirm). |
| **Profiles** | Ready-made tweak bundles (for example *competitive* or *privacy*) and your own profiles you can save and import. |
| **Games** | Prepares the PC for a specific game (process priority and affinity requests, power plan) and restores everything afterwards. |
| **Install apps** | Install and update programs through Microsoft's `winget`, with a catalog of popular apps. |
| **Cleanup** | Removes temporary files and caches, shows what it found first, never touches your documents. |
| **Startup** | Lists the programs that open with Windows and lets you turn them on or off. |
| **Repair** | Runs Windows repair tools (DISM, SFC, disk check, network reset) with progress and a plain explanation of each. |
| **Overlay** | FPS and usage numbers on top of a game. |
| **Mouse / Monitor tests** | Mouse polling rate; dead pixels, ghosting and backlight bleed. |
| **Speed test / Packet loss** | Download, upload, ping and jitter; shows where a connection loses packets. |
| **Restore** | The full history of what the app changed, with undo for one change or everything. |
| **Antivirus/Defender** | Shows the detected antivirus and the exclusions the app uses. |

## Why you can trust a tool that changes Windows

- **Everything is reversible and logged.** The app keeps a history of each change and can undo it. Before a batch of changes it
  offers a Windows restore point.
- **Preview first.** The big actions show the full plan (and what is left out) before you confirm, and Boost has a simulation switch.
- **No data about your PC leaves your PC.** The only network traffic is the connection you ask for (winget installs, the speed
  test) and a read-only check for new versions of this program. See [PRIVACY.md](PRIVACY.md).
- **Signed updates.** The list of versions is signed with a private key that never leaves the developer's computer. The app
  checks the signature, the file size and the SHA-256 of the installer before it opens it, and refuses anything that does not
  match, even if this repository were tampered with.
- **Security reviewed.** See [SECURITY.md](SECURITY.md) for how to report a problem.

## Install

1. Open [Releases](../../releases/latest) and download `SkontzControlSystem-Setup-<version>.exe`.
2. Run it. The installer is in **English by default** and also offers **Português (Brasil)**.
3. Windows SmartScreen may warn that the publisher is unknown, because the installer does not carry a paid code-signing
   certificate yet. Choose *More info* > *Run anyway* only if you downloaded the file from this page.
4. The app asks for administrator permission when it opens: many tweaks change system-wide settings.

To double-check a download, compare its hash with the one in the release's `latest.json`:

```powershell
Get-FileHash .\SkontzControlSystem-Setup-<version>.exe -Algorithm SHA256
```

## Updates

Open **Settings > Updates** (or watch for the banner at the top of the window). The app tells you what changed in the new
version (security, new features, improvements, fixes) and installs it for you after you confirm. Your settings and history are
kept.

## Languages

English (default) and Português (Brasil). Change it any time from the language button in the sidebar; the app restarts to
apply it. More languages are planned, Spanish first.

## Requirements

Windows 10 (version 1809 or later) or Windows 11, 64-bit, and administrator rights.

## Found a problem?

Use **Settings > Export report** to create a small `.zip` with the app version, your Windows version and the errors the app
logged (your user name and computer name are removed). Send it to the maintainer. Nothing is sent unless you do it yourself
or opt in to error reports in a future version.

For **security** problems, do not open a public issue: read [SECURITY.md](SECURITY.md).
