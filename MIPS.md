R-
I-
J-


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