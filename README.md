# CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier
This repository presents the design of 8bit Wallace Tree Multiplier using Synopsys Custom Compiler on 28nm CMOS Technology.
# Abstract
A Wallace multiplier is a hardware implementation of a binary multiplier, a digital circuit that multiplies two integers. It uses a selection of full and half adders (the Wallace tree or Wallace reduction) to sum partial products in stages until two numbers are left. Wallace multipliers reduce as much as possible on each layer.Wallace multipliers were devised by the Australian computer scientist Chris Wallace in 1964.

*The Wallace tree has three steps:*

1. Multiply each bit of one of the arguments, by each bit of the other.
2. Reduce the number of partial products to two by layers of full and half adders.
3. Group the wires in two numbers, and add them with a conventional adder.
# INTRODUCTION
The Wallace tree is a variant of long multiplication. 

- The first step is to multiply each digit (each bit) of one factor by each digit of the other. Each of this partial products has weight equal to the product of its factors. The final product is calculated by the weighted sum of all these partial products.

- In the second step, the resulting bits are reduced to two numbers; this is accomplished as follows: 
 
 As long as there are three or more wires with the same weight add a following layer:-
1. Take any three wires with the same weights and input them into a full adder. The result will be an output wire of the same weight and an output wire with a higher weight for each three input wires.
2. If there are two wires of the same weight left, input them into a half adder.
3. If there is just one wire left, connect it to the next layer.

- In the third and final step, the two resulting numbers are fed to an adder, obtaining the final product.

![2022-03-16 (2)](https://user-images.githubusercontent.com/100506927/158533648-e9faa4b5-4701-4db8-837c-65e05a75b8b8.png)

# Tools Used
- **Synopsys Custom Compiler**:  The Synopsys Custom Compiler™ design environment is a modern solution for full-custom analog, custom digital, and mixed-signal IC design. As the heart of the Synopsys Custom Design Platform, Custom Compiler provides design entry, simulation management and analysis, and custom layout editing features. This tool was used to design the circuit on a transistor level.
- **Synopsys Primewave**:  PrimeWave™ Design Environment is a comprehensive and flexible environment for simulation setup and analysis of analog, RF, mixed-signal design, custom-digital and memory designs within the Synopsys Custom Design Platform. This tool helped in various types of simulations of the above designed circuit.
- **Synopsys 28nm PDK**:  The Synopsys 28nm Process Design Kit(PDK) was used in creation and simulation of the above designed circuit.

# CMOS NOT Gate
![2022-03-01 (38)](https://user-images.githubusercontent.com/100506927/158534736-26f12122-c3ce-4bb7-b6fe-9bf26230602f.png)
# CMOS AND Gate
![2022-03-01 (36)](https://user-images.githubusercontent.com/100506927/158534952-057bbfe0-dd9b-4d93-9731-7c2a0f4e017e.png)
# CMOS OR Gate
![2022-03-01 (41)](https://user-images.githubusercontent.com/100506927/158535048-f30e4953-a17e-41f6-9fee-5615bebf9461.png)
# CMOS EX-OR Gate
![2022-03-01 (43)](https://user-images.githubusercontent.com/100506927/158535174-50a27c7a-2782-4733-b55b-e2e0f35cc4fa.png)
# Half Adder Module
![2022-03-01 (47)](https://user-images.githubusercontent.com/100506927/158535435-2a19d6a8-9cf6-48a3-b47e-b006eaba70c1.png)
# Full Adder Module
![2022-03-01 (45)](https://user-images.githubusercontent.com/100506927/158535605-dbe8be72-7ea0-4b85-a5e2-506e374abead.png)
# 8x1 Multiplier
![2022-03-01 (30)](https://user-images.githubusercontent.com/100506927/158535966-8ca677e1-4322-4bd1-b200-a7478175b057.png)
# Layer 1-Group 1
In this reduction layer, we multiply 3bits by 8bits.
- In doing so, we require 3 8x1 multiplier, 6 Full Adder,and 2 Half Adder:
![2022-03-01 (49)](https://user-images.githubusercontent.com/100506927/158537554-3316ae71-f654-42f6-87e2-01a2ffc9e163.png)
# Layer 1-Group 2
![2022-03-01 (49)](https://user-images.githubusercontent.com/100506927/158537939-3b51d4bd-7a1c-47f9-8dd1-3c9aa5ddb09b.png)
# Layer 1-Group 3
![2022-03-01 (51)](https://user-images.githubusercontent.com/100506927/158537739-9b58c3eb-22df-4d90-b612-2b9c10ee1a78.png)
# Layer 2
![2022-03-01 (53)](https://user-images.githubusercontent.com/100506927/158538217-7dc7d5a8-b749-4739-ba67-8d977e496579.png)
# Layer 3
![2022-03-01 (55)](https://user-images.githubusercontent.com/100506927/158538291-286a93a9-e5ee-48b2-bfb1-4fe1e670199d.png)
# Layer 4
![2022-03-01 (57)](https://user-images.githubusercontent.com/100506927/158538417-4cbc697c-6659-43fe-9421-99f92ca3d8a6.png)
# Layer 5
![2022-03-01 (34)](https://user-images.githubusercontent.com/100506927/158538507-6c1f0dad-de9e-40bb-8ae0-82dd9559f493.png)
# Wallace Tree Symbol
![2022-03-01 (35)](https://user-images.githubusercontent.com/100506927/158539244-d3d30425-b084-496c-90bb-98867794379b.png)
# DC Analysis Testbench
![2022-03-01 (59)](https://user-images.githubusercontent.com/100506927/158539547-f88082e5-9fec-4a4d-8403-f12cc91fb6c9.png)
#
