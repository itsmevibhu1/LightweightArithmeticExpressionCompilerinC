# 🛠️ UNN Compiler

This is a simple compiler written in C for a toy programming language (with `.unn` extension). The compiler performs lexical analysis, parsing, code generation (NASM-compatible x86-64 assembly), and builds a final executable using `nasm` and `gcc`.

---

## 📦 Features

- Parses basic arithmetic expressions (e.g., `exit(2 + 3)`)
- Generates x86-64 assembly using NASM syntax
- Compiles to an executable using `nasm` and `gcc`
- Modular structure:
  - Lexer (`lexerf.h`)
  - Parser (`parserf.h`)
  - Code Generator (`codegeneratorf.h`)

---

## 🗃️ Project Structure

```
.
├── main.c                       # Entry point
├── lexerf.h / lexer.c           # Lexical analysis
├── parserf.h / parser.c         # AST parsing
├── codegeneratorf.h / codegenerator.c  # Codegen logic
├── generated.asm                # Generated NASM code (output)
├── Makefile (optional)
├── README.md
```

---

## 🚀 Usage

### 🧰 Prerequisites

Make sure you have:

- `nasm` installed  
  ```bash
  brew install nasm      # on macOS
  sudo apt install nasm  # on Linux
  ```
- `gcc` installed

---

### 🏗️ Compile the compiler

```bash
gcc main.c lexer.c parser.c codegenerator.c -o unn_compiler
```

---

### ▶️ Run the compiler

```bash
./unn_compiler program.unn output_program
```

This will:

1. Generate `generated.asm` (assembly code)
2. Compile it with `nasm` to `generated.o`
3. Link it with `gcc` to create `./output_program`

---

## 🧪 Example

### Input (`program.unn`)
```
exit(2 + 3)
```

### Output (console)
```bash
Loaded: 2
Loaded: 3
Result: 5
```

---

## 📌 Notes

- The output assembly is written to `generated.asm`.
- Output binary name is defined by the second CLI argument.
- Code assumes Linux x86-64 architecture with System V ABI.

---

## ✅ TODO

- Support subtraction, multiplication, division
- Add variables and assignment
- Add control flow (if/while)
- Error handling improvements
- Code optimization

---

## 📝 License

MIT License — Free to use, modify, and share.

---

## 🙌 Author

Made by **VIBHU YADAV** — as a compiler design project in C.
