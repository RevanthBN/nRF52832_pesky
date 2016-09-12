# nRF52832_pesky
Programming nRF52832 + MPU9250 + BMP280 dev board from https://www.tindie.com/products/onehorse/nrf52832-development-board/ with nRF52 SDK, GCC and JLink.

##Prerequisites

1. nRF5 SDK - https://www.nordicsemi.com/eng/Products/Bluetooth-low-energy/nRF5-SDK (all code adapted for SDK 12.0.0)
2. ARM GCC Toolchain - https://devzone.nordicsemi.com/tutorials/7/ (I do not use Eclipse yet, just plain GCC, so you could skip part about Eclipse configuration)
3. JLink from SEGGER - I'm using EDU version and have no plans to make it to production
4. MSYS2 - https://msys2.github.io/ (I use Windows as development environment)
..* .bash_profile - you should add JLink and GCC to you PATH, like below

```
PATH="/f/Projects/ARM/gcc-arm-none-eabi-5_4-2016q2-20160622-win32/bin:/c/Program Files (x86)/SEGGER/JLink_V600g:${PATH}"
```

##How to use it

*please review Makefile before executing any command and make sure that you understand what you are doing*

1. Clone repository to your *empty* nRF5 SDK folder:

```
mkdir nRF5_SDK_12.0.0_12f24da
cd nRF5_SDK_12.0.0_12f24da
git clone https://github.com/e27182/nRF52832_pesky projects
```

2. Unpack SDK to the folder
3. Connect your board to JLink
4. Make and flush

```
cd projects\peripheral\blinky\tindie\blank\armgcc
make
```

If you wish to use example with SoftDevice s132, you should ensure that you use correct version of soft device. You can flush it with next command:

```
cd projects\peripheral\blinky\tindie\s132\armgcc
make flush_softdevice
make
```
