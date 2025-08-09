# Information is Bit + Context

A Rust source file like main.rs is stored as a sequence of bits grouped into 8-bit bytes. 
ASCII characters use one byte each (e.g., f = 102, n = 110, m = 109), while other UTF-8 characters may use multiple bytes. 
Files with only text-encoded bytes are text files; those with non-text data are binary files. 
In computers, all data—code, files, memory, or network messages—are just bits, and their meaning depends entirely on the context in which they’re interpreted.


## Context Changes Meaning
In Rust (and all programming), **bits themselves have no fixed meaning**.  
The *context* in which those bits are interpreted determines what they represent.

### Example

```rust
fn main() {
    //bytes as hex instead of decimal
    let bytes = [0x41, 0x42, 0x43, 0x44]; // Raw bytes in memory

    // Interpret as text (UTF-8 / ASCII)
    let as_str = std::str::from_utf8(&bytes).unwrap();
    println!("As text: {}", as_str); // "ABCD"

    // Interpret as integer (little-endian u32)
    let as_int = u32::from_le_bytes(bytes);
    println!("As integer: {}", as_int);

    // Interpret as floating point
    let as_float = f32::from_le_bytes(bytes);
    println!("As float: {}", as_float);
}
```