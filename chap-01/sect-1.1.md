# Information is Bit + Context

A Rust source file like main.rs is stored as a sequence of bits grouped into 8-bit bytes. 
ASCII characters use one byte each (e.g., # = 35, i = 105, \n = 10), while other UTF-8 characters may use multiple bytes. 
Files with only text-encoded bytes are text files; those with non-text data are binary files. 
In computers, all data—code, files, memory, or network messages—are just bits, and their meaning depends entirely on the context in which they’re interpreted
