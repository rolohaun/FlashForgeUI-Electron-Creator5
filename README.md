<div align="center">

<img width="48" height="48" alt="icon" src="https://github.com/user-attachments/assets/6f187987-027f-4b66-a4e4-3bc30be4ca90" />

# FlashForgeUI

**A modern, open-source desktop and mobile interface for FlashForge 3D printers**

## Creator 5 Compatibility Fork

This public repository is an unofficial compatibility fork of
[Parallel-7/FlashForgeUI-Electron](https://github.com/Parallel-7/FlashForgeUI-Electron).
All original project credit goes to the upstream owner and contributors.

This fork exists only to preserve the local modifications made to support the
FlashForge Creator 5, which behaves like an AD5X-class printer. The changes add
Creator 5 detection/pairing behavior, use the AD5X/IFS material-station flow,
and avoid legacy TCP probing when the printer only accepts the authenticated
modern HTTP API.

![Platforms](https://img.shields.io/badge/Platforms-Win%20%7C%20macOS%20%7C%20Linux-3178c6?style=flat)
![Downloads](https://img.shields.io/github/downloads/Parallel-7/FlashForgeUI-Electron/total?style=flat&color=brightgreen)
![Version](https://img.shields.io/badge/Version-1.0.4--alpha.4-orange?style=flat)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat)

**Monitor and control your printer from your desktop or any device on your network &mdash; with more features than any official FlashForge software, completely free.**

</div>

<div align="center">

| Get Started | |
| --- | --- |
| **[Creator 5 Fork Releases](https://github.com/rolohaun/FlashForgeUI-Electron-Creator5/releases)** | Use these builds for Creator 5 support when release assets are available |
| **[Original Project Releases](https://github.com/Parallel-7/FlashForgeUI-Electron/releases)** | Upstream builds from the original project |
| **[User Guide & Wiki](https://github.com/Parallel-7/FlashForgeUI-Electron/wiki)** | Upstream setup, pairing, and feature walkthroughs |

</div>

## Overview

FlashForgeUI connects directly to your FlashForge printer over your local network &mdash; no cloud account required. Watch live camera and temperature data, start and manage prints, control LEDs and filtration, and keep an eye on multiple printers at once. When you're away from your desk, the built-in WebUI gives you the same control from your phone or any browser, and headless mode lets you run it as a lightweight always-on server.

It works with everything from the latest Adventurer 5M / 5M Pro / AD5X to older legacy models, automatically picking the right way to talk to each printer.

<div align="center">

## How It Compares

| Feature | FlashForgeUI | OrcaSlicer | Orca-FlashForge | FlashPrint |
| --- | --- | --- | --- | --- |
| **Open Source** | Yes | Yes | No | No |
| **Cross-Platform** | Yes | Yes | Yes | Yes |
| **Full Printer Control** | Yes | No | No | No |
| **Mobile / Remote Access** | Yes (WebUI) | No | No | No |
| **Multi-Printer Management** | Yes | No | No | No |
| **Camera Preview** | Yes | Yes | Yes | Yes |
| **Headless / Server Mode** | Yes | No | No | No |
| **Spoolman Integration** | Yes | No | No | No |
| **Discord Notifications** | Yes | No | No | No |
| **Preview File Metadata** | Full | Limited | Limited | No |

</div>

<div align="center">

## Features

| Capability | What You Get |
| --- | --- |
| **Live Monitoring** | Real-time status, temperatures, progress, layer count, and ETA &mdash; updated every few seconds |
| **Full Print Control** | Start, pause, resume, and cancel jobs • upload `.gcode` / `.gx` / `.3mf` files • browse recent and local jobs with thumbnail previews |
| **[Camera Streaming](https://github.com/Parallel-7/FlashForgeUI-Electron/wiki/Custom-Camera-Setup)** | Auto-detected OEM cameras plus custom RTSP/HTTP sources • watch from multiple devices at once |
| **[Multi-Printer Management](https://github.com/Parallel-7/FlashForgeUI-Electron/wiki/Connecting-to-Multiple-Printers)** | Connect to several printers concurrently • tabbed desktop UI and dropdown WebUI selector • independent per-printer settings |
| **[Remote Access (WebUI)](https://github.com/Parallel-7/FlashForgeUI-Electron/wiki/WebUI-Setup)** | Password-protected, mobile-friendly web interface with full feature parity to the desktop app |
| **[Headless Mode](https://github.com/Parallel-7/FlashForgeUI-Electron/wiki/Headless-Mode)** | Run as a server with no desktop UI &mdash; ideal for a Raspberry Pi or always-on machine |
| **[Spoolman Integration](https://github.com/Parallel-7/FlashForgeUI-Electron/wiki/Spoolman-Integration)** | Track filament usage automatically and assign spools per printer |
| **[Notifications](https://github.com/Parallel-7/FlashForgeUI-Electron/wiki/Notifications)** | Desktop and Discord alerts for print completion, cooldown, and more |
| **Hardware Controls** | Temperature, LED, and filtration control • axis homing • clear platform • direct command terminal |
| **[Customizable UI](https://github.com/Parallel-7/FlashForgeUI-Electron/wiki/Customizing-the-Desktop-UI)** | Drag-and-drop layouts, light/dark themes, and custom color palettes on both desktop and WebUI |

</div>

<div align="center">

## Supported Printers

| Printer | Support | Material Station | Notes |
| --- | --- | --- | --- |
| **Creator 5** | Full | Yes (4 slots) | AD5X-compatible IFS flow |
| **AD5X** | Full | Yes (4 slots) | Multi-material 3MF printing |
| **Adventurer 5M Pro** | Full | No | Includes filtration control |
| **Adventurer 5M** | Full | No | |
| **Adventurer 3 / 4** | Full | No | Legacy API |
| **Older Models** | Legacy Mode | No | Untested, basic control |

**Newer printers (5M series and up) require LAN-only mode and a one-time pairing code &mdash; see [Pairing Your Printer](https://github.com/Parallel-7/FlashForgeUI-Electron/wiki/1.-Pairing-your-printer).**

</div>

<div align="center">

## Quick Start

| Step | Instructions |
| --- | --- |
| **1. Download or build** | Check the [Creator 5 fork releases](https://github.com/rolohaun/FlashForgeUI-Electron-Creator5/releases). If no packaged release is available yet, build from source using the steps below. |
| **2. Install on Windows** | Installer builds are named `FlashForgeUI-Setup-<version>.exe`. Run the installer from your Downloads folder or from `dist\` after a local build. By default, the installed app is `C:\Users\<you>\AppData\Local\Programs\FlashForgeUI\FlashForgeUI.exe` unless you choose a different install folder. The installer also creates Start Menu and desktop shortcuts. |
| **3. Use portable Windows build** | Portable builds are standalone `.exe` files in the release assets or in `dist\` after `pnpm build:win`. They do not need installation; run the portable `.exe` from the folder where you downloaded or built it. |
| **4. Install on macOS or Linux** | macOS uses the `.dmg`: open it and drag `FlashForgeUI` into Applications. Linux uses the `.AppImage`, `.deb`, or `.rpm` package from the release assets or from `dist\` after a local build. |
| **5. Connect printer** | Launch the app, use auto-discovery or enter your printer's IP, and add the [pairing code](https://github.com/Parallel-7/FlashForgeUI-Electron/wiki/1.-Pairing-your-printer) if prompted. Creator 5 should use the AD5X-compatible pairing and IFS flow in this fork. |
| **6. Configure optional features** | Optional: set up [remote access](https://github.com/Parallel-7/FlashForgeUI-Electron/wiki/WebUI-Setup), [Discord alerts](https://github.com/Parallel-7/FlashForgeUI-Electron/wiki/Notifications), [Spoolman](https://github.com/Parallel-7/FlashForgeUI-Electron/wiki/Spoolman-Integration), and [custom cameras](https://github.com/Parallel-7/FlashForgeUI-Electron/wiki/Custom-Camera-Setup). |

Full setup walkthroughs and troubleshooting live in the **[Wiki](https://github.com/Parallel-7/FlashForgeUI-Electron/wiki)**.

</div>

<div align="center">

## Building from Source

</div>

This project uses [pnpm](https://pnpm.io/). Install Node.js LTS first, then enable pnpm:

```powershell
corepack enable
corepack prepare pnpm@10.23.0 --activate
```

Clone and run the app without creating an installer:

```powershell
git clone https://github.com/rolohaun/FlashForgeUI-Electron-Creator5.git
cd FlashForgeUI-Electron-Creator5
pnpm install
pnpm build
pnpm start
```

`pnpm start` launches the built Electron app directly from the project folder. It does not create an installed `.exe`.

Create installable packages:

```powershell
pnpm build:win    # Windows installer and portable .exe in dist\
pnpm build:mac    # macOS .dmg and .zip artifacts in dist\
pnpm build:linux  # Linux .AppImage, .deb, and .rpm artifacts in dist\
```

After `pnpm build:win`, look in `dist\` for:

```text
dist\FlashForgeUI-Setup-<version>.exe  # Windows installer
dist\<another FlashForgeUI .exe>       # portable executable; it is the .exe that is not the -Setup installer
```

After running the Windows installer, the default installed executable is:

```text
C:\Users\<you>\AppData\Local\Programs\FlashForgeUI\FlashForgeUI.exe
```

For active development with hot reload:

```powershell
pnpm dev
```

<div align="center">

![Electron](https://img.shields.io/badge/Electron-39.8.10-47848f?style=flat&logo=electron)
![TypeScript](https://img.shields.io/badge/TypeScript-5.9.3-3178c6?style=flat&logo=typescript)
![Vite](https://img.shields.io/badge/Vite-7.3.2-646cff?style=flat&logo=vite)
![Express](https://img.shields.io/badge/Express-5.2.1-000000?style=flat&logo=express)

## License

MIT License &mdash; Copyright (c) 2025 GhostTypes

</div>
