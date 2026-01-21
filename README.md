# 3-Phase Pipelined RISC-V Processor (SystemVerilog)

Compact RTL implementation of a simple 3-stage (fetch, execute, writeback) pipelined RISC-V core written in SystemVerilog for educational and verification use.

## Features
- Small, modular SystemVerilog RTL for a RISC-V datapath and pipeline
- Basic hazard handling and control logic
- Testbench for simulation

## Files of interest
- `processor.sv` — top-level processor
- `tb_processor.sv` — testbench
- `reg_file.sv`, `reg_file` — register file implementation
- `alu.sv`, `controller.sv`, `hazard_unit.sv`, `pc.sv`, `imm_gen.sv` — core modules
- `inst_mem.sv`, `data_mem.sv` — memories

## Simulation (ModelSim / Questa)
1. Create work library and compile
```
vlib work
vlog -sv *.sv
```
2. Run testbench (batch)
```
vsim -c work.tb_processor -do "run -all; quit"
```
3. View waveforms (VCD) with GTKWave
```
gtkwave processor.vcd
```

Notes: your environment may use `vsim` with GUI options (e.g. `vsim work.tb_processor`) or other simulators.

## GitHub: quick push commands
Option A — using GitHub CLI (`gh`):
```
git init
git add .
git commit -m "Initial commit: 3-phase pipelined RISC-V core"
gh repo create <OWNER>/<REPO> --public --source=. --remote=origin --push
```

Option B — manual remote:
```
git init
git add .
git commit -m "Initial commit: 3-phase pipelined RISC-V core"
git branch -M main
git remote add origin https://github.com/<OWNER>/<REPO>.git
git push -u origin main
```

Replace `<OWNER>` and `<REPO>` with your GitHub username/org and repository name.

## Recommended .gitignore (suggested)
```
/work/
*.vcd
vsim.wlf
transcript
*.qdb
*.qpg
```

---
Created in project root. If you want, I can also add a `.gitignore` file and run the initial `git` commands for you.
