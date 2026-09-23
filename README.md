# Giada F105D VT-x / VT-d firmware fix

Manufacturer-provided firmware package that exposes and enables Intel VT-x and VT-d in the BIOS setup of compatible Giada F105D systems.

## Compatibility

Use this update only with a **Giada F105D** matching the vendor project identifier **JHS61L-10 / 2G Memory**. The image is `H61LCB37.bin`, dated **2025-10-13**.

Do not flash it to another Giada model, board revision, memory configuration, or an unverified variant.

## Download and verification

Download the release asset `JHS61L_H61LCB37_20251013.rar`, then verify its SHA-256 before extracting:

```text
96BE63997F73EC4C5CCC70D2BC18A7710C895933A9A83D53FEC3A9D691102F92  JHS61L_H61LCB37_20251013.rar
```

The extracted firmware image must have this SHA-256:

```text
333141DE9EF4818D08211124FBECB76C35FD966624C4F2763CBDCD127178AA24  H61LCB37.bin
```

## Flashing safety

- This is a 16 MiB firmware image. The included `startup.nsh` runs `fpt.efi -f H61LCB37.bin` automatically; it is not a preview or validation command.
- Verify the board identity and checksums, and make a tested backup of the existing firmware before flashing.
- Use stable power. Do not interrupt the update or flash a system with hardware faults.
- Stop on any FPT error. This repository does not add an alternative flashing procedure.

## Package note

The vendor archive is preserved unchanged. Its README contains stale references to `61L004B0.bin` and an ME update; the actual supplied script targets `H61LCB37.bin`. Analysis of this image found no Intel ME or GbE region in its flash descriptor.

## Distribution

Published with permission from Giada support as a general-availability fix. Firmware remains proprietary to its respective owner; no open-source license is granted by this repository.
