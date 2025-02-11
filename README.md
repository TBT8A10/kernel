This kernel matches the stock kernel's Linux version and is likely very similar. It can be used to build kernel modules, like a driver for an external wifi adapter.

## Building Kernel Modules
* Prepare kernel & toolchain
    1. Clone this repo
    2. Download [Linaro 6.3.1 toolchain](https://releases.linaro.org/components/toolchain/binaries/6.3-2017.05/aarch64-linux-gnu/gcc-linaro-6.3.1-2017.05-x86_64_aarch64-linux-gnu.tar.xz)
    3. `make ARCH=arm64 tbt8a10_defconfig`
* Build module
    1. Go to the directory where the source code of the module you want to build is
    2. `make ARCH=arm64 CROSS_COMPILE=<toolchain-path>/bin/aarch64-linux-gnu- -C <kernel source path>/ M=<module source path>/`
* Push the `<module>.ko` to your device & load it with `insmod <module>.ko`