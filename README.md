# ⚙️ RISC-V Instruction Encoder (Assembler)

> A Python-based assembler that translates a subset of RISC-V assembly instructions into 32-bit machine code by performing instruction encoding, register mapping, immediate handling, and label resolution.

---

## 📌 Overview

The RISC-V Instruction Encoder is the assembler component of a custom RISC-V assembler–simulator pipeline. It reads assembly instructions, identifies their instruction formats, and generates corresponding 32-bit binary machine code following the RISC-V ISA specification.

The project supports multiple instruction formats, resolves symbolic labels for branch instructions, and performs binary encoding of registers, opcodes, function fields, and immediate values.

---

## ✨ Features

- Encode RISC-V assembly instructions into machine code
- Support for multiple instruction formats
- Register name to register number mapping (`x0` – `x31`)
- Automatic label resolution for branch instructions
- Immediate value encoding and bit masking
- Generates one 32-bit binary instruction per line
- Modular and easy-to-extend implementation

---

## 🛠 Supported Instruction Set

### R-Type
- `add`
- `sub`
- `slt`
- `srl`
- `or`

### I-Type
- `lw`
- `addi`
- `jalr`

### S-Type
- `sw`

### B-Type
- `beq`
- `bne`
- `blt`

### J-Type
- `jal`

---

## 🛠 Tech Stack

| Category | Technologies |
|----------|--------------|
| Language | Python |
| Architecture | RISC-V ISA |
| Concepts | Computer Organization, Instruction Encoding, Binary Manipulation |

---

## 🧠 Core Concepts Used

- RISC-V Instruction Set Architecture (ISA)
- Binary Instruction Encoding
- Register Mapping
- Immediate Encoding
- PC-relative Branching
- Label Resolution
- Bit Manipulation
- File Processing

---

## 🏗 Encoding Workflow

```text
Assembly Code
       │
       ▼
Instruction Parser
       │
       ▼
Instruction Format Detection
       │
       ▼
Register & Immediate Encoding
       │
       ▼
Label Resolution
       │
       ▼
32-bit Binary Machine Code
```

---

## 📂 Project Structure

```text
.
├── assembler.py      # Main assembler implementation
├── input.txt         # Input assembly program
├── output.txt        # Generated machine code
└── README.md
```

---

## 🚀 Getting Started

### Clone the Repository

```bash
git clone https://github.com/yourusername/Assembler-Simulator.git
```

### Prepare Input

Create an `input.txt` file containing valid RISC-V assembly instructions.

```assembly
add x1, x2, x3
addi x4, x1, 10

loop:
beq x1, x2, loop
```

### Run

```bash
python assembler.py
```

---

## 📄 Example Output

```text
00000000001100010000000010110011
00000000101000001000001010010011
```

Each line represents the binary encoding of the corresponding assembly instruction.

---

## 📌 Design Decisions

- Registers are mapped using a dedicated lookup table.
- Opcodes, `funct3`, and `funct7` fields follow the RISC-V ISA specification.
- Branch labels are converted into PC-relative offsets.
- Immediate values are masked and encoded according to instruction format.
- Instruction formats are identified dynamically during parsing.

---

## ⚠️ Current Limitations

- Supports a subset of the RISC-V ISA.
- Input must follow valid assembly syntax.
- Pseudo-instructions are not supported.
- Error handling is minimal.

---

## 🚀 Future Improvements

- Support for the complete RV32I instruction set
- Pseudo-instruction expansion
- Improved syntax validation
- Better error reporting
- Hexadecimal machine code output
- Interactive assembler CLI

---

## 📚 What I Learned

This project deepened my understanding of how assembly language is translated into machine code. I gained hands-on experience with instruction encoding, bit-level manipulation, PC-relative addressing, label resolution, and the internal workings of the RISC-V Instruction Set Architecture.
