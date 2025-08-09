# Programs Are Translated By Other Programs Into Different Forms

`ref (./code-files/hello.rs)`

A hello.rs program starts as human-readable Rust code. 
To run it, the Rust compiler (rustc) translates the code into low-level machine instructions, 
then packages them into an executable binary file (object program) that the operating system can load and execute.

TOn a Unix system, the translation from source file to object file is performed
by a compiler driver:
```bash
$ rustc hello.rs
``` 

The flow then goes like this:
```text
[Source Code]
   │
   ▼[Compiler Driver (rustc)]
   │   - Invokes various compiler stages
   │   - Reads `hello.rs`
hello.rs
   │
   ▼
[Macro Expansion & Module Resolution]
   │   - Expands macros (`println!`, `include!`, etc.)
   │   - Resolves `use` and `mod` statements
   ▼
[LLVM IR Generation]
   │   - Rust code lowered into LLVM Intermediate Representation
   ▼
[Assembly Generation]
   │   - LLVM IR translated into target-specific assembly code
   ▼
[Object File Creation]
   │   - Assembly assembled into relocatable object file (`.o`)
   ▼
[Linking]
   │   - Merges `.o` with Rust standard library (`libstd`) and external crates
   ▼
Executable Binary (e.g., `hello`)
   - Ready to run on your system
```

## More light on this process:
1. **Macro Expansion**: 
   - Rust macros like `println!` are expanded into their full code before compilation.
   - This allows for powerful code generation and metaprogramming.
   - Any `use` statements or `mod` declarations are resolved by loading the relevant modules or crates.

2. **Compilation Phase**:
    - The compiler translates the macro-expanded Rust code into **LLVM Intermediate Representation (IR)**
    - LLVM IR is a low-level, platform-independent representation that can be optimized and translated into target-specific assembly language.
    - This concept is similar to C's `hello.i` -> `hello.s` step.

3. **Assembly Phase**:
    - The LLVM IR is translated into target-specific assembly code.
    - This code is still human-readable but is closer to machine language.
    - `rustc` uses LLVM's assembler to produce a relocatable object file (e.g., `hello.o`).
    - This file contains binary instructions for your CPU architecture but is not yet executable.

4. **Linking Phase**:
    - If your Rust code contains functions from standard library (e.g., println! uses std::io), `rustc` invokes the system linker to merge your object files with the required standard library files, plus any external crates you used.
    - The result is the executable binary (hello), ready to be loaded into memory and executed.
