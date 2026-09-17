# ft-drivermesa

**English** | [Bahasa Indonesia](README_ID.md)

Experimental Mesa/Crocus work targeting a specific Intel GPU configuration.

> Created by **ft_aska.90**
>
> **WARNING:** This project is still under active development and is **not recommended for normal/daily use**.

## Target Hardware

This repository is intended for:

- GPU: **Intel HD Graphics 3000**
- Architecture: **Sandy Bridge / SNB GT2**
- PCI ID: **8086:0116**
- Driver family: **Mesa Crocus**
- Primary environment: **Linux / X11**

## Development / Tested Environment

- Laptop: **Toshiba Satellite L735 (PSK0AL-010004)**
- CPU: **Intel Core i3-2350M @ 2.30 GHz**
- GPU: **Intel HD Graphics 3000 / Sandy Bridge GT2**
- GPU PCI ID: **8086:0116**
- RAM: **3.76 GiB**
- OS: **CachyOS x86_64**
- Development kernel: **Linux 7.1.8-1-cachyos**
- Desktop Environment: **Xfce 4.20**
- Window Manager: **Xfwm4**
- Display Server: **X11**
- Graphics stack: **Mesa 26.1.6 / Crocus / i915**

## Compatibility Warning

**Do not blindly install or apply these patches/builds on a different device.**

Only test this project if your GPU, PCI ID, hardware generation, Mesa driver, kernel graphics driver, and environment are the same or genuinely compatible. A similar marketing name does not guarantee the same generation, PCI ID, or driver path.

Before testing, verify at minimum:

```bash
lspci -nn | grep -Ei 'vga|display|3d'
glxinfo -B
uname -a
```

The expected target is Intel HD Graphics 3000 / Sandy Bridge GT2 with the matching PCI ID and a compatible Mesa/Crocus stack.

## Development Status

**Experimental / in development.**

Possible risks include:

- graphical corruption or rendering glitches;
- application/game crashes;
- X11 session instability;
- regressions after Mesa/kernel updates;
- worse performance than the distribution driver;
- graphical applications failing to start after an incorrect installation.

Prefer a side-by-side custom build or an isolated prefix. Avoid replacing distribution Mesa packages directly unless you know how to recover through a TTY and package manager.

## Recovery Preparation

Before testing:

1. keep the distribution Mesa packages available and know how to restore them;
2. back up modified source/configuration;
3. test custom builds through environment variables or an isolated prefix first;
4. record the Mesa version/commit, kernel, GPU PCI ID, and build flags for every test.

## Repository Layout

- `patches/` — Mesa/Crocus patches.
- `scripts/` — build, launch, benchmark, or rollback helpers.
- `docs/` — hardware notes, test results, and development documentation.

## License

Original work by **ft_aska.90** is licensed under the **MIT License** unless a file states otherwise.

Mesa source code and upstream-derived files retain their original upstream copyright and license notices. Do not remove upstream attribution.

See `LICENSE` and `THIRD_PARTY_NOTICES.md`.
