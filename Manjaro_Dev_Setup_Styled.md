# 🦇 **Manjaro GNOME Development Machine Setup Guide**
_A fully themed Dracula-powered developer environment for Mac Mini (2012)_

---

## 🧾 **Table of Contents**
- [Prerequisites](#prerequisites)
- [💿 Phase 1: Base Installation](#-phase-1-base-installation)
- [💾 Phase 2: TimeMachine-Style Backup System](#-phase-2-timemachine-style-backup-system)
- [🔐 Phase 3: Setup SSH](#-phase-3-setup-ssh)
- [⚙️ Phase 4: Base Configuration](#%EF%B8%8F-phase-4-base-configuration)
- [🧛 Phase 5: Terminal Setup and Theming](#-phase-5-terminal-setup-and-theming)
- [🖥️ Phase 6: X11 Configuration](#%EF%B8%8F-phase-6-x11-configuration)
- [🎨 Phase 7: GNOME Theming](#-phase-7-gnome-theming)
- [🧰 Phase 8: Development Tools Installation](#-phase-8-development-tools-installation)
- [🧠 Phase 9: Code Editors Setup](#-phase-9-code-editors-setup)
- [🚀 Phase 10: Final Configuration and Optimization](#-phase-10-final-configuration-and-optimization)
- [🧪 Phase 11: Verification and Testing](#-phase-11-verification-and-testing)
- [🩹 Troubleshooting](#-troubleshooting)
- [🏁 Next Steps](#-next-steps)

---

## 🧰 **Prerequisites**

✅ **Before you begin, make sure you have:**
- Mac Mini 2012 with SSD
- Pre-created partition for Linux installation
- Manjaro GNOME ISO downloaded
- USB drive for installation media

---

## 💿 **Phase 1: Base Installation**
> **Goal:** Install and configure Manjaro GNOME with a BTRFS filesystem and minimal base tools.

### 1.1 Create Installation Media
```bash
# On macOS (if needed)
sudo dd if=manjaro-gnome-*.iso of=/dev/diskX bs=1m status=progress
```
...
