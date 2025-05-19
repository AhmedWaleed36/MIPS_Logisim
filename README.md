# 🧠💻 Single Cycle MIPS CPU — Design & Implementation

## 📌 Project Overview

This project showcases the complete implementation of a Single-Cycle MIPS CPU, built around a simplified MIPS architecture. It supports a subset of 24 instructions:

    - 🧮 14 R-type

    - 📥 9 I-type

    - 🚀 1 J-type

It demonstrates key computer architecture principles including:

    - Data Path Design

    - Control Logic

    - Circuit Component Implementation

## ✨ Features

✅ Full single-cycle CPU simulation
✅ Supports 24 MIPS instructions
✅ Designed in Logisim for digital simulation
✅ Tested with MARS (MIPS Assembler and Runtime Simulator)
🧩 Architecture Design
🔁 1. Data Path

The data path represents how data flows through the CPU during execution:

    🚦 Starts at the Program Counter (PC)

    📜 Fetches instruction from memory

    🎯 Decoded by the Register File

    🔧 Processed by the ALU or control logic, depending on instruction type:

        - 🧮 R-type: Registers → ALU → Destination Register

        - 🧾 I-type: Register + Immediate → ALU

        - 🧭 J-type: ALU calculates new PC address

    🔀 PC path selected via multiplexer based on instruction type

## ⚙️ 2. Core Components

    - 🧱 Register File

    - 📍 Program Counter

    - 🧾 Instruction Memory

    - 🗃️ Data Memory

    - 🧮 Arithmetic Logic Unit (ALU)

    - 🎛️ ALU Control Unit

    - 🧭 PC Control Unit

    - 🕹️ Main Control Unit

## 🧠 3. Control Logic
### 🕹️ Main Control Unit

   - Decodes opcodes

   - Generates signals: Jump, BEQ, BNE, ALUSrc, ALUOp, etc.

   - Controls instruction flow in the ID (Instruction Decode) stage

### 🧭 PC Control Unit

   - Calculates next PC address

   - Uses flags (Zero, Jump, Branch) to control flow

   - Handles jump, branch equal/not equal logic

### 🔧 ALU Control Unit

    - Selects ALU operations based on control signals + function bits

    - Controls logic during EX (Execution) stage

## 🧠 Component Circuit Implementations
### 🗂️ 1. Register File

    - 32 × 32-bit general-purpose registers

    - 🧮 Dual-read ports (Ra, Rb)

    - ✍️ Write port (Rw + BusC + RegWrite)

    - 🧠 Decoder for register selection

    - 🕒 Signals: Clk, Reset, RegWrite

### ➕ 2. ALU Circuit

    - Performs add, sub, and logical ops (AND, OR, SLT)

    - 🌐 32-bit ALU built from 1-bit slices

    - 🚩 Zero detection for branching

### 🎚️ 3. ALU Control Circuit

    - Inputs: ALUOp (4-bit), Funct (6-bit)

    - Logic + MUXes to output ALU control signals

### 🧭 4. Program Counter Circuit

    - Calculates next instruction address

    - Supports jumps, branches, and sequential flow

    - Built using adders, MUXes, and logic gates

### 🧩 5. Main Control Unit Circuit

    - Interprets opcodes

    - Controls execution via signals like:

        RegDst, ALUSrc, MemToReg, RegWrite

        MemRead, MemWrite, Branch, Jump

## 📊 Control Tables
### 🧾 Main Control Table

Includes control signal mappings for instruction types:

   - RegDst, MemWrite, MemRead, MemToReg, RegWrite

   - Jump, BNE, BEQ, ALUSrc, ExtOp, ALUOp

### 🔧 ALU Control Table

Maps ALUOp and Funct to operations:

    - AND → (000, 0)

    - OR → (001, 0)

    - XOR → (010, 0)

    - ADD → (100, 0)

    - SUB → (100, 1)

    - SLT → (101, 1)

## 🧪 Simulation & Testing
### 💻 Development Environment

    - 🔌 Logisim — for circuit design

    - 🧾 MARS — for writing & assembling MIPS code

### 🛠️ Implementation Steps

    - Write & compile assembly in MARS

    - Extract hex output

    - Load hex into Logisim instruction memory

    - 🔍 Simulate & observe CPU behavior

### 🚀 Usage Instructions

   - Open circuit in Logisim

   - Load hex-formatted assembly code

   - Start simulation

    Monitor:

        🔢 Register values

        🧠 Instruction flow

        🗃️ Memory changes

### 🛠️ Requirements

    🧰 Logisim

    💾 MARS MIPS Simulator

## 👨‍💻 Authors

    🧑‍💻 Ahmed Khaled Mohamed

    🧑‍💻 Ahmed Waleed Ahmed

    🧑‍💻 Hazem Ahmed Abdelfattah

    🧑‍💻 Saeed Khalid Awaad

## 🎓 Supervision

    👩‍🏫 Dr. Lamiaa Elrefaai

    👩‍🔧 Eng. Shimaa Yosry

📜 License

This project was developed as part of academic coursework at Benha University, Shoubra Faculty of Engineering, Communication and Computer Engineering Department.

📘 Note: For full implementation details and diagrams, please refer to the accompanying project report.