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