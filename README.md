# KAction Worklow

## Usage

> After successful build, it will upload AnyKernel3 in `Action`, which has turned off device check, please flash to phone in Twrp.

First confirm that you have all the required patches for `KernelSU` to work. Then fork this repository to your repository and edit config.env as follows, then click `Star` or `Action`, you will see `Build Kernel` option on the left side, click it and you will see `Run workflows` on the top of the big dialog box on the right side, click it and it will start the build.

### Kernel Source

Type your kernel link

e.g. https://github.com/begonia-dev/android_kernel_xiaomi_mt6785

### Kernel Source Branch

Type your kernel branch

e.g. 13.0

### Kernel defconfig

Type your kernel defconfig

e.g. begonia_user_defconfig

### Kernel file

Type in the image you need, usually the same as BOARD_KERNEL_IMAGE_NAME in your aosp-device tree.

e.g. Image.gz-dtb

### Clang version

The default version is zyc clang19.0.0, if you need to change it, do it so by editing the build-kernel.yml

### Extra build commands

Some kernels require some build commands to be typed in manually in order to build properly, so please don't type them in if you don't need to.
Separate commands with spaces.

e.g. LLVM=1 LLVM_IAS=1

### Disable LTO

This is used to optimize the kernel, but sometimes it causes errors, so it is provided that it can be disabled, set to false to enable.

### Use overlayfs

It is recommended to add the overlayfs configs in defconfig of your kernel soure.

`CONFIG_OVERLAY_FS=y`
`CONFIG_OVERLAY_FS_REDIRECT_DIR=y`
`CONFIG_OVERLAY_FS_INDEX=y`

### Need DTBO

If your kernel also needs to be flashed with DTBO image, set it to true.

## Credits

- [Yervant](https://github.com/Yervant7)
- [Ravindu](https://github.com/ravindu644)
- [AnyKernel3](https://github.com/osm0sis/AnyKernel3)
- [AOSP](https://android.googlesource.com)
- [xiaoxindada](https://github.com/xiaoxindada)
- [xiaoleGun](https://github.com/xiaoleGun)
