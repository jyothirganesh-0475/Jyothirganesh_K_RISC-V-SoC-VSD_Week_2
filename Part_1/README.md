# Week 2 – Part 1: Fundamentals of SoC Design(Theory (Conceptual Understanding))

## 🏗️ Introduction to the VSDBabySoC
The **VSDBabySoC** is a **simplified, RISC-V based System-on-Chip (SoC)** created for educational and research purposes.  

## 🤔 What is a System-on-Chip (SoC)?
A **System-on-Chip (SoC)** is an integrated circuit that brings together all the essential components of a computing system onto a single silicon die. Instead of using multiple separate chips, an SoC integrates:

- **CPU (processor core)** for computation and control  
- **Memory modules** for storing data and instructions  
- **Peripherals** for communication with external devices  
- **Interconnect fabric** to enable data transfer between components  

### ✨ Benefits of SoCs
- 🔹 **Reduced size** – compact and space-efficient  
- 🔹 **Lower power consumption** – suitable for mobile/embedded systems  
- 🔹 **Improved performance** – faster communication due to on-chip integration  

SoCs power modern technologies like **smartphones, IoT devices, automotive electronics, and embedded systems**.  

---

## 🛠 Components of a Typical SoC (CPU, memory, peripherals, interconnect).
1. **💻 CPU (Central Processing Unit)**  
   - The “brain” of the SoC.  
   - Executes instructions and manages system operations.  

2. **🧠 Memory**  
   - **Volatile (RAM):** temporary data storage.  
   - **Non-volatile (ROM/Flash):** permanent storage of instructions and data.  

3. **📡 Peripherals**  
   - Interfaces for external communication such as **UART, SPI, I²C, GPIO, timers**.  

4. **🔗 Interconnect**  
   - The communication backbone (bus or **Network-on-Chip**) linking CPU, memory, and peripherals.  

---

## 🔲 Why BabySoC  is a simpliﬁed model for learning SoC concepts ?
The **BabySoC** is a simplified SoC model created for **educational and experimental learning**.  

- Strips away unnecessary complexity while **retaining the essential SoC architecture**.  
- Demonstrates how **CPU, memory, and peripherals interact**.  
- Acts as a **bridge between theory and real-world SoCs**.  
- Allows beginners to explore SoC design **without being overwhelmed** by advanced features.  

👉 In short, BabySoC = *minimal but powerful model to learn SoC fundamentals*.  

---

## ⚙️The role of functional modelling before RTL and physical design stages.
Before diving into RTL coding and physical design, engineers perform **functional modelling**.  
This stage validates the **conceptual behavior** of the system.  

### Why Functional Modelling is Important:
- ✅ **Verify functionality** early, ensuring correct design intent.  
- 🛑 **Catch design flaws** before costly hardware implementation.  
- 🔄 **Enable faster iteration**, since changes are easier at higher abstraction.  

**Tools like Icarus Verilog and GTKWave** provide an accessible environment to:  
- Simulate SoC modules  
- Observe signals (reset, clock, dataflow)  
- Validate expected behavior  

---

## 🎯 Conclusion
- **SoC Fundamentals:** A System-on-Chip integrates CPU, memory, peripherals, and interconnect on a single chip for efficiency and performance.  
- **BabySoC:** A simplified SoC model that makes learning SoC design approachable.  
- **Functional Modelling:** A crucial step that ensures correctness before RTL and physical implementation.  

📌 With BabySoC and functional modelling, learners gain both **theoretical knowledge** and **practical skills**, laying the foundation for advanced SoC development.  
