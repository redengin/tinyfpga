Demonstration of APIO tools
================================================================================
| Build Commands | |
| -------------- | - |
| apio build     |  Synthesize the bitstream. |
| apio upload    |  Upload the bitstream to the FPGA. |
| apio clean     |  Delete the apio generated files. |


| Verification Commands |   |
| --------------------- | - |
| apio lint             | Lint the source code. |
| apio format           | Format verilog source files. |
| apio report           | Report design utilization and timing. |
| apio graph            | Generate a visual graph of the code. |


| Test Commands |   |
| ------------- | - |
| apio sim      | Simulate a testbench with graphic results.
| apio test     | Test all or a single verilog testbench module. |
Test Commands require *testbench* support
* [uut]_tb.v       - testbench I/O mapping
* [uut]_tb.gtkw    - test implementation

Where [uut] has a [uut].v (the implementation of the *unit-under-test*)
