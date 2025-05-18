# ft8042
This is the patched version of `i8042` module to make PS/2 keyboard & mouse/trackpad on Phytium processor based laptops work.

This is originally from [atzlinux-kernel](https://gitee.com/atzlinux/atzlinux-kernel/tree/master/drivers/input/serio/ft8042) and patched to make it compile on Gentoo kernel 6.12.21.

# How to compile and use
1. Put `ft8042.c`, `ft8042.h` and `parameter.h` in `/usr/src/linux/drivers/input/serio`.
2. Add the following line in `Makefile` under `/usr/src/linux/drivers/input/serio`:
   ```
   obj-m += ft8042.o
   ```
3. Assuming kernel configuration has been done, `cd /usr/src/linux && make -j$(nproc)`
4. `make modules_install && make install`
5. Make sure module `ft8042` in configured in `/etc/modules-load.d/` .
6. Reboot and check if it works.

# License ?
Upstream (atzlinux-kernel & Phytium Co., Ltd.) didn't specify a license.
