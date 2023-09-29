# Compiled firmware

The compiled firmware is ready to flash, and you can download it from [here](https://drive.google.com/drive/folders/1hYmq0JSfdpY_xRYRoUmOEOPrWqblNjE2?usp=drive_link).

# Raw Firmware

* Rev. 1 Support RGB matrix
* Rev. 2 Support RGB light (underglow)


Make example for this keyboard (after setting up your build environment):

    make dp3000/rev1:default
    make dp3000/rev2:default
    make dp3000/rev1:via
    make dp3000/rev2:via

Flashing example for this keyboard:

    make dp3000/rev1:default:flash
    make dp3000/rev2:default:flash
    make dp3000/rev1:via:flash
    make dp3000/rev2:via:flash

See the [build environment setup](https://docs.qmk.fm/#/getting_started_build_tools) and the [make instructions](https://docs.qmk.fm/#/getting_started_make_guide) for more information. Brand new to QMK? Start with our [Complete Newbs Guide](https://docs.qmk.fm/#/newbs).

## Bootloader

Enter the bootloader in 3 ways:

* Bootmagic reset: Hold down the key at (0,0) in the matrix (left rotary encoder push switch) and plug in the keyboard
* Physical reset button: Briefly press reset button twice, located in front of the first rotary encoder (left rotary encoder)
* Keycode in layout: Press the key mapped to QK_BOOT if it is available
