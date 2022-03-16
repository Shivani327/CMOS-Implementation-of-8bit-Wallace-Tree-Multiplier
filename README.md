# CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier
This repository presents the design of 8bit Wallace Tree Multiplier using Synopsys Custom Compiler on 28nm CMOS Technology.

# Table of Content
- [Abstract](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#abstract)
- [INTRODUCTION](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#introduction)
- [Tools Used](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#tools-used)
- [CMOS NOT Gate](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#cmos-not-gate)
- [CMOS AND Gate](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#cmos-and-gate)
- [CMOS OR Gate](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#cmos-or-gate)
- [CMOS EX-OR Gate](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#cmos-ex-or-gate)
- [Half Adder Module](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#half-adder-module)
- [Full Adder Module](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#full-adder-module)
- [8x1 Multiplier](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#8x1-multiplier)
- [Design Approach](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#design-approach)
- [Layer 1-Group 1 Reduction](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#layer-1-group-1-reduction)
- [Layer 1-Group 2 Reduction](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#layer-1-group-2-reduction)
- [Layer 1-Group 3 Reduction](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#layer-1-group-3-reduction)
- [Layer 2 Reduction](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#layer-2-reduction)
- [Layer 3 Reduction](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#layer-3-reduction)
- [Layer 4 Reduction](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#layer-4-reduction)
- [Layer 5 Reduction or Wallace Tree Schematic](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#layer-5-reduction-or-wallace-tree-schematic)
- [Wallace Tree Symbol](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#wallace-tree-symbol)
- [DC Analysis Testbench](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#dc-analysis-testbench)
- [Simulation Result](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#simulation-result)
- [Netlist](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#netlist)
- [Author](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#author)
- [Acknowledgement](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#acknowledgement)
- [References](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier#references)

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

# Design Approach
We have all the basic elements to build the reduction layers. Reduction layers are build as follows:
- First 3 partial product terms are grouped to group-1. Group-1 includes A0B, A1B, A2B partial products.
- Next 3 partial product terms are grouped to group-2. Group-2 includes A3B, A4B, A5B partial products.
- Remaining 2 partial products are grouped to group-3. Group-3 includes A6B, A7B partial products.
The partial product terms goes through series of reduction layers until there are less than 3 wires having same weight. Reduction layers consists of Full adders and half adders.

In the final stage, we have less than 3 wires having same weights. To get final result we can use ripple carry adder or a carry look a head adder to reduce it to 1bit for each weight

# Layer 1-Group 1 Reduction
The design implemeted in the below schematic reduces A0B, A1B, A2B partial products. This layer uses 3-8x1 multiplier, 6-Full Adder modules and 2-Half Adder modules:
![2022-03-01 (49)](https://user-images.githubusercontent.com/100506927/158537554-3316ae71-f654-42f6-87e2-01a2ffc9e163.png)

# Layer 1-Group 2 Reduction
The design implemeted in the below schematic reduces A3B, A4B, A5B partial products. This layer uses 3-8x1 multiplier, 6-Full Adder modules and 2-Half Adder modules:
![2022-03-01 (49)](https://user-images.githubusercontent.com/100506927/158537939-3b51d4bd-7a1c-47f9-8dd1-3c9aa5ddb09b.png)

# Layer 1-Group 3 Reduction
In the below shown schematic, module generates partial product terms A6B and A7B. These Partial products are passed to next layer for reduction. This layer uses only 2-8x1 multiplier:
![2022-03-01 (51)](https://user-images.githubusercontent.com/100506927/158537739-9b58c3eb-22df-4d90-b612-2b9c10ee1a78.png)

# Layer 2 Reduction
This layer consist of two parts:
- In the first part, the outputs obtained from Layer 1-Group1 is grouped along with the sum obtained from Layer 1-Group2. And with the help of combination of 1-Half adder module and 7-Full adder modules, this layer is further reduced to layer 3.
- In the second part, carry obtained from Layer 1-Group2 is grouped along with the outputs of layer1-group3. With the help of 2-half adder modules and 5-full adder modules, this layer is reduced to layer 3.
![2022-03-01 (53)](https://user-images.githubusercontent.com/100506927/158538217-7dc7d5a8-b749-4739-ba67-8d977e496579.png)

# Layer 3 Reduction
Outputs of layer2 part1 is grouped along with sum of layer2 part2 and using 4-half adder modules and 6-full adder modules, this layer is reduced to layer4.
![2022-03-01 (55)](https://user-images.githubusercontent.com/100506927/158538291-286a93a9-e5ee-48b2-bfb1-4fe1e670199d.png)

# Layer 4 Reduction
With the help of 4-half adder modules and 7-full adder modules,this layer is reduced to layer5.
![2022-03-01 (57)](https://user-images.githubusercontent.com/100506927/158538417-4cbc697c-6659-43fe-9421-99f92ca3d8a6.png)

# Layer 5 Reduction or Wallace tree schematic
This is the final wallace tree schematic which used the concept of 10bit Ripple Carry adder.
![2022-03-01 (34)](https://user-images.githubusercontent.com/100506927/158538507-6c1f0dad-de9e-40bb-8ae0-82dd9559f493.png)

# Wallace Tree Symbol
![2022-03-01 (35)](https://user-images.githubusercontent.com/100506927/158539244-d3d30425-b084-496c-90bb-98867794379b.png)

# DC Analysis Testbench
![2022-03-01 (59)](https://user-images.githubusercontent.com/100506927/158539547-f88082e5-9fec-4a4d-8403-f12cc91fb6c9.png)

# Simulation Result
![2022-03-01 (61)](https://user-images.githubusercontent.com/100506927/158571750-52090a49-7ac3-4f21-acbf-db5da27fb98c.png)
![2022-03-01 (62)](https://user-images.githubusercontent.com/100506927/158574768-07c4c968-5e95-4aab-a0d5-04100709a1e3.png)

# Netlist
Refer to the netlist of the circuits here: [Netlist](https://github.com/Shivani327/CMOS-Implementation-of-8bit-Wallace-Tree-Multiplier/blob/main/Netlist)

# Author
Shivani, BTech Electronics and Communication Engineering, J.C. Bose University of Science and Technology, YMCA, Faridabad, Haryana.

# Acknowledgement
- [Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/)
- [Cloud Based Analog IC Design Hackathon](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/')
- [Synopsys India](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/')
- [Sameer Durgoji, NIT Karnataka](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/')
- [Chinmay panda, IIT Hyderabad](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/')

# References
- C.S. Wallace, A suggestion for a fast multiplier, IEEE Trans. Computers, Vol. 13, pp. 14-17, Feb. 1964.
- [Wikipedia](https://en.wikipedia.org/wiki/Wallace_tree)
- K. Prasad and K.K. Parhi, Low-power 4-2 and 5-2 compressors, Proc. of 2001 Asilomar Conf. on Signals, Systems and Computers, Pacific Grove, CA, USA.
- Neil H. Weste and Kamran Eshraghian, Principles of CMOS VLSI design-A Systems Perspective, Pearson Edition Pvt Ltd. 3rd edition.
- N. Sureka ; R. Porselvi ; K. Kumuthapriya, “An Efficient High Speed Wallace Tree Multiplier”, 2013 International Conference on Information Communication and Embedded Systems (ICICES). Technologies.
