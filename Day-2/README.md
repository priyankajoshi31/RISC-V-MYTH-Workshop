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
A new program is made by modifying the original `sum1ton.c` and adding ASM and ABI function call .The code can be found [here](https://github.com/priyankajoshi31/RISC-V-MYTH-Workshop/blob/main/code/day2/sum1to9.c)

* Command used to compile the program is `riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o 1to9_custom.o 1to9_custom.c load.S`.
* Use command `riscv64-unknown-elf-objdump -d 1to9_custom.o|less` to disassemble and view the object file in readable format.
* To run we use spike which is a RISC-V simulator, use command `spike pk 1to9_custom.o`.

## Lab 2 : To run and verify on a RISC-V Core

An RTL implementation of a RISC-V core has been provided to us and we run the above program using the scripts provided to using iverilog simulator, just to observe the behaviour of the program in hardware. A similar core would be implemented by us in the forthcoming days.
