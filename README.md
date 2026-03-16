# 4-to-1 Multiplexer: Logic Design & PCB Implementation

## Overview
This project details the systematic design process of a 4-to-1 Multiplexer (MUX) combinational logic circuit. The workflow spans from defining the functional truth table and deriving the Boolean expression to minimizing logic gates for physical Printed Circuit Board (PCB) implementation. A strong emphasis is placed on Bill of Materials (BOM) cost optimization through universal logic gate synthesis.

## Tools & Components
* **Simulation & Schematic:** Proteus 8, KiCad
* **PCB Layout:** Proteus 8
* **Active Components:** 3x 74HC00 (Quad 2-input NAND gate ICs)
* **Passive & UI Components:** 6x Red LEDs (Input state indicators), 1x Green LED (Output indicator), 7x 220Ω Resistors, 6x 10kΩ Resistors.
* **Hardware Base:** 12cm x 8cm Copper Board.

## Logic Minimization & BOM Optimization (Engineering Highlight)
The canonical Sum-of-Products (SOP) expression for the 4-to-1 MUX was derived from the truth table as:
`Y = (S1'.S0'.I₀) + (S1'.S0.I₁) + (S1.S0'.I₂) + (S1.S0.I₃)`

To optimize manufacturing costs and simplify routing, the design constraint was to utilize **only universal NAND gates**. We mathematically evaluated multiple Boolean transformations:
* **Solutions 1 & 2:** Required 29 and 19 NAND gates respectively. This would necessitate a mix of expensive 4-input NAND ICs (SN74LS20N) and 2-input NAND ICs (74HC00N), resulting in a logic cost of ~17,200 VND.
* **Solution 3 (Chosen Design):** Through meticulous Boolean algebra manipulation, the logic was minimized to require **only 11 NAND gates**. This allowed the entire system to be built using just three inexpensive **74HC00N** ICs. This optimization successfully reduced the logic component cost to 9,600 VND while improving board space efficiency.


![image](https://github.com/Hudo1501/4-to-1-Multiplexer/blob/37a3eb20336899f85c454583f295ef8d6ca089c8/simplify_table.jpg)

## Simulation Verification
The minimized gate-level schematic was built and simulated in Proteus 8. All 16 possible combinations of data inputs (I0 to I3) and select inputs (S1, S2) were rigorously tested. The output 'Y' accurately reflected the selected data channel across all scenarios, verifying the mathematical logic.

![image](https://github.com/Hudo1501/4-to-1-Multiplexer/blob/1625b1436196f37465febde09cdb8dcccda68ceb/schematic.jpg)

## PCB Layout & Physical Implementation
The verified logic was routed on a 12x8cm custom copper board. To make the digital behavior easily observable, Red LEDs were integrated to indicate the real-time high/low states of the inputs, while a Green LED was used to display the final routed output signal.

*(Paste your Proteus PCB Layout and 3D View here - Fig 4 & Fig 5)*
![image](https://github.com/Hudo1501/4-to-1-Multiplexer/blob/c70d2fa79254cbfc412de4f14d992998a83793ce/3d_front.jpg)
![image](https://github.com/Hudo1501/4-to-1-Multiplexer/blob/72190008b4e57703fd8c99165d8a23e0ef781faa/3d_bottom.jpg)
*(Paste your final physical hardware testing image here)*


## My Contribution
As a core member of Team 1, my primary contributions (accounting for 35% of the total workload) included:
* **Simulation:** Translating the derived Boolean logic into the Proteus schematic and conducting comprehensive state-space testing.
* **PCB Design:** Routing the physical traces and finalizing the board layout for hardware fabrication.
* **Documentation:** Synthesizing the logic derivation and experimental validation into the final technical report.
