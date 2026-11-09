# OnePlus SM8650 kernel

Linux kernel tree for OnePlus devices based on Qualcomm SM8650 (pineapple),
used by the OnePlus 12 (`waffle`) MikuUI build.

## Maintainer

- **SorasakiHinaHusband** — <https://github.com/SorasakiHinaHusband>

## Branch

- `Cinderella` — MikuUI (Android 17 / BP2A)

## Building

The kernel is built as part of the Android build; the device tree sets:

- `TARGET_KERNEL_SOURCE := kernel/oneplus/sm8650`
- `TARGET_KERNEL_CONFIG := gki_defconfig vendor/oplus/pineapple_GKI.config`
- `TARGET_KERNEL_EXT_MODULE_ROOT := kernel/oneplus/sm8650-modules`

Device trees and out-of-tree modules live in the sibling repositories:

- `SorasakiHinaHusband/android_kernel_oneplus_sm8650-devicetrees`
- `SorasakiHinaHusband/android_kernel_oneplus_sm8650-modules`

```bash
source build/envsetup.sh
lunch miku_waffle-cp2a-user
mka bootimage
```

## License

The kernel is licensed under the GNU General Public License, version 2. See
`COPYING` and the `SPDX-License-Identifier` tags in individual files.
