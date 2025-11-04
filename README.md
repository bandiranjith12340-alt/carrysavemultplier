# AIM : 4-bit Carry Save Multiplier implementation on fpga
# Appratus : pc , vivado z board 
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
   <img width="339" height="814" alt="image" src="https://github.com/user-attachments/assets/4ffc5ec7-0c9d-4e9a-b86c-883a7e557430" />
# Testbench  
<img width="578" height="435" alt="image" src="https://github.com/user-attachments/assets/71cf7b62-fded-4180-be5e-619f57bdaeb6" />
# FPGA Pin Mapping (XDC Constraints)
<img width="443" height="885" alt="image" src="https://github.com/user-attachments/assets/58496937-3c3f-454f-af30-6b94a6084def" />
#  Simulation Results
The simulation was performed in Vivado. The waveform below shows correct multiplication outputs.
![WhatsApp Image 2025-10-30 at 13 01 42_6b9566de](https://github.com/user-attachments/assets/446f2638-ebd1-4647-a10f-bec7bdbd1d4c)

# Schematic and Layout
The synthesized RTL schematic and physical layout views are shown below.
![WhatsApp Image 2025-10-30 at 12 58 50_b4e3e00c](https://github.com/user-attachments/assets/9a4e642a-a47c-4799-a312-4b71a7456269)

![WhatsApp Image 2025-10-30 at 12 59 45_d35a5354](https://github.com/user-attachments/assets/d6c68617-a794-49fa-acdc-55788fd6c778)

# FPGA Implementation
The design was implemented on the Digilent ZedBoard FPGA. The product output is
displayed on LEDs.
![WhatsApp Image 2025-11-02 at 22 56 03_e5ef85c2](https://github.com/user-attachments/assets/90b44062-7e25-4cee-bc34-c96322a07f0f)
# Results
The 4-bit Carry Save Multiplier successfully computes partial products and sums them
in a carry-save manner. Simulation and hardware outputs confirm correct operation.
#  Conclusion
The 4-bit Carry Save Multiplier was designed and implemented using Verilog HDL, verified through simulation, and realized on FPGA hardware. The design can be extended
to 8-bit or 16-bit versions for higher performance.




