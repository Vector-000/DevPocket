# DevPocket
DevPocket is a portable, encrypted development environment that runs from a USB drive without rebooting or permanent host setup. It launches a consistent Linux VM, mounts your workspace, and provisions tools from a declarative manifest; ensuring the same environment on Windows, macOS, and Linux.

Why DevPocket?

Identical dev environment everywhere. Entire workspace lives on USB. Encrypted secrets vault. Declarative tool provisioning (manifest.yaml). Browser-based IDE (code-server). Hardware acceleration when available

Built to eliminate:

“Works on my machine”. Host dependency conflicts. Setup time during interviews / hackathons

Quick Start: Plug in USB. Run launcher.

Windows → devpocket.exe

macOS → ./devpocket-macos

Linux → ./devpocket-linux

Browser opens to full development environment

No reboot. No permanent host install.

Architecture Overview:
Host OS (Windows/macOS/Linux)
        │
        ▼
DevPocket Launcher
        │
        ▼
QEMU Linux VM (on USB)
        │
        ├── Mounts /workspace (USB)
        ├── Reads manifest.yaml
        ├── Provisions tools
        └── Starts code-server

The host OS is abstracted away entirely.

Security Model: Encrypted secrets/ directory. Vault unlock on launch. No plaintext token storage in workspace. USB loss is assumed possible — encryption is mandatory.

Use Cases: Interviews. Hackathons. Workshops. Secure travel dev setup. Offline development.

Tech Stack

Launcher: Go / Rust

Virtualization: QEMU

Guest OS: Minimal Ubuntu/Debian

Provisioning: Bash + apt (MVP)

IDE: code-server

