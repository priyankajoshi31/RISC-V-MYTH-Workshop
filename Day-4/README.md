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
![1](https://user-images.githubusercontent.com/73126590/96648863-a9604400-134d-11eb-8304-27f56991d556.PNG)

### 2. Instruction Fetch Logic
![2](https://user-images.githubusercontent.com/73126590/96648907-bd0baa80-134d-11eb-8e3c-74d334b6d5db.PNG)

### 3. Instruction Decode
![3](https://user-images.githubusercontent.com/73126590/96648949-cdbc2080-134d-11eb-8ef0-9517ae531d88.png)

### 4. Register File Read
![4](https://user-images.githubusercontent.com/73126590/96648956-d0b71100-134d-11eb-82ab-7cf31c67742e.png)

### 5. Arithmetic and Logic Unit(ALU)
![5](https://user-images.githubusercontent.com/73126590/96649024-f217fd00-134d-11eb-8834-10ad765ca3d6.png)

### 6. Register File Write
![6](https://user-images.githubusercontent.com/73126590/96649032-f6441a80-134d-11eb-9b54-f17776ace620.png)

### 7. Branch Instructions
![7](https://user-images.githubusercontent.com/73126590/96649039-f9d7a180-134d-11eb-9ced-f25f494fb6cc.png)

### Final Output: RISCV Core
The final RISC-V CPU core (without pipelining) has been completely implemented.
![8](https://user-images.githubusercontent.com/73126590/96649044-fc39fb80-134d-11eb-9e77-eb62e76aa828.png)
