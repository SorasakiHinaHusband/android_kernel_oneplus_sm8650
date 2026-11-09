# 一加 SM8650 内核 🌱

高通 SM8650（pineapple）平台的一加机型内核源码，
一加 12（`waffle`）的 MikuUI 构建就跑在这上面。

> 上游 Android Common Kernel 的说明挪到了 `README.upstream.md`，
> 想给 ACK 提补丁的请出门左转。

## 谁在管这棵树

**SorasakiHinaHusband** —— 内核 panic 了别急着骂，先带上 last_kmsg 🙏

## 分支

`Cinderella` —— MikuUI（Android 17 / BP2A）。

## 怎么编

内核是跟着 Android 构建系统一起编的，设备树里定好了：

- `TARGET_KERNEL_SOURCE := kernel/oneplus/sm8650`
- `TARGET_KERNEL_CONFIG := gki_defconfig vendor/oplus/pineapple_GKI.config`
- `TARGET_KERNEL_EXT_MODULE_ROOT := kernel/oneplus/sm8650-modules`

设备树和外部模块住在隔壁：

- `SorasakiHinaHusband/android_kernel_oneplus_sm8650-devicetrees`
- `SorasakiHinaHusband/android_kernel_oneplus_sm8650-modules`

```bash
source build/envsetup.sh
lunch miku_waffle-cp2a-user
mka bootimage
```

## 许可证

内核按 GNU General Public License v2 授权。
详见 `COPYING` 和各文件里的 `SPDX-License-Identifier` 标识。
