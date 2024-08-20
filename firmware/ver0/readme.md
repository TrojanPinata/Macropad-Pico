# Macropad-Pico

A 12 key macropad based on the Raspberry Pi Pico.

* Keyboard Maintainer: [Brian Hill](https://github.com/TrojanPinata)
* Hardware Supported: [GitHub](https://github.com/TrojanPinata/Macropad-Pico)

## Building and Flashing

Make example for this keyboard (after setting up your build environment):

    make trojan_pinata/macropad-pico/rev0:default
    
Flashing example for this keyboard:

    make trojan_pinata/macropad-pico/rev0:default:flash

Compile example:

    qmk compile -kb trojan_pinata/macropad-pico/rev0 -km default

See the [build environment setup](https://docs.qmk.fm/#/getting_started_build_tools) and the [make instructions](https://docs.qmk.fm/#/getting_started_make_guide) for more information. Brand new to QMK? Start with our [Complete Newbs Guide](https://docs.qmk.fm/#/newbs).

## Bootloader

Enter the bootloader in 3 ways:

* **Physical reset button**: Hold down the `BOOTSEL` button on the Pi Pico, then either plug the board in or press the `RESET` button.

After entering the bootloader through one of the three methods above, the keyboard will appear as a USB mass storage device named `RPI-RP2`. If the CLI is unable to find this device, the compiled `.uf2` file can be manually copied to it. The keyboard will reboot on completion with the new firmware loaded.
