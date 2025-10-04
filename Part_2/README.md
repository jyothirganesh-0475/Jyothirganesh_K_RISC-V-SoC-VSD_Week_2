# Part 2 – BabySoC Functional Modelling (Labs)

This section contains the **hands-on work** for simulating BabySoC using **Icarus Verilog** and **GTKWave**.

---

## ⚙️ Tools Used

* 🖥 **Icarus Verilog (iverilog)** – For compiling and simulating Verilog code.
* 📈 **GTKWave** – For viewing waveform dumps (`.vcd` files).

---

## 🎯 Problem Statement

This project focuses on designing a **compact, open-source System-on-Chip (SoC)** based on **RVMYTH**, a RISC-V-based processor core.

The SoC integrates:

* ⏱ **Phase-Locked Loop (PLL)** for precise clock generation and control
* 🎚 **10-bit Digital-to-Analog Converter (DAC)** for analog interfacing

By converting digital signals into analog, the DAC enables BabySoC to communicate with **external analog devices** such as televisions, audio systems, and mobile phones.
This makes BabySoC an **educational platform** that bridges the gap between digital and analog design for SoC learners.

---
## Steps Performed
1. Cloned the BabySoC repo Project.
2. TLV to Verilog Conversion for RVMYTH.
3. Created an **output directory**:  
4. Compiled the Verilog design files using `iverilog`.  
5. Ran simulation and generated `.vcd` waveform files.  
6. Opened `.vcd` in GTKWave and analyzed signals.
---

## 📂 Project Structure

```text
VSDBabySoC/
├── src/
│   ├── include/                 # Header files (.vh) with macros and parameter definitions
│   │   ├── sandpiper.vh
│   │   └── other header files...
│   ├── module/                  # Verilog/TLV modules
│   │   ├── vsdbabysoc.v         # Top-level module integrating all SoC components
│   │   ├── rvmyth.v             # RISC-V (RVMYTH) core module (converted from TLV)
│   │   ├── avsdpll.v            # PLL module for clock generation
│   │   ├── avsddac.v            # DAC module for analog output
│   │   └── testbench.v          # Testbench for simulation
├── output/                      # Directory for compiled outputs and simulation results
└── compiled_tlv/                # Intermediate TL-Verilog compiled files (if needed)
```

---

## 🛠️ Step 1 – Cloning the Project

To begin, clone the **VSDBabySoC repository**:

```bash
cd ~/VLSI
git clone https://github.com/manili/VSDBabySoC.git
cd ~/VLSI/VSDBabySoC/
```

Check repository contents:

```bash
jyothirganesh@jyothirganesh:~/VLSI$ ls VSDBabySoC/
images  LICENSE  Makefile  README.md  sp_env  src
```

Check `src/module` directory:

```bash
jyothirganesh@jyothirganesh:~/VLSI$ ls VSDBabySoC/src/module/
avsddac.v  clk_gate.v  pseudo_rand.sv  rvmyth.tlv  testbench.rvmyth.post-routing.v  vsdbabysoc.v
avsdpll.v  pseudo_rand_gen.sv  rvmyth_gen.v    rvmyth.v    testbench.v
```

---

## 🔧 Step 2 – TL-Verilog to Verilog Conversion (RVMYTH Core)

The **RVMYTH core** is initially provided in **TL-Verilog** (`rvmyth.tlv`).

Steps performed:

1. Installed and set up a **Python virtual environment**
2. Installed **SandPiper-SaaS** for TLV → Verilog conversion
3. Converted `rvmyth.tlv` into `rvmyth.v` using:

```bash
sandpiper-saas -i ./src/module/*.tlv -o rvmyth.v \
--bestsv --noline -p verilog --outdir ./src/module/
```

✅ Verified that `rvmyth.v` was generated successfully in `src/module/`.

---

## ▶️ Step 3 – Pre-Synthesis Simulation

1. Created an **output directory**:

```bash
mkdir -p output/pre_synth_sim
```

2. Compiled the Verilog design and testbench with **Icarus Verilog**:

```bash
iverilog -o output/pre_synth_sim/pre_synth_sim.out \
-DPRE_SYNTH_SIM \
-I src/include -I src/module src/module/testbench.v
```

3. Ran the simulation:

```bash
cd output/pre_synth_sim
./pre_synth_sim.out
```

👉 This generated a waveform dump file: **`pre_synth_sim.vcd`**

---

## 👀 Step 4 – Waveform Analysis with GTKWave

Opened the VCD in GTKWave:

```bash
gtkwave output/pre_synth_sim/pre_synth_sim.vcd
```

### Signals Observed

* ⏱ **CLK** – Input clock signal to RVMYTH (from PLL)
* 🔄 **reset** – External reset signal
* 🔟 **RV_TO_DAC[9:0]** – 10-bit data output from RVMYTH register #17 to DAC
* 📤 **OUT** – DAC output signal (digital in simulation, step-like analog view in GTKWave)

---

## 🔎 Step 5 – Observations

### 🔹 Reset Operation

* **Screenshot 1** – Shows that all registers are cleared during reset.
* After reset is deasserted, normal SoC operation begins.

### 🔹 Clocking

* **Screenshot 2** – Clock toggling consistently.
* All modules synchronize operations with clock edges.

### 🔹 Dataflow Between Modules

* **Screenshot 3** – Verified correct data transfer: **RVMYTH → DAC → OUT**.
* Output signal visualized in **Analog → Step mode** in GTKWave.

---

## 🚑 Troubleshooting Notes

* ⚠️ **Module Redefinition** – Avoid including the same module twice.
* 📂 **Path Issues** – Ensure `-I` include directories are correct; absolute paths may help.

---

## ✅ Final Deliverables

* 📜 **Simulation Logs** – Output from compilation and execution
* 🖼 **GTKWave Screenshots** – Reset, clock, and dataflow behavior
* 📝 **Explanations** – Each screenshot documented with observed BabySoC behavior

---

## 🎓 Summary of Week 2 (Labs)

✔️ Set up **VSDBabySoC project structure**
✔️ Installed & configured **SandPiper-SaaS**
✔️ Converted **RVMYTH TLV → Verilog**
✔️ Performed **pre-synthesis simulation** with Icarus Verilog
✔️ Opened & analyzed waveforms in **GTKWave**
✔️ Verified **reset, clock, and dataflow**
✔️ Documented **observations + troubleshooting tips**

✨ BabySoC **functional modelling** was successfully completed and verified.

---


