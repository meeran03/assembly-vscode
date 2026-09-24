# Assembly in VS Code — historical learning setup

A small **2021 learning project** for assembling and debugging 32-bit x86 NASM programs on Linux. Retained because people still use the setup; it is not a current cross-platform assembly toolchain.

## What is here

- `test.asm`: a Linux `int 0x80` hello-world program.
- `.vscode/tasks.json`: NASM assembly followed by GNU `ld` linking.
- `.vscode/launch.json`: debugger configuration for VS Code.

## Build the included example

On an x86 Linux environment with NASM, GNU binutils, and 32-bit executable support:

```bash
nasm -f elf -F dwarf -g test.asm
ld -m elf_i386 -o test test.o
./test
```

The VS Code build task applies the same commands to the active assembly file. Debugging also needs GDB and the VS Code C/C++ extension.

## Platform boundary

The ELF format, `elf_i386` linker target, and Linux system calls are intentional. This is not a native macOS, Apple Silicon, Windows, or x86-64 example. Use an appropriate Linux environment to reproduce it. The legacy setup has not been revalidated as part of the September 2026 documentation refresh.

For current work in voice AI, reliable backend systems, and applied AI, visit [meeran.dev](https://meeran.dev) or [my GitHub profile](https://github.com/meeran03).
