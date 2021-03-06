# arm-cortexm-toolchain-macos-arm64
A cross-compiler toolchain for macOS (12) arm64 host and arm-none-eabi targets optimized for cortex-m0+, cortex-m4f and cortex-m7f.

#### Installation
Checkout somewhere (e.g. to `/usr/local/arm-none-eabi`) and add the `bin` folder of that path (e.g `/usr/local/arm-none-eabi/bin`) to *PATH*.

#### Components and Versions
* gcc 12.1, newlib 4.2, binutils 2.38, gdb 12.1 (built with crosstool-ng)
  * newlib is built with nano malloc
  * newlib is available in two versions:
    1. with standard printf (*libc.a*)
    1. with nano formatted io printf (*libc_nano.a*), select with `--specs=nano.specs`
  * newlib and libstdc++ are build with unwind tables, if not needed, discard sections `.ARM.exidx` and `.ARM.extab` via linker script to save some memory
