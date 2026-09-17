# ft-drivermesa

[English](README_EN.md) | **Bahasa Indonesia**

Project eksperimen Mesa/Crocus untuk target GPU Intel tertentu.

> Dibuat oleh **ft_aska.90**
>
> **PERINGATAN:** Project ini masih dalam pengembangan aktif dan **tidak direkomendasikan untuk penggunaan harian/normal**.

## Target Hardware

Repository ini ditujukan untuk:

- GPU: **Intel HD Graphics 3000**
- Arsitektur: **Sandy Bridge / SNB GT2**
- PCI ID: **8086:0116**
- Driver family: **Mesa Crocus**
- Environment utama: **Linux / X11**

## Lingkungan Pengembangan / Pengujian

- Laptop: **Toshiba Satellite L735 (PSK0AL-010004)**
- CPU: **Intel Core i3-2350M @ 2.30 GHz**
- GPU: **Intel HD Graphics 3000 / Sandy Bridge GT2**
- GPU PCI ID: **8086:0116**
- RAM: **3.76 GiB**
- OS: **CachyOS x86_64**
- Kernel pengembangan: **Linux 7.1.8-1-cachyos**
- Desktop Environment: **Xfce 4.20**
- Window Manager: **Xfwm4**
- Display Server: **X11**
- Graphics stack: **Mesa 26.1.6 / Crocus / i915**

## Peringatan Kompatibilitas

**Jangan langsung memasang atau menerapkan patch/build ini pada perangkat berbeda.**

Project hanya layak dicoba jika GPU, PCI ID, generasi hardware, Mesa driver, kernel graphics driver, dan environment kamu sama atau benar-benar kompatibel. GPU dengan nama pemasaran yang mirip belum tentu memakai generasi, PCI ID, atau driver path yang sama.

Sebelum mencoba, cek minimal:

```bash
lspci -nn | grep -Ei 'vga|display|3d'
glxinfo -B
uname -a
```

Target yang diharapkan adalah Intel HD Graphics 3000 / Sandy Bridge GT2 dengan PCI ID yang sesuai dan stack Mesa/Crocus yang kompatibel.

## Status Pengembangan

**Experimental / in development.**

Risiko yang mungkin terjadi:

- graphical corruption / rendering glitch;
- aplikasi atau game crash;
- session X11 tidak stabil;
- regresi setelah update Mesa/kernel;
- performa lebih buruk dari driver distro;
- aplikasi grafis gagal berjalan jika install salah.

Sebaiknya gunakan custom build secara side-by-side atau prefix terisolasi. Jangan mengganti package Mesa distro secara langsung kecuali kamu tahu cara recovery melalui TTY/package manager.

## Persiapan Recovery

Sebelum testing:

1. simpan package Mesa distro dan pahami cara restore;
2. backup source/config yang dimodifikasi;
3. coba custom build lewat environment variables atau isolated prefix lebih dulu;
4. catat versi/commit Mesa, kernel, PCI ID GPU, dan build flags untuk setiap test.

## Struktur Repository

- `patches/` — patch Mesa/Crocus.
- `scripts/` — helper build, launch, benchmark, atau rollback.
- `docs/` — catatan hardware, hasil test, dan dokumentasi pengembangan.

## Lisensi

Kode/original work buatan **ft_aska.90** menggunakan **MIT License**, kecuali file tertentu menyatakan hal lain.

Source Mesa dan file turunan upstream tetap mempertahankan copyright dan lisensi upstream masing-masing. Jangan menghapus attribution upstream.

Lihat `LICENSE` dan `THIRD_PARTY_NOTICES.md`.
