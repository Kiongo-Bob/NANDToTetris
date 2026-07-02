# NAND2Tetris — Build a Modern Computer from First Principles

Personal practice repo for working through [**The Elements of Computing Systems**](https://www.nand2tetris.org/) (Nisan & Schocken) — building a full computer system from NAND gates up to a working Tetris-capable machine, across two courses (Part I: hardware, Part II: software).

## Why this repo

Practicing the "neurons and bits" of computing at the lowest level: logic gates → ALU → CPU → assembler → VM → compiler → OS. This complements embedded systems and low-level firmware work by lifting the abstraction layers through the hardware/software boundary enhancing clarity and transparency, top to bottom.

## Repo Structure

```
nand2tetris/
├── projects/
│   ├── 01_boolean_logic/        # Nand, And, Or, Xor, Mux, Not16, etc.
│   ├── 02_boolean_arithmetic/   # HalfAdder, FullAdder, ALU
│   ├── 03_sequential_logic/     # Bit, Register, RAM8/64/512/4K/16K, PC
│   ├── 04_machine_language/     # Mult.asm, Fill.asm
│   ├── 05_computer_architecture/# CPU, Memory, Computer
│   ├── 06_assembler/            # Hack assembler (your language of choice)
│   ├── 07_vm_i_stack_arithmetic/# VM translator: push/pop, arithmetic
│   ├── 08_vm_ii_program_control/# VM translator: branching, functions
│   ├── 09_high_level_language/  # Jack program (mini-app/game)
│   ├── 10_compiler_i_syntax/    # Jack tokenizer + parser
│   ├── 11_compiler_ii_codegen/  # Full Jack compiler → VM code
│   └── 12_operating_system/     # Jack OS: Math, String, Array, Output, etc.
├── tools/                       # Official N2T CLI tools (HardwareSimulator, CPUEmulator, etc.)
└── notes/                       # Personal notes, gotchas, diagrams per project
```

## Progress Tracker

### Part I — Hardware (Projects 1–6)
- [ ] Project 1: Boolean Logic
- [ ] Project 2: Boolean Arithmetic (ALU)
- [ ] Project 3: Sequential Logic (Memory)
- [ ] Project 4: Machine Language (Hack assembly)
- [ ] Project 5: Computer Architecture (CPU + Memory + Computer)
- [ ] Project 6: Assembler

### Part II — Software (Projects 7–12)
- [ ] Project 7: VM I — Stack Arithmetic
- [ ] Project 8: VM II — Program Control
- [ ] Project 9: Jack Language — build a simple program/game
- [ ] Project 10: Compiler I — Syntax Analysis
- [ ] Project 11: Compiler II — Code Generation
- [ ] Project 12: Operating System

## Setup

1. Download the [Nand2Tetris Software Suite](https://www.nand2tetris.org/software) and unzip `nand2tetris/tools/` into `tools/` here.
2. Make the shell scripts executable:
   ```bash
   chmod +x tools/*.sh
   ```
3. Add tools to your PATH (optional, for convenience):
   ```bash
   export PATH="$PATH:$(pwd)/tools"
   ```
4. Test a project with the Hardware Simulator:
   ```bash
   HardwareSimulator.sh
   ```
   Load a `.hdl` file and its matching `.tst` script, then run.

## Testing Workflow

For each hardware project:
```bash
tools/HardwareSimulator.sh projects/01_boolean_logic/And.tst
```

For each software project (VM/compiler):
```bash
tools/VMEmulator.sh
# or, once you have your own translator:
python vm_translator.py projects/07_vm_i_stack_arithmetic/StackTest
```

Compare output `.out` files against the provided `.cmp` files — a clean diff means the test passed.

## Rules of Engagement (self-imposed)

- No peeking at reference `.hdl`/`.asm`/`.vm` solutions before attempting a project.
- Every chip/program must pass its official `.tst`/`.cmp` before moving on.
- Write a short note in `notes/` after each project — what broke, what clicked.
- Projects 6 and 11 (assembler, compiler) should be implemented in real code, not just by hand — good excuse to practice a language deeply.
- Stick through the suck, AI makes things easy since information is very readily.

## Resources

- Course site & book: https://www.nand2tetris.org/
- Course lectures (Coursera): [Part I](https://www.coursera.org/learn/build-a-computer) · [Part II](https://www.coursera.org/learn/nand2tetris2)
- Errata & FAQ: https://www.nand2tetris.org/errata

## License

Personal learning repo. Course materials, specs, and test scripts are © Nisan & Schocken / nand2tetris.org — used here under the project's stated terms for personal educational use. All code in `projects/` is my own implementation.
