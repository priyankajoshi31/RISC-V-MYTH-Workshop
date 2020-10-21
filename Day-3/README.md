
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

![3](https://user-images.githubusercontent.com/73126590/96648164-9731d600-134c-11eb-8645-a227b1fa49a2.PNG)

### Lab Exercises:
### 1. Combinational Logic Example: Full Adder
![1](https://user-images.githubusercontent.com/73126590/96648421-f4c62280-134c-11eb-924b-488ce188dd8e.PNG)

### 2. Combinational Calculator
![2](https://user-images.githubusercontent.com/73126590/96648477-06a7c580-134d-11eb-8410-5de23db5b879.PNG)

### 3. Sequential Logic Example: Fibonacci Series
![3](https://user-images.githubusercontent.com/73126590/96648531-1cb58600-134d-11eb-9877-f3b4a6263123.PNG)

### 4. Sequential Calculator
![4](https://user-images.githubusercontent.com/73126590/96648581-2f2fbf80-134d-11eb-8244-34397d536651.PNG)

### 5. A Simple Pipeline through Pythagorous Theorem
![5](https://user-images.githubusercontent.com/73126590/96648637-4373bc80-134d-11eb-91fa-80f56c74252a.PNG)

### 6. Implementation of Pipelining throuh TL-Verilog
![6](https://user-images.githubusercontent.com/73126590/96648672-51c1d880-134d-11eb-9ceb-18c4e3aeadf5.PNG)

### 7. 2-Cycle Calculator
![7](https://user-images.githubusercontent.com/73126590/96648705-61d9b800-134d-11eb-9d0f-a09abd3ae623.PNG)

### 8. Example : Distance Acculmulator
![8](https://user-images.githubusercontent.com/73126590/96648710-64d4a880-134d-11eb-87b4-6cd8fa0280f9.PNG)

### 9. 2-Cycle Calculator with validity
![9](https://user-images.githubusercontent.com/73126590/96648759-7c139600-134d-11eb-8829-8aea651be43b.PNG)

### 10. Calculator with Single Value Memory
![10](https://user-images.githubusercontent.com/73126590/96648769-7ddd5980-134d-11eb-8733-fc19cabf1ae5.PNG)
