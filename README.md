# ARITHMETIC-LOGIC-UNIT-ALU

*COMPANY*: CODTECH IT SOLUTIONS PVT LTD

*NAME*: GUJJULA TIRUPATHI REDDY

*INTERN ID*: CTIS0865

*DOMAIN*: VLSI

*DURATION* 24 WEEKS

*DESCRIPTION*:
The Arithmetic Logic Unit (ALU) is one of the most important components in any digital system, including microprocessors, embedded controllers, and programmable logic devices. It performs all arithmetic and logical operations required by the processor. In this project, a basic 8-bit ALU was designed using Verilog hardware description language, supporting five key operations: Addition, Subtraction, AND, OR, and AND-NOT. The objective of the project was to understand digital design principles, combinational logic implementation, and functional verification through simulation.

The ALU designed here is purely combinational, meaning outputs respond immediately to changes in inputs without requiring a clock. Two 8-bit operands, A and B, and a 3-bit opcode are provided as inputs. The opcode determines the operation to be performed. For example, opcode 000 corresponds to addition, 001 to subtraction, 010 to logical AND, 011 to OR, and 100 to AND-NOT operation, which computes A AND (NOT B). The output Y is also 8 bits wide and updates in real time based on the selected operation.

Working Principle

The internal design uses a Verilog case statement inside a combinational always @(*) block. When the opcode changes, the ALU selects the corresponding expression. For arithmetic operations, the design uses the built-in + and - operators, while logical operations use bitwise operators such as &, |, and ~. Since the ALU is combinational, propagation delay depends only on the logic depth and not on a clock period. The ADD and SUB operations generate results immediately by using built-in binary adders and subtractors available in synthesis tools. The logical operations simply apply gate-level functionality on corresponding bits of A and B.

Simulation and Verification

To verify the design, a comprehensive Verilog testbench was created. The testbench initializes different input values and applies all five operations sequentially. For example, when A=10, B=5, and opcode=000, the output Y correctly shows 15, confirming that the addition unit works. Similarly, subtraction was tested using values such as A=20 and B=7, resulting in Y=13. Logical operations were verified using bit patterns such as 11001100 and 10101010, and the outputs matched expected results for AND, OR, and AND-NOT operations.

Waveforms generated in simulation tools like ModelSim or QuestaSim clearly show that the ALU output changes instantly when inputs or opcode change. No glitches or metastability issues were observed, confirming the correctness of the combinational design. The simulation also validated that the ALU handles both arithmetic and logical operations without clocking overhead.

Performance Analysis

The designed ALU is highly efficient since it is purely combinational. The latency is equal to the propagation delay of the slowest path, typically the adder logic. Throughput is effectively instantaneous because the ALU can compute one result per input change. The hardware utilization is minimal: a single adder/subtractor block and a few logic gates for AND/OR operations. The AND-NOT operation is implemented using a NOT gate followed by an AND gate, requiring negligible extra logic. Since no registers or clock circuitry are used, power consumption is low, and the design is synthesizable on both FPGA and ASIC platforms.

