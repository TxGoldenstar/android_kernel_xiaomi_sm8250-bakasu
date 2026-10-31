# Source Attribution and Modification History

## 1. Project

**Project:** BakaSU + SUSFS for Xiaomi Redmi K40 (alioth)

**Kernel:** Linux 4.19.325

**Kernel release string:** `4.19.325-cip135-st19-Astrology`

This repository contains a custom Linux 4.19.325 kernel with BakaSU and a manually adapted SUSFS v2.3.0 NON-GKI implementation.

## 2. Original Kernel Reference

**Repository:** [AstideLabs/android_kernel_xiaomi_sm8250](https://github.com/AstideLabs/android_kernel_xiaomi_sm8250)

**Reference release:** `v20260821-a8adb967`

**Original package:**

`APTKernel_AOSP_alioth_ReSukiSU-SuSFS_20260821_101206_anykernel3_a8adb967.zip`

**Original SUSFS version:** v2.2.0

The original SUSFS integration was taken from this APTKernel release and subsequently adapted for Linux 4.19.325.

## 3. Original SUSFS Integration History

The following commits were identified in the AstideLabs source repository:

| Commit | Date | Description |
|---|---|---|
| `794e35b14239fe5a6b13d3d2069ab6004c3f00ae` | 2026-07-15 | Integrate SuSFS v2.2.0 |
| `913b8219fcded28cb7f1cad90c182546452e7c21` | 2026-07-30 | Sync SuSFS Code |
| `757a6fb42c6cdc0b0e3b80645780c9e140df4bb9` | 2026-08-03 | Sync SuSFS Code |

The original integration includes SUSFS source files and modifications to other Linux kernel components.

## 4. Custom SUSFS Adaptation

The maintainer independently updated and adapted the original v2.2.0 implementation to a custom v2.3.0 NON-GKI implementation for Linux 4.19.325.

This adaptation was performed specifically for the target kernel and is not claimed to be an official upstream SUSFS v2.3.0 release.

### Main changes

- Updated the SUSFS version identifier to v2.3.0.
- Added and adjusted KSTAT functionality.
- Corrected the `KSTAT_SPOOF_CTIME_TV_SEC` bitmask definition.
- Added mount ID and filesystem statistics handling.
- Added KSTAT integration for stat, statfs, inotify and `/proc/fd`.
- Added KSTAT handling for `show_map_vma`.
- Refactored parts of the interaction between KSTAT and Open Redirect.
- Added process flags and helper functions.
- Improved error handling in SUSFS feature reporting.
- Adapted the implementation to the Linux 4.19 kernel interfaces.

### Main SUSFS-related files

- `fs/susfs.c`
- `fs/stat.c`
- `fs/statfs.c`
- `fs/notify/fdinfo.c`
- `fs/proc/fd.c`
- `fs/proc/task_mmu.c`
- `include/linux/susfs.h`
- `include/linux/susfs_def.h`

## 5. BakaSU

**Upstream:** [BakaSU](https://github.com/Baka-SU/BakaSU)

**Integrated commit:** `d5e9e025`

BakaSU is integrated as the kernel root management implementation.

Its original license files and copyright notices are retained. BakaSU has separate licensing terms for its kernel components, userspace components and designated visual assets.

Designated visual assets with separate restrictive licensing terms are excluded from this repository's Git tracking pending separate review.

## 6. Build and Test Information

- Target device: Xiaomi Redmi K40 (`alioth`)
- Android environment: PixelOS 17 (Android 17)
- Kernel version: Linux 4.19.325
- SUSFS: v2.3.0 NON-GKI
- Compiler: Clang 22.0.2
- Root implementation: BakaSU

The kernel was successfully compiled and temporarily boot-tested on the target device.

The running kernel reported the expected custom kernel release string. The SUSFS command-line utility reported version v2.3.0, variant NON-GKI and its enabled feature configuration.

These checks do not imply that every individual SUSFS feature has undergone independent functional testing.

## 7. Licensing and Third-Party Notices

The original kernel tree contains its `COPYING` and `LICENSES` files. Its root license declaration is:

`GPL-2.0 WITH Linux-syscall-note`

BakaSU retains its own license files and asset licensing notices.

The SUSFS source files examined during this adaptation did not contain individual SPDX identifiers or copyright headers. The original APTKernel integration commits examined also did not provide a separate SUSFS licensing statement.

The precise licensing scope of the imported SUSFS contributions therefore remains subject to confirmation with the relevant upstream copyright holders.

No new license is asserted for third-party code by this document. No blanket relicensing of the complete source tree is intended.

All original copyright and license notices must be preserved.

## 8. Acknowledgements

Thanks to the developers and maintainers of:

- Linux Kernel
- LineageOS
- AstideLabs / ApartTUSITU
- BakaSU
- SUSFS and its upstream contributors
- The Xiaomi SM8250 kernel development community
