
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
A basic C program to calculate sum of natural numbers upto a limit provided by the user. The code can be found [here](https://github.com/priyankajoshi31/RISC-V-MYTH-Workshop/blob/main/code/day1/sum1ton.c)

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
A C program is implemented to show the maximum and minimum unsigned and signed number representations for a RV64I instruction. The code can be found [here](https://github.com/priyankajoshi31/RISC-V-MYTH-Workshop/blob/main/code/day1/highest_unsigned.c)
**Commands used are same as Lab 2.**

## Final Output Results for Day_1 of the Workshop

1. Sum of numbers from 1 to n (n=9).

2. To find the maximum and minimumm number that can be represented using 64-bit unnsigned and signed integer number reperesentation
