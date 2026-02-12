# Minimal Debugger - Quick Start

## Build & Run (30 seconds)

```bash
cd ~/Documents/Code/debugger
make clean && make
./debugger ./test_prog
```

## Inside the Debugger

```
(dbg) run              # Start program
(dbg) help             # Show commands
(dbg) break 0x100003d40  # Set breakpoint at address
(dbg) continue         # Run to breakpoint
(dbg) print $rax       # Show register value
(dbg) step             # Execute one instruction
(dbg) quit             # Exit
```

## How to Use with Your Code

```bash
# 1. Compile with debug symbols
gcc -g -O0 -o myprog myprog.c

# 2. Get function address
nm myprog | grep main

# 3. Debug it
./debugger ./myprog

# 4. Inside debugger
(dbg) run
(dbg) break 0x100003d40     # Replace with your address
(dbg) continue
(dbg) print $rax             # Check registers
(dbg) step
(dbg) quit
```

## What It Does

✓ Fork & ptrace target process
✓ Set breakpoints (INT3)
✓ Single-step code
✓ Read/write registers
✓ Inspect memory
✓ Basic REPL interface

## What It Doesn't Do (Yet)

- No symbol resolution (use `nm` manually)
- Limited to x86-64
- No multi-threading
- No disassembly
- Basic error handling

## Code Structure

- `debugger.h` - 45 lines header
- `debugger.cpp` - 320 lines implementation
- `main.cpp` - 15 lines entry point
- **Total: 380 lines**

## Status

✓ Builds cleanly
✓ Runs test program
✓ Implements core features
✓ Ready to use and extend
