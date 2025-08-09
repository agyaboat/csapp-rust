# Chapter 1 — A Tour of Computer Systems

## Overview
This chapter uses the classic `"hello, world"` program to introduce the major concepts of computer systems.  
By tracing the program’s lifetime — from writing the source code to running it and producing output — we see how **hardware and system software work together** to execute applications.

The chapter sets the foundation for the rest of the book:
- Understanding the representation of information as bits and bytes.
- Recognizing the roles of compilers, linkers, loaders, and operating systems.
- Seeing how the CPU, memory, and I/O devices cooperate.
- Realizing how low-level details influence correctness, performance, and security.

## Goals
By the end of this chapter, you should be able to:
1. Describe the main hardware and software components in a computer system.
2. Understand the stages a program goes through from source code to execution.
3. Explain how data and instructions are represented in memory.
4. Identify key concepts that will be studied in depth in later chapters (e.g., compilation, linking, memory hierarchy, concurrency).

## Sections in This Chapter
1. **Information is Bits + Context** — All data in a computer is stored as binary bits, interpreted according to context.
2. **Representing and Running a Program** — How source code is translated into executable machine code.
3. **Hardware Organization** — CPU, main memory, I/O devices, and their roles.
4. **Operating System Overview** — How the OS manages hardware resources and provides services.
5. **Networks and Distributed Systems** — How computers communicate over networks.
6. **Concurrency and Parallelism** — Why modern systems use multiple cores and threads.
7. **Performance Considerations** — The influence of hardware design and memory systems.
8. **The Lifetime of the “Hello” Program** — From writing the file to execution and termination.

---

**Next Steps:** This chapter’s sections will each have their own `.md` explanation file and, where applicable, a `.rs` Rust example to illustrate the concept.
