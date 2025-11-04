# AIM : 4-bit Carry Save Multiplier RTL to GDS
# Appratus : pc , vivado z board 
# Introduction
This project presents the RTL-to-GDSII design flow of a 4-bit Carry Save Multiplier
(CSM). The objective is to design, verify, synthesize, and implement the multiplier on
FPGA and ASIC platforms. The design was verified in Vivado, simulated using behavioral
testbenches, and synthesized for hardware implementation.
# Introduction
This project presents the RTL-to-GDSII design flow of a 4-bit Carry Save Multiplier
(CSM). The objective is to design, verify, synthesize, and implement the multiplier on
FPGA and ASIC platforms. The design was verified in Vivado, simulated using behavioral
testbenches, and synthesized for hardware implementation.
#  Design Flow
The steps followed for the 4-bit Carry Save Multiplier are:
1. RTL design using Verilog HDL.
2. Functional verification using testbench and simulation.
3. Synthesis and implementation on FPGA (ZedBoard).
4. Post-synthesis simulation and timing analysis.
5. Physical layout (place & route) and generation of GDSII
# . RTL Design (Source Code)
   The Verilog source code for the 4-bit Carry Save Multiplier is given below:
   module carry_save_multiplier_4bit (
2 input [3:0] A ,
3 input [3:0] B ,
4 output [7:0] P
5 ) ;
6 wire [3:0] pp0 , pp1 , pp2 , pp3 ;
7 wire [7:0] s1 , s2 , s3 ;
8
9 // Partial Products
10 assign pp0 = A & {4{ B [0]}};
11 assign pp1 = A & {4{ B [1]}};
12 assign pp2 = A & {4{ B [2]}};
13 assign pp3 = A & {4{ B [3]}};
14
15 // Align partial products
16 assign s1 = {4 ’ b0 , pp0 };
17 assign s2 = {3 ’ b0 , pp1 , 1 ’ b0 };
3
18 assign s3 = {2 ’ b0 , pp2 , 2 ’ b0 };
19 wire [7:0] pp4 = {1 ’ b0 , pp3 , 3 ’ b0 };
20
21 // Stage - wise addition
22 wire [7:0] sum1 , sum2 , sum3 , carry1 , carry2 , carry3 ;
23 assign { carry1 , sum1 } = s1 + s2 ;
24 assign { carry2 , sum2 } = sum1 + s3 ;
25 assign { carry3 , sum3 } = sum2 + pp4 ;
26
27 // Final output
28 assign P = sum3 + carry3 ;
29 endmodule
4. Testbench
The testbench used for f

