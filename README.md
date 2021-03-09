[![Build][ot-gh-action-build-svg]][ot-gh-action-build]

[ot-gh-action-build]: https://github.com/openthread/ot-kw41z/actions?query=workflow%3ABuild+branch%3Amain+event%3Apush
[ot-gh-action-build-svg]: https://github.com/openthread/ot-kw41z/workflows/Build/badge.svg?branch=main&event=push

---

# OpenThread on KW41Z Example

This repo contains example platform drivers for the [NXP(Freescale) Kinetis MKW41Z512][mkw41z512] based on [FRDM-KW41Z][frdm-kw41z] hardware platform.

[mkw41z512]: http://www.nxp.com/products/microcontrollers-and-processors/arm-processors/kinetis-cortex-m-mcus/w-series-wireless-m0-plus-m4/kinetis-kw41z-2.4-ghz-dual-mode-ble-and-802.15.4-wireless-radio-microcontroller-mcu-based-on-arm-cortex-m0-plus-core:KW41Z
[frdm-kw41z]: http://www.nxp.com/products/software-and-tools/hardware-development-tools/freedom-development-boards/nxp-freedom-development-kit-for-kinetis-kw41z-31z-21z-mcus:FRDM-KW41Z

The example platform drivers are intended to present the minimal code necessary to support OpenThread. As a result, the example platform drivers do not necessarily highlight the platform's full capabilities.

## Toolchain

Download and install the [GNU toolchain for ARM Cortex-M][gnu-toolchain].

[gnu-toolchain]: https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm

In a Bash terminal, follow these instructions to install the GNU toolchain and other dependencies.

```bash
$ cd <path-to-ot-kw41z>
$ ./script/bootstrap
```

## Building

In a Bash terminal, follow these instructions to build the kw41z examples.

```bash
$ cd <path-to-ot-kw41z>
$ ./script/build
```

## Flash Binaries

If the build completed successfully, the `elf` files may be found in `<path-to-ot-kw41z>/build/bin/`. You can convert them to `bin` files using `arm-none-eabi-objcopy`:

```bash
$ arm-none-eabi-objcopy -O binary ot-cli-ftd ot-cli-ftd.bin
```

Compiled binaries may be flashed onto the MKW41Z512 using drag-and-drop into the board's MSD Bootloader or the [NXP(Freescale) Test Tool][test-tool] or [JTAG interface][jtag]. The [NXP(Freescale) Test Tool][test-tool] provides a convenient method for flashing a MKW41Z512 via the [J-Link][jlink].

[test-tool]: http://www.nxp.com/webapp/sps/download/license.jsp?colCode=TESTTOOL_SETUP
[jtag]: https://en.wikipedia.org/wiki/JTAG
[jlink]: https://www.segger.com/jlink-software.html

## Interact

1. The CLI example uses a UART connection (serial port settings: 115200 8-N-1).
2. Type `help` for list of commands.
3. See [OpenThread CLI Reference README.md][cli] to learn more.

[cli]: https://github.com/openthread/openthread/blob/main/src/cli/README.md

# Contributing

We would love for you to contribute to OpenThread and help make it even better than it is today! See our [Contributing Guidelines](https://github.com/openthread/openthread/blob/main/CONTRIBUTING.md) for more information.

Contributors are required to abide by our [Code of Conduct](https://github.com/openthread/openthread/blob/main/CODE_OF_CONDUCT.md) and [Coding Conventions and Style Guide](https://github.com/openthread/openthread/blob/main/STYLE_GUIDE.md).

# License

OpenThread is released under the [BSD 3-Clause license](https://github.com/openthread/ot-kw41z/blob/main/LICENSE). See the [`LICENSE`](https://github.com/openthread/ot-kw41z/blob/main/LICENSE) file for more information.

Please only use the OpenThread name and marks when accurately referencing this software distribution. Do not use the marks in a way that suggests you are endorsed by or otherwise affiliated with Nest, Google, or The Thread Group.

# Need help?

There are numerous avenues for OpenThread support:

- Bugs and feature requests — [submit to the Issue Tracker](https://github.com/openthread/openthread/issues)
- Stack Overflow — [post questions using the `openthread` tag](http://stackoverflow.com/questions/tagged/openthread)
- Google Groups — [discussion and announcements at openthread-users](https://groups.google.com/forum/#!forum/openthread-users)

The openthread-users Google Group is the recommended place for users to discuss OpenThread and interact directly with the OpenThread team.
