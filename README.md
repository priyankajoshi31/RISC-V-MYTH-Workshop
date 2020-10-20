# RISC-V MYTH Workshop- Building a RISC-V core using TL-Verilog
The study of a basic RISC-V ISA and the implementation of a simple RISC-V core with base instruction set have been covered in the 5-day MYTH (Microprocessor for You in Thirty Hours) Workshop on RISC V based CPU Core Design organized by VLSI System Design (VSD) & Redwood EDA. The programming languages employed in the software section are C, Assembly Language, and some pseudo codes. 
The RISC-V CPU core has been designed with the aid of Transaction Level Verilog (TL-Verilog) along with the Makerchip IDE platform. All the information regarding this workshop has been incorporated into this repository as below. Tools used: Spike and Makerchip IDE.

## Table of Contents:

```
* Introduction to RISC-V Worksshop
* Day-1 Instruction Set Architecture & GNU Toolchain.
* Day-2 Application Binary Interface and basic verification flow.
* Day-3 Implementation of Digital logic with TL Verilog and Makerchip.
* Day-4 RISC-V CPU Core Micro-instructions and Implementation.
* Day-5 Pipelining the RISC-V Core Micro-instructions.
* Acknowledgements.
```

## Introduction to RISC V
RISC-V is an open standard instruction set architecture (ISA) based on established reduced instruction set computer (RISC) principles. Unlike most other ISA designs, the RISC-V ISA is provided under open source licenses.Notable features of the RISC-V ISA include a load–store architecture, bit patterns to simplify the multiplexers in a CPU, IEEE 754 floating-point, and placing most-significant bits at a fixed location to speed sign extension. The instruction set is designed for a wide range of uses. It is variable-width and extensible so that more encoding bits can always be added. It supports three word-widths, 32, 64, and 128 bits, and a variety of subsets.

### Advantage of RISC-V over ARM and X86 :

* RISC-V is open-source, there is no need to pay for the IP.
* RISC-V is far smaller than other commercial ISAs.
* RISC-V has a small standard base ISA, with multiple standard extensions.
* Base and first standard extensions are already frozen. There is no need to worry about major updates.
* Specific functions can be added based on extensions. There are many more extensions are under development, such as Vector.

### Makerchip Platform
Makerchip developed by Redwood EDA is a free online environment for developing high-quality integrated circuits. This platform can code, compile, simulate and debug Verilog designs from a browser and the code, block diagram and waveform are tightly integrated. It supports Transaction-Level Verilog (TL-Verilog), in addition to Verilog and synthesizable SystemVerilog.

![1](https://user-images.githubusercontent.com/73126590/96647739-ddd30080-134b-11eb-897f-038b9f6cb3ff.PNG)


### TL-Verilog
Transaction-Level Verilog (TL-Verilog) is an emerging extension to SystemVerilog that supports a new design methodology, called transaction-level design. In this project design TL-Verilog has been chosed as the HDL of choice with Makerchip IDE. Transaction Level Verilog standard is an extension of Verilog having advantages like simpler syntax, shorter code length and easy pipelining which results in less execution time. The main advantage of TL-Verilog over System Verilog is the code length reduction.

Timing abstract can be done in TL-Verilog, which is specified by pipelines in which the sequential elements are generated by tools from the pipelined specification. This allows for easy retiming without the risk of introduction of any functional bugs.

## DAY-1: Instruction Set Architecture & GNU Toolchain.

 
### Contents:
```
1. Introduction to RISC-V basic keywords
2. Labwork for RISC-V software toolchain
3. Integer number representation
4. Signed and unsigned arithmetic operations
```

The workshop began with the brief introductory session about the flow we would be following in making RISC-V CPU Core by @Kunalghosh and @Stevehoover.We were made familiar with the VSD-IAT platform and the lab instances we will be using for the design.

A brief overview of how the higher level languages are converted into assembly language followed by conversion into machine/binary format, and finally how it gets converted into a chip layout was explained by @Kunalghosh. We were introduced to RISC-V ISA and GNU Compiler Toolchain as well as with various types of RISC-V instructions sets, such as:

* **RV64I or RV32I Base integer instructions**: 64 and 32 bit data instructions respectively
* **RV64M**: Multiply extension
* **RV64IM**: Includes base and multiple extension.
* **RV64F and RV64D**: Floating point and Double extenstion.

Additionally we learnt about the signed and unsigned integer number representation and their maximum and minimum ranges for a 64bit instruction set.

### Integer:
* **Word**: 32 bits.
* **Double word**: 64 bits
RV64 range = 0 to (264 - 1)

* **Negative i.e signed numbers**:
Range = -263 to (263 - 1)

The instructions which work on these numbers are called Base Integer Instruction RV64I.

A CPU core implementing all the above type of instrcutions is called as **RV64IMFD CPU Core**.

# Lab Exercises

## Lab 1 : C program for the Sum of numbers from 1 to n
A basic C program to calculate sum of natural numbers upto a limit provided by the user. The code can be found here

### Commands used for compiling using GNU toolchain
1. Open a file named sum_1_to_n. using leafpad editor. `$leafpad sum_1_to_n.c`
2. Write your C code for sum of numbers from 1 to n (here n =9).
3. Compile using GNU compiler. `$gcc sum_1_to_n.c`
4. Run the compiled object file (Default object file formed with the name a.out). $./a/out

## Lab 2 : Sum of 1 to n using RISC-V compiler toolchain.
The C program for sum of 1 to n is now compiled using RISC-V toolchain. Spike simulator is used to run the object file , as well as a debugger.

### Commands for compiling using RISC-V simulator
1. To run the previously created program of sum_1_to_n.c program  using RISC-V simulator: 
`$riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum_1_to_n.o sum_1_to_n.c`

2. To check the assembly code for the C program that we are running,i.e to see the disassembled file, we run the following in a new tab in the terminal: 
`$riscv64-unknown-elf-objdump -d sum_1_to_n.o | less`

3. Type \main when the objdump file opens.
### Objdump file using -Ofast:
### Objdump file usinf -O1:

4. For running the object file compiled by RISC-V compiler, we are using the spike simulator. `$spike pk sum_1_to_n.o`

5. In order to debug all the assembly set instructions, we do it with the spike debugger.

`$spike -d pk sum_1_to_n.o`

## Lab 3 : To find the Max and Min unsigned and signed number representations.
A C program is implemented to show the maximum and minimum unsigned and signed number representations for a RV64I instruction. The code can be found here
Commands used are same as Lab 2.

## Final Output Results for Day_1 of the Workshop

1. Sum of numbers from 1 to n (n=9).

2. To find the maximum and minimumm number that can be represented using 64-bit unnsigned and signed integer number reperesentation.

## Day-2: Application Binary Interface and verification

### Contents:
```
1. Application Binary interface (ABI)
2. Lab work using ABI function calls
3. Basic verification flow using iverilog
```

On Day-2, we way down into understanding the lower layers on how the higher layer instructions in C are translated to machine understandable codes. Just like how Application Program Interface (API) is used by application programs to access the standard libraries, an Application Binary Interface(ABI) , aslo called as System call interface is utilised to access the hardware resources. The ISA is divided into two parts: User & System ISA and User ISA. User ISA is available to the programmer directly through system calls.

How the ABI access the hardware resources?

It uses different registers out of available 32 which are each of width `XLEN = 32 bit` for RV32 (~`XLEN = 64 for RV64`). On a higher level of abstraction these registers are accessed by their respective ABI names.

In RISC-V architecture, the memories are byte addressable. The RISC-V belongs to the little endian memory addressing system.

For base integer instructions there are broadly 3 types of of such registers:

* **I-type** : For instructions having immediate values as operands.
* **R-type** : For instructions having only registers as operands.
* **S-type** : For instructions used for storing operations.
### Snapshot of Modified custom C prorgram and "load.S" Assembly language program

## Lab 1 : ASM & ABI function Calls
A new program is made by modifying the original `sum1ton.c` and adding ASM and ABI function call .The code can be found here

* Command used to compile the program is `riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o 1to9_custom.o 1to9_custom.c load.S`.
* Use command `riscv64-unknown-elf-objdump -d 1to9_custom.o|less` to disassemble and view the object file in readable format.
* To run we use spike which is a RISC-V simulator, use command `spike pk 1to9_custom.o`.

## Lab 2 : To run and verify on a RISC-V Core

An RTL implementation of a RISC-V core has been provided to us and we run the above program using the scripts provided to using iverilog simulator, just to observe the behaviour of the program in hardware. A similar core would be implemented by us in the forthcoming days.

## Day-3: Digital Logic with TL-Verilog and Makerchip

### Contents:
```
1. Combinational logic in TL-Verilog using Makerchip
2. Sequential and pipelined logic
3. Validity
4. Hierarchy
```
An introduction to TL-Verilog with implemention of basic combinational and sequential logic.Finally implementating a sequential cyclic calculator. Makerchip IDE, which is an open source tool developed by Redwood EDA was utilised for this.
TL-Verilog is an extension for System Verilog, moreover it acts as an higher level abstraction for System verilog which makes HDL implementation very easy and error free. Here we deal the design at a transaction level assuming the design as a pipeline, where inputs would be provided and output will be generated at the end of the pipeline.

### Advantages :

* Code reduction , and thus less chances of being bug prone.
* In pipelining ,the flip flops,registers and other staged signals are implied from the context.
* It's very easy to stage different sections without impacting the behaviour of the logic.
* Validity feature which provides easier debugging, cleaner design, automated clock gating and better error checking capabilities.

### Lab Exercises:
### 1. Combinational Logic Example: Full Adder
### 2. Combinational Calculator
### 3. Sequential Logic Example: Fibonacci Series
### 4. Sequential Calculator
### 5. A Simple Pipeline through Pythagorous Theorem
### 6. Implementation of Pipelining throuh TL-Verilog
### 7. 2-Cycle Calculator
### 8. Example : Distance Acculmulator
### 9. 2-Cycle Calculator with validity
### 10. Calculator with Single Value Memory

## Day-4: Basic RISC-V CPU micro-architecture and Implementation

### Contents:
```
1. Microarchitecture and testbench for a simple RISC-V CPU
2. Fetch, decode, and execute logic
3. RISC-V control logic
```

After having a strong basics built in TL-Verilog and digital design, and getting completely familiar with the Makerchip Platform, finally we move to the core aspect of the workshop, i.e. to build a RISC V core. On this day, the instruction set architecture of base integer instructions, next_pc logic, the register file, ALU, branch instructions, etc. and eventually the CPU core was built and tested, using appropriate testbench logic, and assembly code developed on Day 2. The codes can be found here.

### Lab Exercises:
### 1. Next PC Logic
### 2. Instruction Fetch Logic
### 3. Instruction Decode
### 4. Register File Read
### 5. Arithmetic and Logic Unit(ALU)
### 6. Register File Write
### 7. Branch Instructions
### Final Output: RISCV Core
The final RISC-V CPU core (without pipelining) has been completely implemented.

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

The final code can be found here.

### Final Day_5 Output
### Final Implemention of RISC-V CPU Core
