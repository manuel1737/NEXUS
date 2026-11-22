# NEXUS OS Creator Edition 1.0 — Build Kit

This is a reproducible **Debian Live Build project**, not a prebuilt ISO.
It builds a bootable 64-bit live/installable environment with an XFCE desktop,
a NEXUS launcher/dashboard, and a starter set of game-development tools.

## Build host
Use a Debian 13 (trixie) 64-bit machine or VM with internet access and at least
25 GB free disk space. Building an ISO requires downloading Debian packages.
The resulting ISO size depends on package versions and firmware; the 1–4 GB
target is an estimate, not a guarantee.

## Build
From this directory, run:

```bash
sudo apt update
sudo apt install -y live-build
sudo lb config
sudo lb build
```

The resulting ISO will be named similar to `live-image-amd64.hybrid.iso`.
It supports BIOS and UEFI boot through Debian Live Build's standard hybrid image
configuration. Test it in a virtual machine before installing it on hardware.

## What's included
- Debian 13 base, XFCE desktop and LightDM
- Firefox ESR
- Godot, Blender, Kdenlive and common developer tools (where available in Debian)
- Mesa Vulkan drivers and common firmware packages
- NEXUS offline dashboard and launcher

## Important limitations
- NEXUS Studio is currently a launchpad/dashboard, not a custom game engine.
  Godot and Blender are independent applications included as tools.
- NEXUS Publish is currently a local prototype screen. A real private store
  requires a separately hosted server, user accounts, secure authentication,
  storage, backups and access-control rules. Do not expose a test server to the
  public internet.
- Hardware support varies. NVIDIA proprietary drivers may need to be installed
  separately for the exact GPU and kernel.
- This project does not contain games.

## Customization
Edit `config/package-lists/nexus.list.chroot` to add/remove packages.
Edit `config/includes.chroot/usr/share/nexus/index.html` to customize the dashboard.
