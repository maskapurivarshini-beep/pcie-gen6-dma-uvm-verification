# Multi-Channel DMA Engine Verification (PCIe Gen 6 Protocol)

A production-grade, highly scalable **Universal Verification Methodology (UVM)** testbench architecture engineered to functionally validate a multi-channel Direct Memory Access (DMA) Engine designed for enterprise AI data center compute clusters. The environment implements transaction-level modeling (TLM 2.0) to stress-test high-speed data routing protocols under massive line-rate injections.

## 🚀 Key Features & Architectural Highlights
* **UVM Architecture:** Built completely from scratch utilizing an Object-Oriented Framework including Virtual Sequencers, Scoreboards, Drivers, Monitors, and Agents.
* **Protocol Alignment:** Configured to monitor and validate data routing matching strict **PCIe Gen 6** data-highway interface constraints.
* **Stress Validation:** Supports virtual sequence scenarios capable of injecting **100 Gbps simulated line-rates** to monitor structural deadlocks and buffer overflows.
* **Performance Boost:** Achieved a **25% verification throughput efficiency** improvement by replacing legacy directed checks with structured constraint-random test distributions.

## 📂 Repository Structure
```text
├── sim/                # Simulation run scripts (Makefile, VCS/Questa commands)
├── src/                # RTL Source files for the DMA Engine (Verilog/SystemVerilog)
└── tb/                 # UVM Testbench Environment
    ├── agents/         # PCIe and Register Configuration Agents
    ├── env/            # Top-level UVM Environment Configuration
    ├── sequences/      # Virtual Sequences & Constraint-Random Test Cases
    ├── tests/          # Base Test Classes 
    └── tb_top.sv       # Top-level Hardware Module Harness
```

## 🛠️ Tools & Prerequisites
* **EDA Simulators:** Synopsys VCS, Cadence Xcelium, or Siemens Questa
* **Languages:** SystemVerilog (IEEE 1800), Python 3.x (for automated regression data processing)

## 💻 How to Run Simulations
To execute the base UVM test case utilizing the provided Makefile framework:
```bash
cd sim
make run TESTNAME=dma_base_test SEED=random COMPILER=vcs
```
To generate coverage matrices post-simulation:
```bash
make view_coverage
```
