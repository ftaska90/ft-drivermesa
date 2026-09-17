# ft-drivermesa

Experimental Mesa/Crocus graphics-driver work for a **specific Intel GPU target**.

> Created by **ft_aska.90**
>
> **WARNING:** This project is still under active development and is **not recommended for normal/daily use**.

## Target hardware

This repository is intended for the following graphics hardware/configuration:

- GPU: **Intel HD Graphics 3000**
- Architecture: **Sandy Bridge / SNB GT2**
- PCI ID: **8086:0116**
- Driver family: **Mesa Crocus**
- Primary environment: Linux / X11

## Important compatibility warning

Do **not** blindly install or apply these changes on another machine.

Only test this project if your graphics hardware and driver stack match the target above. Even hardware with a similar marketing name may use a different generation, PCI ID, kernel stack, or Mesa path.

Before trying it, verify at minimum:

```bash
lspci -nn | grep -Ei 'vga|display|3d'
glxinfo -B
uname -a
```

The expected GPU should identify as Intel HD Graphics 3000 / Sandy Bridge GT2, with the intended PCI ID and a compatible Mesa/Crocus stack.

## Development status

**Experimental / in development.**

Possible risks include:

- graphical corruption or rendering glitches;
- application/game crashes;
- X11 session instability;
- regressions after a Mesa/kernel update;
- worse performance than the distribution driver;
- failure to start graphical applications if installed incorrectly.

Use a side-by-side/custom Mesa build whenever possible. Avoid replacing your distribution Mesa packages directly unless you know how to recover from a broken graphics stack.

## Recommended recovery preparation

Before testing:

1. Keep the distribution Mesa packages installed and know how to restore them from a TTY.
2. Keep a backup of any modified source/configuration.
3. Test custom builds through environment variables or an isolated prefix first.
4. Record the exact Mesa commit/version, kernel, GPU PCI ID, and build flags used for each benchmark.

## Repository layout

- `patches/` — Mesa/Crocus patches.
- `scripts/` — build, launch, benchmark, or rollback helpers.
- `docs/` — hardware notes, results, and development documentation.

## Licensing

Original work in this repository by **ft_aska.90** is released under the MIT License unless a file states otherwise.

Mesa source code and any upstream-derived files retain their **original upstream copyright and license notices**. Do not remove or replace upstream attribution when carrying patches against Mesa.

See `LICENSE` and `THIRD_PARTY_NOTICES.md`.
