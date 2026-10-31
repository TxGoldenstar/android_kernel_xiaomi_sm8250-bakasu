# BakaSU + SUSFS for Redmi K40 (alioth)

An independently maintained Linux kernel source tree for the
Xiaomi Redmi K40 (`alioth`), based on Linux 4.19.325.

## Project Status

The current build has been boot-tested on a Redmi K40 running
PixelOS 17 (Android 17).

- Device: Xiaomi Redmi K40 (`alioth`)
- Kernel release: `4.19.325-cip135-st19-Astrology`
- Root implementation: BakaSU
- BakaSU version code: `35252`
- BakaSU source commit: `d5e9e025`
- SUSFS: v2.3.0 (NON-GKI)
SUSFS Patch: JackA1ltman/NonGKI_Kernel_Build_2nd
- Compiler: Android LLVM r596125, Clang 22.0.2

The maintainer verified that the test device boots, root works, and
the SUSFS command-line tool reports version `v2.3.0` and the enabled
feature list.

This does not imply exhaustive hardware, long-duration stability,
or compatibility testing across other ROMs and firmware versions.

## SUSFS Features Reported by the Test Device

- SUS_PATH
- SUS_MOUNT
- SUS_KSTAT
- SPOOF_UNAME
- ENABLE_LOG
- HIDE_KSU_SUSFS_SYMBOLS
- SPOOF_CMDLINE_OR_BOOTCONFIG
- OPEN_REDIRECT
- SUS_MAP

## Build Information

The verified build used an Ubuntu build environment and Android LLVM
r596125 / Clang 22.0.2.

The exact defconfig and full build invocation still need to be
documented before this source snapshot can be considered fully
reproducible.

## Source Provenance

The parent kernel source was imported without its original top-level
Git history. Its original repository URL and base commit were not
preserved in this working copy, so this project does not claim an
unverified upstream URL or commit.

Existing source copyright notices and license files are retained.
If the original parent repository is identified later, this section
should be updated with the exact source URL and revision.

BakaSU source:
https://github.com/Baka-SU/BakaSU
Pinned source commit: `d5e9e025`

SUSFS original kernel integration reference:
AstideLabs/android_kernel_xiaomi_sm8250

Reference release: v20260821-a8adb967
Original SUSFS version: v2.2.0

Original integration commits:
- 794e35b14239fe5a6b13d3d2069ab6004c3f00ae
- 913b8219fcded28cb7f1cad90c182546452e7c21
- 757a6fb42c6cdc0b0e3b80645780c9e140df4bb9

Upstream SUSFS project:
https://gitlab.com/simonpunk/susfs4ksu

The current v2.3.0 NON-GKI implementation is a custom
adaptation for Linux 4.19.325, not an official upstream release.

See SOURCES.md for detailed source attribution and modification history.

## Installation and Recovery

This kernel is intended for the Redmi K40 (`alioth`). Do not assume
that it is compatible with other devices or ROMs.

Back up the current boot image and make sure a recovery method is
available before installing a kernel. Keep the original boot image
separate from this source repository.

Prebuilt images and installation packages, when published, should be
distributed through GitHub Releases rather than committed into the
source tree.

## Licensing

This repository contains components with different licensing terms.
See `COPYING`, `LICENSES/`, and the license files and notices supplied
with individual components.

BakaSU has separate licensing terms for its kernel and non-kernel
components. Preserve its upstream license notices; this README does
not relicense every file under a single project-wide license.

SUSFS and other incorporated components retain their respective
upstream notices and applicable license terms.
