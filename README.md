# Pipelined RISC-V Instruction Execution

## 🚀 Overview

This project builds on the Phase 2 implementation of a RISC-V simulator and extends it to support **pipelined execution**. The simulator includes support for key pipelining features such as:
- Pipeline registers (inter-stage buffers)
- Data forwarding
- Hazard detection & stalling
- Pipeline flushing
- Dynamic branch prediction

---

## 🗂️ Directory Structure
<pre>
.
├── outputs
│   ├── bubblesort.mc
│   ├── data_mem.mc
│   ├── data_r.mc
│   ├── factorial.mc
│   ├── fibonacci.mc
│   └── mcode.mc
├── Readme.md
├── src
│   ├── mcode.mc
│   ├── operation.txt
│   └── PHASE3.cpp
└── test
    ├── bubble_sort.asm
    ├── fact.asm
    └── fibonacci.asm
</pre>

---

## 🧰 Features & Input Knobs

| Knob      | Description 					    |
|-----------|-------------------------------------------------------|
| **Knob1** | Enable/disable pipelining 			    |
| **Knob2** | Enable/disable data forwarding 			    |
| **Knob3** | Print register file contents at the end of each cycle |
| **Knob4** | Print pipeline registers + cycle info (full trace)    |
| **Knob5** | Trace pipeline registers for a specific instruction   |
| **Knob6** | Print Branch Prediction Unit (PC, PHT, BTP) details   |


---

## 📊 Output Statistics (printed to file)

- **Stat1**: Total number of cycles
- **Stat2**: Total instructions executed
- **Stat3**: CPI
- **Stat4**: Number of load/store instructions
- **Stat5**: Number of ALU instructions
- **Stat6**: Number of control instructions
- **Stat7**: Number of stalls/bubbles
- **Stat8**: Number of data hazards
- **Stat9**: Number of control hazards
- **Stat10**: Number of branch mispredictions
- **Stat11**: Stalls due to data hazards
- **Stat12**: Stalls due to control hazards

---

## ✅ Test Cases

Test programs located in `/test` include:
- `bubble_sort.asm`
- `fact.asm`
- `fibonacci.asm`

> These are assembled and run through the simulator. Output memory states are logged in `/outputs`.

---

## 📦 How to Run

1. Compile the simulator:
   ```bash
   g++ -o phase3_sim PHASE3.cpp
