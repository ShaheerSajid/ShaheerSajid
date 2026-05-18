<h1 align="center">Hi, I'm Shaheer 👋</h1>

<p align="center">
  <em>Physical Design Engineer · RTL → GDSII · Samsung 4nm &amp; TSMC 5nm</em><br/>
  <em>Building a chip-design toolchain in my spare time — core, SoC, SDK, and a parametric SRAM compiler.</em>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/shaheer-sajid-a00b4b309">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white" alt="LinkedIn"/>
  </a>
  <a href="mailto:shaheersajid15@gmail.com">
    <img src="https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white" alt="Email"/>
  </a>
  <img src="https://img.shields.io/badge/Pakistan-01411C?style=flat&logo=googlemaps&logoColor=white" alt="Location"/>
</p>

---

### 🔧 Day job

Senior Physical Design at **DreamBig Semiconductor** (recently acquired by Arm for our RDMA &amp; Chiplet Hub work). I close advanced-node SoCs on **Samsung 4nm**, focused on power-grid architecture, flow automation, and timing convergence. Highlights:

- 🧩 Designed a **self-aligning multilayer PG mesh** — modular "Lego-block" grids that snap together across subblocks with consistent VDD/VSS rail alignment.
- 🔬 Wrote a **recursive TCL via-stack analyzer** and via-ladder methodology for high-current buffers and clock drivers.
- 🧠 Built a **connected-components / flood-fill TSV detection** algorithm that auto-shifts NoC buffer paths around clustered TSV regions; extended to backside metal for HBM JEDEC bus routing.
- 📡 Authored an internal-patent methodology for **buffering &amp; shielding ARM CMN interconnects** (~2 GHz, 2000+ signals).

### 🌙 Spare time

A connected ecosystem around **NTiny** — the first truly indigenously-designed microprocessor taped out in Pakistan (NUST × TSMC 65nm, where I was on the core design team) — and the open EDA tooling around it.

---

### 🚀 Pinned projects

| Project | What it is | Stack |
|---|---|---|
| 🔥 [**ntiny**](https://github.com/ShaheerSajid/ntiny) | The taped-out RISC-V SoC — **runs Linux**. RV32IMCB, 4-stage in-order pipeline, M/S/U privilege with Sv32 MMU, JTAG + RISC-V Debug, full peripheral set (UART/SPI/I²C/PWM/Timers/PLIC/GPIO/CRC). Silicon validated on a custom PCB. | SystemVerilog · TSMC 65nm |
| 🧠 [**ntiny-ooo**](https://github.com/ShaheerSajid/ntiny-ooo) | A classical **Tomasulo out-of-order** successor: per-FU reservation stations, ROB, 3-wide CDB, per-branch RAT snapshots for single-cycle mispredict recovery. RV32IM + Zicsr + Zb* + Zicond. RISCOF + directed test battery (11/11 green). | SystemVerilog · Verilator · spike |
| 📦 [**ntiny-sdk**](https://github.com/ShaheerSajid/ntiny-sdk) | Software SDK for the NTiny SoC, shipped as an **Open-CMSIS-Pack** — works in Keil, IAR, STM32CubeIDE, Eclipse, and VS Code. SVD, drivers, FreeRTOS, CoreMark, Dhrystone, and 10+ example apps. | C · CMSIS · GCC · FreeRTOS |
| 🧮 [**PakFPU**](https://github.com/ShaheerSajid/PakFPU) | **IEEE-754 compliant** floating-point unit for the open-source community. Parameterizable FP32/FP64 with FMA, division, and square root. Verified against **Berkeley TestFloat** across all 5 rounding modes; IEEE corner cases (sNaN, ±Inf×±0, canonical qNaN, FDIV ready/valid handshake) proven with **SymbiYosys + Bitwuzla** formal. Ships with the ntiny SoC. | SystemVerilog · Verilator · SymbiYosys |
| 🧱 [**fabram**](https://github.com/ShaheerSajid/fabram) | A parametric **SRAM compiler** targeting sky130A. Give it `(words, bits, mux)` → get a hierarchical SPICE netlist, a Liberty `.lib` from ngspice characterization (3×3 LUTs, setup/hold bisection), and a Verilog model with a `specify` block. Includes a Bayesian cell-sizing optimizer. | Python · ngspice · sky130A |
| ⚙️ [**spice_gen**](https://github.com/ShaheerSajid/spice_gen) | A **PDK-aware SPICE netlist generator** from YAML topology descriptions. Multi-dialect (ngspice / hspice / spice3), hierarchical `deps:`, automatic M→X conversion for subcircuit PDKs. Backbone of fabram. | Python · Pydantic |

<sub>How they fit together: <code>spice_gen</code> emits the netlists. <code>fabram</code> uses it to compose SRAM blocks from cell YAMLs, characterizes them with ngspice, and writes Liberty + Verilog. <code>ntiny</code> is the taped-out core (with <code>PakFPU</code> as its FPU); <code>ntiny-ooo</code> is its OoO successor; <code>ntiny-sdk</code> is how software runs on either.</sub>

---

### 🧰 Earlier work

[**RISCV**](https://github.com/ShaheerSajid/RISCV) ⭐19 — 32-bit soft RV32IMF processor for FPGAs (DE10-Lite, Avalon bus, GPIO/UART/Timer). CoreMark **2.58/MHz**, Dhrystone **1.45 DMIPS/MHz**. The ancestor of ntiny.
[**AES-256-Verilog**](https://github.com/ShaheerSajid/AES-256-Verilog) · [**SM4-Verilog**](https://github.com/ShaheerSajid/SM4-Verilog) — Synthesizable block ciphers.
[**RISCV-Compliant-Divider**](https://github.com/ShaheerSajid/RISCV-Compliant-Divider) · [**RV32_with_MAC**](https://github.com/ShaheerSajid/RV32_with_MAC) — RV32 extensions.
[**OpenCV-Maze-Solving**](https://github.com/ShaheerSajid/OpenCV-Maze-Solving) · [**Water-Management-System**](https://github.com/ShaheerSajid/Water-Management-System) — Older CV / embedded projects.

---

### 🛠️ Tools &amp; Tech

```
Physical Design    Synopsys Fusion Compiler · Custom Compiler · ICV · PrimeTime
                   Cadence Innovus · Genus · Virtuoso · PVS · RedHawk
RTL & Verification SystemVerilog · DPI-C · Verilator · VCS · QuestaSim
                   RISCOF · Berkeley TestFloat · SymbiYosys · Bitwuzla
Analog & SPICE     ngspice · hspice · sky130A · Liberty characterization
Scripting          Python · TCL · C/C++ · Bash · Makefile
Domains            Advanced-node PD · PG mesh · RDL · 3DIC / Chiplet · HBM3 · ARM CMN
                   RISC-V (in-order & OoO) · CMSIS · FreeRTOS
```

---

### 📊 GitHub

<p align="center">
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=ShaheerSajid&show_icons=true&hide_border=true&include_all_commits=true&count_private=true&theme=tokyonight" />
  <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=ShaheerSajid&layout=compact&hide_border=true&theme=tokyonight&langs_count=8" />
</p>

<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=ShaheerSajid&bg_color=1a1b27&color=70a5fd&line=bf91f3&point=38bdae&area=true&hide_border=true" alt="Contribution activity graph" />
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/ShaheerSajid/ShaheerSajid/output/github-contribution-grid-snake-dark.svg" alt="Contribution snake animation" />
</p>

---

### 🎓 Education

**MS, Electrical Engineering (ICs &amp; Systems)** — NUST · GPA 4.00/4.00 · 2024  
Thesis: *A commercially-compatible memory compiler framework for automated SRAM array generation* — productized as [fabram](https://github.com/ShaheerSajid/fabram).

**BS, Electrical Engineering** — NUST · 2021  
FYP: *Event-based image processing for drone obstacle avoidance.*

---

<p align="center"><em>Always happy to chat about advanced-node PD, RISC-V microarchitecture, parametric memory generation, or chiplet integration.</em></p>
