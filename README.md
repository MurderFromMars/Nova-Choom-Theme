# Nova-Choom — Neon Red Plasma Theme

**Nova-Choom** is a neon-red, cyberpunk-inspired theme for **KDE Plasma 6** that transforms Plasma into a futuristic, dynamic tiling window manager (TWM) setup with high-contrast crimson visuals and productivity-focused workflow enhancements.

Nova-Choom integrates advanced visual effects, KWin scripts, and curated configurations to deliver a fully immersive neon desktop experience — built around a `#fb1010` accent that sets it apart from the magenta-leaning CyberXero lineage.

![Nova-Choom Desktop Overview](screenshot1.png)
![Nova-Choom Desktop Overview](screenshot2.png)
![Nova-Choom Desktop Overview](screenshot3.png)

---

## Quick Install

The easiest way to install Nova-Choom on your system:
```bash
curl -fsSL https://raw.githubusercontent.com/MurderFromMars/Nova-Choom/main/install.sh | bash
```

This command downloads the installer and deploys the full Nova-Choom environment automatically.

---

## Features

**Visual Enhancements:**
- Neon red color scheme (`NovaChoom.colors`) with `#fb1010` accent
- YAMIS icon theme
- Modern Clock Plasma widget
- Custom wallpapers and icons

**Window Management:**
- **Krohnkite:** dynamic tiling KWin script
- **Kyanite:** true GNOME-style dynamic workspace management for Plasma 6, authored by me
- Plasma panel colorizer
- Kurve Cava powered audio visualizer for KDE Panels
- KDE Rounded Corners custom window rounding and shadow/border effects
- Better Blur DX for blur effects on transparent windows

**Configuration Management:**
- Automatic backup of your configuration files
- Deployment of preconfigured Plasma and KWin configuration files including btop, kitty, fastfetch, and cava configurations
- Auto rebuild system for KDE Rounded Corners and Better Blur DX after KWin updates

**Advanced Automation:**
- Removes existing Plasma panels safely during deployment
- Applies Breeze window decoration automatically
- Sets wallpapers programmatically (via `plasma-apply-wallpaperimage` or JavaScript fallback)
- Auto-patches the desktop activity ID so wallpaper containment binds correctly on any system
- Reconfigures KWin automatically after changes

---

## Supported Platforms

- **Arch / Arch-based**
- **Debian / Ubuntu-based**
- **Fedora-based**
- **Other distributions** — Not officially supported

**Requirements:**
- KDE Plasma 6.x
- Bash shell
- Active Plasma session
- Internet connectivity
- Sudo privileges
- Wayland only

---

## Technology Highlights

- **Bash Automation:** orchestrates builds, configuration, and deployment
- **KDE JavaScript Integration:**
  Nova-Choom uses inline JavaScript via `qdbus6` to:
  - Remove live Plasma panels
  - Set wallpapers programmatically
  - Interact with KDE Plasma APIs directly

- **Source Builds:**
  Components like `KDE Rounded Corners`, `Better Blur DX`, `Kurve`, and `Plasma Panel Colorizer` are built from source for performance and stability.

- **Auto Rebuild Hooks for KWin Effects:**
  Nova-Choom ensures compatibility after KWin updates:
  - **Arch:** pacman hook executes `/usr/local/bin/rebuild-kwin-effects.sh` post-kwin upgrade
  - **Debian/Ubuntu:** APT post-invoke hook triggers rebuild if kwin packages were updated
  - **Fedora:** dnf post-transaction action runs the rebuild on kwin install/update

---

## Installation Details

Nova-Choom performs the following phases automatically:

### Phase 1: System Preparation
- Clone or update the Nova-Choom repository
- Detect Linux distribution
- Install system dependencies (Arch, Debian, or Fedora-based)

### Phase 2: Building Core Components
- Compile Plasma Panel Colorizer, Kurve, KDE Rounded Corners, and Better Blur DX
- Set up auto-rebuild scripts and package-manager hooks

### Phase 3: Theme Deployment
- Stop PlasmaShell and remove old panels
- Deploy icons, wallpapers, color schemes, and widgets
- Apply preconfigured Plasma and KWin configuration files
- Patch desktop activity ID to match the target system
- Set active wallpaper
- Activate KWin scripts:
  - **Krohnkite:** dynamic tiling
  - **Kyanite:** true GNOME-style dynamic workspace management, fully dynamic and adaptable to your workflow
- Enforce Breeze window decoration
- Apply `#fb1010` accent color and YAMIS icon theme
- Reconfigure KWin and restart PlasmaShell

---

## Backup Strategy

All modified files are backed up to:
```
~/NovaChoom-backup-YYYYMMDD_HHMMSS
```

This allows you to restore previous configurations manually if needed.

---

## Post-Installation

- **Logout or reboot** is required to fully apply all theme and script changes.
- The installer will indicate when this step is necessary.

---

## Maintenance

- Automatic rebuild hooks ensure KDE Rounded Corners and Better Blur DX remain compatible after KWin updates:
  - Arch: pacman hook
  - Debian/Ubuntu: APT post-invoke hook
  - Fedora: dnf post-transaction action
- Rebuild logs are saved at:
```
/var/log/kde-rounded-corners-rebuild.log
/var/log/better-blur-dx-rebuild.log
```

---

## Audience

**Intended for:**
- KDE Plasma 6 enthusiasts
- Users seeking a cyberpunk dynamic tiling workflow with a bold red palette
- Anyone on supported Linux distributions who wants a futuristic dynamic TWM desktop with the creature comforts of Plasma

---

## License

Nova-Choom is distributed under the MIT license. All projects built by, or included in, the script retain their original licensing.
