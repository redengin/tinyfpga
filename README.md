Playground for exploring [TinyFPGA](https://tinyfpga.com/)
================================================================================
[TinyFPGA Github](https://github.com/tinyfpga)

I'm using a [TinyFPGA BX](https://www.crowdsupply.com/tinyfpga/tinyfpga-ax-bx).
* [bootloader github](https://github.com/tinyfpga/TinyFPGA-Bootloader)
* [TinyFPGA BX github](https://github.com/tinyfpga/TinyFPGA-BX)

Setup https://tinyfpga.com/bx/guide.html
================================================================================
How I installed APIO and tinyprog
```
pipx install apio tinyprog
apio drivers --serial-enable # asks for root permission to update udev

# test it out by updating the bootloader
tinyprog --update-bootloader
```

For IDE I'm using vscode with the "fpgawars.apio" extension
* not available on the marketplace, so install via [VSIX](https://github.com/FPGAwars/apio-vscode/releases).

**NOTE**: you must launch vscode from an FPGA project directory

**NOTE**: the first time the "fpgawars.apio" extension activates it attempts
to install apio and fails. closing the vscode workspace and reopening it all
starts working...

FPGA Projects
================================================================================
[Quick Start](https://fpgawars.github.io/apio/docs/quick-start/)
--------------------------------------------------------------------------------
The [quickstart/](quickstart/) folder was created by
```sh
apio examples fetch alhambra-ii/getting-started
```

