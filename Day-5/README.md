## Day 5: Complete Pipelined RISC-V CPU micro-architecture

### Contents:
 ```
 1. Pipelining the CPU
 2. Load and store instructions and memory
 3. Completing the RISC-V CPU
 4. Wrap-up and future opportunities
``` 

Implementing the pipelining technique and some additonal instructions for the RISC-V core developed on Day-4. The above architecture is pipelined as follows :
* A 3 cycle RISC V pipelined core, with all the base integer instruction sets was developed.
* For Load and store a Data memory element was added with neccessary instruction decoding logic.
* Register Bypass and Squashing techniques were also incorporated to prevent Read followed by write and branchinghazards, arised due to pipelining.
* Testing of the pipeline design was done in same manner with Load and store incorporated in asm code.
* Additionally Incorporation of Jump feature (JAL and JALR instructions) was also done.

The final code can be found [here](https://github.com/priyankajoshi31/RISC-V-MYTH-Workshop/blob/main/code/Final_code_RISCV_Core.v).

### Final Day_5 Output
![1](https://user-images.githubusercontent.com/73126590/96649177-3dcaa680-134e-11eb-8493-95cbbb8a0f5c.png)

### Final Implemention of RISC-V CPU Core
![2](https://user-images.githubusercontent.com/73126590/96649191-428f5a80-134e-11eb-9e1c-a7b45fac1431.png)
