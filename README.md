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
