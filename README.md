# RISC-V MYTH Workshop- Building a RISC-V core using TL-Verilog

This repository contains all the information regarding the 5-day RISC-V based CPU Core Design MYTH (Microprocessor for You in Thirty Hours) Workshop, offered by for VLSI System Design (VSD) and Redwood EDA. In a short span of 5-days, the basic RISC-V ISA was studied & a simple RISC-V core with base instruction set was implemented. Under the software section, the programming languages that have been used are C, Assembly language and some Pseudo codes. The RISC-V CPU Core has been designed with the help of Transaction Level Verilog(TL-Verilog) in addition with the Makerchip IDE Platform. Find below the accompanying details.

My Project Repository for RISC-V MYTH ( Microprocessor for You in Thirty Hours) workshop, conducted by VSD Corp and Redwood EDA.This workshop was conducted over a period of 5 days and in this short span of time we were able to understand & implement a RISC-V core with base instruction set. Programming language used in the software section was C, assembly (pseudo codes) were also utilised, along with TL-Verilog for HDL implementation. Tools used: Spike and Makerchip IDE.

## Table of Contents

* Introduction to RISC-V
* Day 1 Instruction Set Architecture & GNU Toolchain.
* Day 2 Application Binary Interface and basic verification flow.
* Day 3 Implementation of Digital logic with TL Verilog and Makerchip.
* Day 4 RISC-V CPU Core Micro-instructions and Implementation.
* Day 5 Pipelining the RISC-V Core Micro-instructions.
* Acknowledgements.

Introduction to RISC V
RISC-V is an open standard instruction set architecture (ISA) based on established reduced instruction set computer (RISC) principles. Unlike most other ISA designs, the RISC-V ISA is provided under open source licenses.

Advantage of RISC-V over ARM and X86 :

Free: RISC-V is open-source, there is no need to pay for the IP.
Simple: RISC-V is far smaller than other commercial ISAs.
Modular: RISC-V has a small standard base ISA, with multiple standard extensions.
Stable: Base and first standard extensions are already frozen. There is no need to worry about major updates.
Extensibility: Specific functions can be added based on extensions. There are many more extensions are under development, such as Vector.

Makerchip Platform
Makerchip is a free online environment by Redwood EDA for developing high-quality integrated circuits. The online platform can be used to code, compile, simulate and debug Verilog designs from a browser. It gives you a place to create any digital sequential logic you can dream up faster than you ever thought was possible, all within your browser. The breakthrough in productivity is two fold:

A tight integration of design, simulation, and debug capabilities
Support for Transaction-Level Verilog (TL-Verilog), in addition to Verilog and synthesizable SystemVerilog.

TL-Verilog
Transaction-Level Verilog (TL-Verilog) is an emerging extension to SystemVerilog that supports a new design methodology, called transaction-level design. For this project, TL-Verilog has been chosed as the HDL of choice for the design. Projects on Makerchip can be completely designed using TL-Verilog. Transaction Level Verilog standard is an extension of Verilog which has various advantages like simpler syntax, shorter codes and easy pipelining. Tha main advantage of TL-Verilog over System Verilog is the amount of code reduction in designing even a simple model.

Timing abstract can be done in TL-Verilog. This model is specified for pipelines where the sequential elements are generated by tools from the pipelined specification. This allows for easy retiming without the risk of introduction of any functional bugs. More information on timing abstract in TL-Verilog can be found in the IEEE paper "Timing-Abstract Circuit Design in Transaction-Level Verilog" by Steven Hoover".
