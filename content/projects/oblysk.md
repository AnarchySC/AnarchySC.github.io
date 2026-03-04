---
title: "Oblysk"
description: "Smart clipboard manager for virtual consoles, remote sessions, and power users."
weight: 4
icon: "&#9670;"
status: "released"
tech: ["Electron", "JavaScript", "Cross-platform"]
github: "https://github.com/AnarchySC/oblysk"
demo: "https://github.com/AnarchySC/oblysk/releases"
cta_url: "https://github.com/AnarchySC/oblysk/releases/latest"
cta_label: "Download Latest"
support_url: "https://ko-fi.com/cassettefuture"
---

## The Problem

Copy-paste is broken in virtual consoles. VMware vSphere web consoles, iDRAC sessions, AWS CloudShell, corporate VDI — the clipboard fails exactly when you need it most. You end up manually typing long commands, passwords, and connection strings into remote terminals.

Oblysk fixes this.

## How It Works

A **9-cell grid** stores your most-used text snippets — commands, credentials, connection strings, anything. Each cell is bound to a **global hotkey** that works everywhere, including environments where standard clipboard operations fail.

Store once. Paste anywhere. `Ctrl+Alt+1` through `Ctrl+Alt+9`.

<div class="feature-grid">
  <div class="feature-card">
    <h4>Grid Interface</h4>
    <p>9-cell visual grid. Double-click to edit. Persistent storage survives restarts.</p>
  </div>
  <div class="feature-card">
    <h4>22+ Global Hotkeys</h4>
    <p>System-wide shortcuts that work in virtual consoles, web terminals, and locked-down environments.</p>
  </div>
  <div class="feature-card">
    <h4>AES-256 Encryption</h4>
    <p>Master password protection with PBKDF2 hashing (100k iterations). Your data stays encrypted at rest.</p>
  </div>
  <div class="feature-card">
    <h4>Zero Cloud</h4>
    <p>No telemetry. No cloud sync. No accounts. Everything stays local on your machine.</p>
  </div>
</div>

## Built For

- **VMware vSphere / ESXi** web consoles
- **iDRAC / iLO / IPMI** management interfaces
- **AWS CloudShell** and cloud terminals
- **Corporate VDI** environments
- **SSH terminals** and command prompts
- **Secure environments** where clipboard access is restricted

## Hotkeys

<div class="hotkey-grid">
  <div class="hotkey"><kbd>Ctrl+Alt+1-9</kbd> <span>Paste grid cells</span></div>
  <div class="hotkey"><kbd>Ctrl+Alt+O</kbd> <span>Toggle window</span></div>
  <div class="hotkey"><kbd>Ctrl+Alt+C</kbd> <span>Copy to notepad</span></div>
  <div class="hotkey"><kbd>Ctrl+Alt+V</kbd> <span>Paste on-deck</span></div>
  <div class="hotkey"><kbd>Ctrl+Alt+R</kbd> <span>Reverse copy</span></div>
  <div class="hotkey"><kbd>Ctrl+Shift+D</kbd> <span>Debug export</span></div>
</div>

On macOS, use `Cmd+Alt` instead of `Ctrl+Alt`.

## Security

Your stored data is encrypted with **AES-256-GCM**. The encryption key is derived from your master password via **PBKDF2** with 100,000 iterations and per-password salts. The plaintext password is never stored in memory — key derivation happens through the Web Crypto API.

- **Auto-lock** after configurable inactivity
- **Content Security Policy** blocks all external scripts and connections
- **Open source** — audit the code yourself

## Platform Support

<div class="platform-row">
  <span class="platform-badge">Windows 10+</span>
  <span class="platform-badge">Ubuntu 20.04+</span>
  <span class="platform-badge">Fedora 36+</span>
  <span class="platform-badge">macOS 11+</span>
</div>

| Platform | Paste Method | Clipboard |
|----------|-------------|-----------|
| Windows | PowerShell SendKeys | Built-in |
| Linux (X11) | xdotool | xclip |
| Linux (Wayland) | wtype | wl-clipboard |
| macOS | osascript | Built-in |

### Linux Dependencies

**X11:** `sudo apt install xdotool xclip`
**Wayland:** `sudo apt install wtype wl-clipboard`

## Quick Start

1. **Download** the portable executable or installer from [GitHub Releases](https://github.com/AnarchySC/oblysk/releases/latest)
2. **Run** — no installation required for the portable version
3. **Set** your master password when prompted
4. **Store** commands and credentials in grid cells (double-click to edit)
5. **Paste anywhere** with `Ctrl+Alt+1` through `Ctrl+Alt+9`

## Open Source

Oblysk is MIT licensed. Fork it, modify it, build on it. Contributions welcome.

[View on GitHub](https://github.com/AnarchySC/oblysk) · [Report Issues](https://github.com/AnarchySC/oblysk/issues) · [Support Development](https://ko-fi.com/cassettefuture)
