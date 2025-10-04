# Week 2 – BabySoC Fundamentals & Functional Modelling

This repository contains the deliverables for **Week 2** of the BabySoC learning journey.  

## 🎯 Objectives
The main goals of this week are:
- To gain a **solid conceptual understanding** of **System-on-Chip (SoC) fundamentals**.  
- To practice **functional modelling** of the BabySoC using open-source simulation tools like **Icarus Verilog (iverilog)** and **GTKWave**.  

---

## 🏗️ Introduction to the VSDBabySoC
The **VSDBabySoC** is a **simplified, RISC-V based System-on-Chip (SoC)** created for educational and research purposes.  

### ✨ Key Highlights
- Built around the **RVMYTH RISC-V microprocessor** core.  
- Integrates an **8x Phase-Locked Loop (PLL)** to generate a stable high-frequency clock.  
- Includes a **10-bit DAC (Digital-to-Analog Converter)** to interface with analog devices.  

The primary motivation for BabySoC is:
- To demonstrate **integration of multiple open-source IP cores** on a single SoC.  
- To provide a **minimal but functional SoC model** that learners can simulate and study before exploring more complex SoCs.  
- To **calibrate the analog components** in sync with the digital system.  

---

## 📂 Repository Structure
- **[part1](https://github.com/jyothirganesh-0475/Jyothirganesh_K_RISC-V-SoC-VSD_Week_2/tree/main/Part_1)** – Theory write-up: *Conceptual understanding of SoC design and the role of BabySoC in learning.*  
- **[part2](https://github.com/jyothirganesh-0475/Jyothirganesh_K_RISC-V-SoC-VSD_Week_2/tree/main/Part_2)** – Labs: *Hands-on functional modelling of BabySoC (simulation, waveforms, and analysis).*  

---

## ✅ Expected Outcomes
By the end of this week, you should be able to:
- **Explain** what an SoC is, its **main components**, and why BabySoC is a good entry point for learning.  
- **Understand** the role of **functional modelling** before RTL and physical design stages.  
- **Simulate** BabySoC Verilog modules, generate and analyze **waveforms** (reset, clock, dataflow) using GTKWave.  
- **Document** observations with logs, screenshots, and explanations.  

---

## 🔧 Tools Used
- **Icarus Verilog (iverilog)** – Compiling and simulating Verilog code.  
- **GTKWave** – Viewing `.vcd` waveform dumps for signal analysis.  
- **GitHub** – Version control and documentation.  

---
By the end of this week:
- You should be able to **explain what an SoC is, its components, and why functional modelling is essential**.  
- You should also be able to **simulate BabySoC modules, analyze reset/clock/dataflow waveforms, and document the observations**.

📌 *This repository is part of the Risc-v-SoC-VSD “BabySoC Journey” and builds a foundation for deeper exploration into SoC design, RTL development, and physical implementation.*


