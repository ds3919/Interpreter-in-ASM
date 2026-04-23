# Interpreter-in-ASM
A small 4 instruction interpreter built in ASM using custom [6502 instruction set](./Instruction%20Set.pdf) provided by Brian Gormanly, professor of Organization and Architecture at Marist University.

## Usage
Write your code after line 93 (0x5C). The four instructions available:
- 0x01 = Increment Accumulator
- 0x02 = Decrement Accumulator
- 0x03 = Print Accumulator
- 0x04 = HALT Program\

You can run the program on [tsiram](https://tsiram.com).\
*200 instruction max including the prebuilt code.

## Key Takeaways
- Mimics program counter like behavior by manipulating the low-byte of the load instruction operand. This was to resolve the issue with how LDA works in this instruction set, it doesn't inherently allow loading a memory address stored at another location.
- Uses address 0x5B as a simulated accumulator for the interpreter since using the main accumulator would require a lot of manipulation between the X and Y registers. It saves tons of space by eliminating the need for the dance between the registers to simulate an accumulator.
- Uses address 0x5A as a constant for both decrementing and forcing the Z-flag to equal 0.

## Restrictions
- No ability to increment the high-byte of load operand, so the max amount of instructions this can account for is 256. Not much of a concern considering the max instruction load for the website is 200.

## Constrictions placed by Project
- 200 Instructions Max
- Infinite Loop Protection (can cause issues with certain loops if not written correctly)

## Assignment
Write one working 6502 machine-instruction program, paste the MMU load code in the Appendix A format, and include at least one add, compare, and branch instruction, with examples including Fibonacci, loops, if-else logic, or any other creative program.
