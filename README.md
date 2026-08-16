# Awesome Miyoo Mini [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

Curated software, tooling, and documentation for the Miyoo Mini family of handhelds.

**Scope:** Miyoo Mini (v1–v4), Mini Plus, and Mini Flip.

## Contents

- [Custom Firmware](#custom-firmware)
- [Installers](#installers)
- [Apps & Paks](#apps--paks)
  - [Onion](#onion)
  - [MinUI / NextUI](#minui--nextui)
- [Emulators](#emulators)
- [Ports & Homebrew](#ports--homebrew)
- [Development](#development)
- [Hardware & SoC](#hardware--soc)
- [Community](#community)

## Custom Firmware

- [Onion](https://github.com/OnionUI/Onion) — The default recommendation. Full OS overhaul: 100+ emulators, game switcher, auto-resume, activity tracker, themes, OTA updates. Heaviest and most featureful.
- [MinUI](https://github.com/shauninman/MinUI) — Deliberately minimal launcher and libretro frontend. No box art, no themes, no music. Multi-device (Miyoo, Trimui, RG35XX, MagicX) on one card.
- [NextUI](https://github.com/LoveRetro/NextUI) — MinUI fork that keeps the philosophy but adds box art, better menus, a pak store, and an in-device updater. Currently the more actively developed of the two.
- [spruceOS](https://github.com/spruceUI/spruceOS) — Python-based themeable UI aiming between Onion's density and MinUI's austerity. Game switcher, autosave/autoresume, RetroAchievements, SSH/SFTP, Syncthing, Samba, RTC-over-WiFi sync.
- [Koriki](https://github.com/Rparadise-Team/Koriki) — SimpleMenu frontend over stock firmware. Single card auto-detects v1–v4/Plus/Flip; multi-resolution, netplay, RetroArch overlay manager, WebDAV save sync.
- [MyMinUI](https://github.com/Turro75/MyMinUI) — MinUI fork with a rewritten NEON multicore rendering engine, cheats, save-state slot previews with screenshots, extra aspect ratios, and a debug HUD (per-core CPU load, freq, temp).
- [sprigUI](https://github.com/spruceUI/sprigUI) — Minimal spruceOS for the Mini Flip.
- [Allium](https://github.com/goweiwen/Allium) — A custom launcher for the Miyoo Mini/Plus/Flip, designed to replace the stock MainUI with a faster and more user-friendly UI.

## Apps & Paks

Pak formats are not interchangeable between firmwares. Split accordingly.

### Onion

The [community apps index](https://onionui.github.io/docs/community-apps) is the upstream source for most of these; several require the Plus's WiFi.

- [Better WiFi Tools](https://github.com/XK9274/better-wifi-miyoo) — Replacement WiFi management for the Plus.
- [Cloud Saves](https://github.com/hotcereal/cloud-saves-miyoo-mini-plus) — rclone-backed save upload/download.
- [Syncthing](https://github.com/XK9274/syncthing-app-miyoo) — Syncthing injected into Onion's `runtime.sh`.
- [Screen Capture Toolkit](https://github.com/XK9274/screencap-toolkit-miyoo) — Twitch / RTMP / VNC / file output.
- [VNC Server](https://github.com/XK9274/vncserver-miyoo) — Remote framebuffer access.
- [Spotify Client](https://github.com/XK9274/ncspotcli-compile-miyoo) — ncspot build with app folder.
- [Time Quick Fix](https://github.com/hotcereal/time-quick-fix) — NTP + Cloudflare clock fix, for the clockless base Mini.
- [Speed Test](https://github.com/josegonzalez/miyoo-speedtest) — On-device bandwidth test.
- [Wthr](https://github.com/trashplusplus/wthr) — Weather forecast app in Go.
- [Lynx](https://github.com/tailtwo/lynx-miyoo) — Terminal web browser.
- [WiFi Password Saver](https://github.com/funkykovalski/WIFI) — Persists WiFi credentials.
- [Bible.sh](https://github.com/likeich/bible-sh) — KJV reader.
- [Terminal](https://github.com/OnionUI/app-Terminal) — On-device shell.
- [Search/Filter](https://github.com/OnionUI/SearchFilter) — Global game search for MainUI.

### MinUI / NextUI

- [Pakman](https://github.com/josegonzalez/pakman) — Auto-generated pak collection covering miyoomini, my282, my355, rg35xxplus, tg5040. The single highest-value entry for MinUI users.
- [NextUI Pak Store](https://github.com/UncleJunVIP/nextui-pak-store) — On-device pak browser and installer, bundled with NextUI.
- [adjLCD](https://github.com/DesiQuintans/adjLCD) — Tool paks for LCD luma and a 5-level blue light filter, persisted across reboots via `auto.sh`.
- [ClearRecent](https://github.com/DesiQuintans/ClearRecent) — Edit or wipe the Recently Played list.
- [minUI_additions](https://github.com/dleicht/minUI_additions) — Extra emulator paks, notably packaging steward-fu's DraStic as an NDS pak.

## Emulators

- [steward-fu/nds](https://github.com/steward-fu/nds) — The DraStic NDS port. Heavily customized SDL2 + ALSA with hooking points into a specific DraStic build; requires the exact documented binary version.
- [RetroArch-patch](https://github.com/OnionUI/RetroArch-patch) — Onion's RetroArch fork with a custom display driver.

## Ports & Homebrew

- [OnionUI/Ports-Collection](https://github.com/OnionUI/Ports-Collection) — Official native ports repository.

## Development

- [steward-fu/sdl2](https://github.com/steward-fu/sdl2) — SDL2 for Mini/Plus using MI\_GFX for rendering, with SwiftShader providing `libEGL`/`libGLESv2`. Docker build path included. Start here if you're porting anything graphical.
- [union-toolchain](https://github.com/MiyooMini/union-toolchain) — Dockerized toolchain; the community baseline.
- [miyoo-toolchain](https://github.com/MiyooMini/miyoo-toolchain) — Vendor-adjacent cross-compilation toolchain.
- [dev-miyoomini-toolchain](https://github.com/OnionUI/dev-miyoomini-toolchain) — Onion's build environment.
- [Miyoo Mini SDK org](https://github.com/MiyooMini) — Vendor SDK, firmware backups, language packs, sample SDL apps (sdl2048, SDL Pal).
- [tGecko/miyoo-mini](https://github.com/tGecko/miyoo-mini) — Firmware image scripts: unpack the three squashfs partitions from `miyoo***_fw.img`, edit, repack in place. Also carves out `lcd_init`.
- [steward-fu/website](https://github.com/steward-fu/website) — Prebuilt toolchain tarballs referenced by most of the above.

## Hardware & SoC

- SSD202D: dual Cortex-A7 @ 1.2 GHz, 128 MB DDR3, 16 MB SPI ROM, MI_GFX 2D engine, no 3D GPU.
- Display: 640×480 IPS — 2.8" on the Mini, 3.5" on the Plus. Newer v4 units and the Flip ship a 752×560 panel.
- RTC: absent on the base Mini and early Plus units; present on later Plus revisions. Common mod otherwise.
- WiFi: Plus only. No Bluetooth on any model.
- Battery: 1900 mAh (v1) / 2000 mAh (v2) Mini; ~3000 mAh Plus.

## Community

- [Onion Discord](https://discord.gg/Jd2azKX)
- [r/MiyooMini](https://reddit.com/r/miyoomini)
- [r/SBCGaming](https://www.reddit.com/r/SBCGaming/)
- [Onion docs](https://onionui.github.io/docs) · [wiki](https://github.com/OnionUI/Onion/wiki) · [discussions](https://github.com/OnionUI/Onion/discussions)
- [NextUI docs](https://nextui.loveretro.games/docs/)
- [Koriki wiki](https://github.com/Rparadise-Team/Koriki/wiki)
- [spruceOS wiki](https://github.com/spruceUI/spruceOS/wiki)
