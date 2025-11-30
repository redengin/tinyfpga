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
# install APIO
pipx install -U git+https://github.com/fpgawars/apio.git@develop
apio drivers install serial
apio drivers install ftdi

# install tinyprog
pipx install tinyprog

# update the bootloader
tinyprog --update-bootloader
```

For IDE I'm using vscode with the "fpgawars.apio" extension
* not available on the marketplace, so install via [VSIX](https://github.com/FPGAwars/apio-vscode/releases).

**NOTE**: you must launch vscode from an FPGA project directory (see [FPGA Projects](#fpga-projects))

**NOTE**: the first time the "fpgawars.apio" extension activates it attempts
to install apio and fails. closing the vscode workspace and reopening it all
starts working...

FPGA Projects
================================================================================
APIO provides examples/templates
```sh
apio install examples
```

[Quick Start](quickstart/)
--------------------------------------------------------------------------------
**NOTE** this is just an example to use APIO tools (not for a TinyFPGA-BX)

The [quickstart/](quickstart/) contents were created by
```sh
apio examples fetch Alhambra-II/ledon
```

[tinyfpga-bx.blinky/](tinyfpga-bx.blinky/)
--------------------------------------------------------------------------------
was created via
```sh
apio examples fetch Alhambra-II/ledon
```
Let's you explore APIO tools
```
Build commands:
  apio build        Synthesize the bitstream.
  apio upload       Upload the bitstream to the FPGA.
  apio clean        Delete the apio generated files.

Verification commands:
  apio lint         Lint the source code.
  apio format       Format verilog source files.
  apio sim          Simulate a testbench with graphic results.
  apio test         Test all or a single verilog testbench module.
  apio report       Report design utilization and timing.
  apio graph        Generate a visual graph of the code.
```


[TinyFPGA-BX/](submodules/TinyFPGA-BX/)
--------------------------------------------------------------------------------
NOTE: ```git submodule update --init```

Provides TinyFPGA-BX specific board schematic, templates, design-for-test (DFT),
and an alternate bootloader.

### [picosoc](submodules/TinyFPGA-BX/examples/picosoc)
An example of a RISC-V soft-core.

* Needs [OSS-CAD-SUITE](https://github.com/YosysHQ/oss-cad-suite-build#installation)
  * if you use the source release you'll need to run `builder.py` which takes quite a while...
  * binary releases - https://github.com/YosysHQ/oss-cad-suite-build/releases

NOTE: it appears additional tools are required, but I stopped here
  * [arachne-pnr](https://github.com/YosysHQ/arachne-pnr)