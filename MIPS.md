R- 6 5 5 5 6 (32)
I- 
J- 6, 16


## Complex Instruction Set Computer (CISC)
Example: x86-32 (IA32), Intel IA-64 bits
Single instruction performs complex operation
	VAX architecture had an instruction to multiple polynomials
		VAX -> Mini computer
		polynomials -> string copying/Fast Fourier Transform of images
		MB -> 100$
		Memory was expensive
Smaller program size as memory was premium
Complex implementation, no room for hardware optimization

## Reduced Instruction Set Computer (RISC)
Example: MIPS, ARM
Keep the instruction set small and simple, makes it easier to build/optimise hardware
Burden on software to combine simpler operations to implement high-level language statements
	More/cheaper memory
	Compiler Optimization

# Data Storage
Storage Architecture
General Purpose Register Architecture
	-> MIPS

## Storage Architecture Definitions
C = A + B
Operands may be implicit or explicit
* von Neumann Architecture:
	* Data (operands) are stored in memory
* For a processor, storage architecture concernswith:
	* Where do we store the operands so that the computation can be performed?
	* Where do we store the computation result afterwards?
	* How do we specify the operands?
* Major storage architectures

### Common Design
- Stack Architecture:
	- Operands are implicitly on top of the stack.
		- implicit operand
- Accumulator architecture:
	* One operand is implicitly in the accumulator (a special register).
		* implicit operand
	* Examples: IBM 701, DEX PDP-8. Synetek b502 Apple 2
- General-purpose register architecture:
	- Only explicit operands.
	- Register-memory architecture (one operand in memory).
		- Examples: Motorola 86000, Intel 80386
	- Register-register (or load-store) architecture
		- Examples: MIPS, DEX Alpha, ARM(used in smartphones)/M1/Arduino ABR Processor (RISC)
	Intel -> CISC 70s / ARM -> RISC
- Memory-memory architecture:
	- All operands in memory. Example: DEX VAX -> mini computer

## GPR Architecture
* For modern processors:
	* General-Purpose Register (GPR) is the most common choice for storage design
	* RISC computers typically use Register-Register (Load/Store) design
		* e.g MIPS, ARM
	* CISC computers use a mixture of Register-Register and Register-Memory
		* e.g IA32

## Memory Address and Content
- Given k-bit address, the address space is of size $2^k$ 
- Each memory transfer consists of one word of n bits
- Types of processors
	- Memory Address Register
		- k-bit address bus
			* one direction towards memory, write to memory only
		- writes addresses
		- 0 - $2^32$
	* Memory Data Register
		* n-bit data bus
			* bidirectional, read and write to memory
		* writes data
- The buses are called control lines
	- Manages if current memory access is read or write

## Memory Content: Endianness
- Endianness:
	- The relative ordering of the **bytes** in a multiple-byte word stored in memory
* Big Endian
	* MSB to lowest (topmost) address
	* Read from lowest to highest address
	* E.g. IBM 360/370, Motorola 68000 MIPS (Silicon Graphics), SPARC
* Little Endian
	* LSB to lowest (topmost) address
	* Read from highest to lowest address
	* E.g. Intel 80x86, DEX VAX, DEX Alpha

## Addressing Modes
- Addressing Mode:
	- Ways to specify an operand in an assembly language
- In MIPS, there are only 3 addressing modes:
	- Register:
		- Operand is in a register (eg. add $t1, $t2, $t3)
	- Immediate:
		- Operand is specified in the instruction directly (eg: addi $t1, $t2, 98)
	- Displacement:
		- Operand is in memory with address calculated as Base + Offset. (e.g lw \$t1, 20(\$t2))

![[Pasted image 20250908214148.png]]

![[Pasted image 20250908214528.png]]
## Frequently Used Instructions
- Profiler (SW)
	- Code
	- Memory
	- Cache Performance
	- Most Frequently Used Instructions
- Load, Conditional Branch, Compare, Store

## Instruction Formats
- Instruction Length
	- Variable-length (CISC)
		- Intel 80x86: instructions vary from 1 to 17 bytes long
		- Digital VAX: Instructions vary from 1 to 54 bytes long.
		- Require multi-step fetch and decode
		- Allow for a more flexible (but complex) and compact instruction set
	- Fixed-length (RISC)
		- Used in most RISC
		- MIPS, PowerPC, ARM: Instructions are 4 bytes long
		- Allow for easy fetch and decode
		- Simplify pipelining and parallelism
		- Instruction bits are scarce
		- e.g. ARM 64 bit -> 2x32bit or 1x64bit
			- Very Long Instruction Word (VLIW) architecture
- There is also hybrid instructions: a mix of variable: and fixed-length instructions
## Instruction Fields
- An instruction consists of:
	- opcode: unique code to specify the desired operation
	- operands: zero or more additional information needed for the operation
- The operation designates the type and size of the operands
	- Typical type and size: Character (8 bits), half-word (eg: 16 bits), word (eg. 32 bits), single-precision floating point (eg: 1 word), double-precision floating point (eg: 2 words).
- Expectations from any new 32-bit architecture:
	- Support for 8-, 16- and 32-bit integer and 32-bit and 64-bit floating point operations. A 64-bit architecture would need to support 64-bit integers as well.

## Instruction Encoding
- Issues: Code size, speed/performance, design complexity
- Things to be decided:
	- Number of registers
	- Number of addressing modes - more modes more complex
	- Number of operands in an instruction
- The different competing forces:
	- How many registers and addresing modes
	- Reduce code size (RISC vs CISC)
	- Have instruction length that is easy to handle (fixed-length instructions are easier to handle)

# Control Paths
| Control Signal   | Execution Stage      | Purpose                                               |
| ---------------- | -------------------- | ----------------------------------------------------- |
| RegDst           | Decode/Operand Fetch | Select the destination register number                |
| RegWrite         | Decode/Operand Fetch | Enable writing of register                            |
| ALUSrc           | ALU                  | Select the 2nd operand for ALU                        |
| ALUcontrol       | ALU                  | Select the operation to be performed                  |
| MemRead/MemWrite | Memory               | Enable reading/writing of data memory                 |
| MemToReg         | RegWrite             | Select the result to be written back to register file |
| PCSrc            | Memory/RegWrite      | Select the next PC value                              |
