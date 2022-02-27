# Design and Simulation of NAND gate on CMOS 28nm Technology

## Table of Contents
- [ Abstract](https://linktodocumentation)
- [Introduction](https://linktodocumentation)
- [Circuit Design](https://linktodocumentation)
- [Simulation Results](https://linktodocumentation)
- [Netlist](https://linktodocumentation)
- [Conclusion](https://linktodocumentation)
- [Acknowledgements](https://linktodocumentation)
- [References](https://linktodocumentation)

##  Abstract
Real world signals are mostly based on Boolean
Operators. Boolean Operators are simple words (AND, OR,
NOT or AND NOT) used as conjunctions to combine or
exclude keywords in a search, resulting in more focused and
productive results. Especially, the work is focused NAND gate
on reduction of power dissipation, which is showing the effect
of transient fault on selected NMOS transistor and PMOS
transistor duplication and scaling connected to the same
input.. All the above
circuits are implemented using 28nm CMOS
technology using a supply voltage of 1.1v Vdc in
Synopsys TOOL.

Keywords-NAND gate, Synopsys tool



## Introduction

The NAND or “Not AND” function is a combination
of the two separate logical functions, the AND function and
the NOT function connected together in series.
![Screenshot (35)](https://user-images.githubusercontent.com/92818847/155886289-4eaf57ff-a010-4f72-9ce2-bb19b514b0af.png)
</p>
<p align="center">
Fig 2. NAND gate Symbole
</p>
Figure 1: Symbol of NAND gate
Power consumption plays an important role and it
affects proportionally to the performance of the circuit. The
duplication and scaling means adding of transistors i.e
connecting transistor in parallel or series to NAND gate. This
paper is organized into four sections.The design of a
conventional NAND gate using 28m CMOS
technology.  Duplication
and scaling of NAND gate using 28m CMOS
technology, with the implementation and
results using Synopsystool.


##  Circuit Design


![Screenshot (36)](https://user-images.githubusercontent.com/92818847/155886667-9c6eb106-1c58-42ad-910c-bde5536b6807.png)

</p>
<p align="center">
Fig 2. schematic
</p>

Considering the truth table; Case:1)  When A=B=0,both the NMOS are in off condition and PMOS are in on condition. Therefore the output is connected to vdd 1.8v and 1.1v HIGH logic is present at the output terminal.Case:2) When A=0 and B=1, the upper NMOS are in off  and lower NMOS is on condition. Left PMOS are in on and right PMOS in off condition. Therefore the output is connected to vdd and HIGH logic is present at the output terminal. Case:3) When A=1 and B=0,upper NMOS are in on and lower  NMOS is off condition. Left PMOS are in off and right PMOS are in on condition. Therefore the ouput is connected to vdd and HIGH logic is present at the output terminal. Case :4) When A=B=1 , both the NMOS are in on condition and PMOS are in off condition. Therefore the output is  connected to vdd and LOW logic is present connected to vdd and LOW logic is present at the output terminal.   


## Simulation Results


 ![Screenshot (27)](https://user-images.githubusercontent.com/92818847/155886818-c32eb359-723d-47d4-875b-7d15c8245da7.png)

</p>
<p align="center">
Fig 3.  simulation input and output waveforms
</p>


![Screenshot (28)](https://user-images.githubusercontent.com/92818847/155887315-ac41a7b0-e84c-4aa8-8e23-a2fd1df683c4.png)

<p align="center">
Fig 4. Testbench 


##  Netlist


*  Generated for: PrimeSim
*  Design library name: NAND_Gate
*  Design cell name: NAND_Gate_testbench
*  Design view name: schematic

*Custom Compiler Version S-2021.09


.global gnd!
********************************************************************************
* Library          : NAND_Gate
* Cell             : NAND_Gate
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt nand_gate va vb vout gnd_1 vdd
xm5 vout va vdd vdd p105 w=0.3u l=0.03u nf=1 m=1
xm4 vout vb vdd vdd p105 w=0.3u l=0.03u nf=1 m=1
xm7 net11 va gnd_1 gnd_1 n105 w=0.3u l=0.03u nf=1 m=1
xm6 vout vb net11 gnd_1 n105 w=0.3u l=0.03u nf=1 m=1
.ends nand_gate

********************************************************************************
* Library          : NAND_Gate
* Cell             : NAND_Gate_testbench
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xi0 va vb vout gnd! net10 nand_gate
vb vb gnd! dc=0 pulse ( 0 1.8 0 0.1u 0.1u 10u 20u )
v8 va gnd! dc=0 pulse ( 0 1.8 0 0.1u 0.1u 5u 10u )
v10 net10 gnd! dc=1.1
.tran '1u' '40u' name=tran


## Conclusion

The Average power and Delay of NAND gate is
represented in 180nm and 90nm CMOS technology using
TANNER EDA tool.The Simulation results shows the
Comparison of Delay and Average power of Conventional,
Duplication and scaling with  1.1v VDD. The
Duplication and scaling can be used to minimize Average
power and Delay in NAND gate.


## Acknowledgements

- [Kunal Ghosh, Co-founder, VSD Corp. Pvt Ltd.]
- Chinmay Panda, IIT Hyderabad
- [Synopsis Team/Company](synopsys.com/company/contact-synopsys/office-locations/india/about-synopsys-india.html)
- [IIT Hyderabad](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/)

## References

1.	KrashnaNandMishra “Efficient Carrying Generation technique Incorporation Energy Recovering Logic Circuitry for Low Power VLSI”.IEEE,2008.
2.	Debaprasad Das “VLSI Design” published by Oxford University Press 2010.
3.	Taub’s Principles of  Communication Systems   Fourth Edit ion

