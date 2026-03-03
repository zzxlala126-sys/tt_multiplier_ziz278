<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

This project implements a simple 4-bit digital multiplier in Verilog and integrates it into a top-level module compatible with the TinyTapeout interface. The multiplier module computes the product of two 4-bit inputs (A and B) and produces an 8-bit output P using combinational logic (P = A * B). In the top module, the input bus ui_in is divided into two 4-bit operands: the upper four bits represent A and the lower four bits represent B. When the enable signal is active and reset is not asserted, these values are passed to the multiplier. The computed result is then routed directly to the output bus uo_out.

## How to test

The design is verified using a Verilog testbench that performs automated functional testing of the multiplier. The testbench generates a clock signal and initializes control signals such as reset (rst_n) and enable (ena). After reset is released, the enable signal activates the multiplier and random values are applied to inputs A and B. For each test iteration, the expected product is calculated inside the testbench and compared with the module output. The simulation runs for 1000 test cases to validate correctness. A counter records the number of successful matches, and the final results are printed at the end of the simulation to evaluate the design.

## External hardware

This project does not require any external hardware components. The entire design is implemented using synthesizable Verilog logic and is intended for digital simulation or FPGA/ASIC integration. All inputs and outputs are handled through the standard TinyTapeout interface signals, including ui_in, uo_out, clk, ena, and rst_n. The multiplier operates purely as digital combinational logic and does not rely on peripherals such as PMOD devices, displays, sensors, or external memory. Therefore, the design can be fully tested in a simulation environment without any additional hardware resources.
