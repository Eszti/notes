# HPC with C++

## HPC

- some problems require more computing than what a PC/laptop can provide
- solutions
	- optimize code
		- signle core
			- SIMD (Signle Instruction Multiple Data)
		- many cores
			- multithreading
				- declarative
				- imperative
	- expand HW
		- clusters
			- MPI
		- custom HW
			- GPGPU (general purpose GPE)
			- HW acceleration

## SIMD

- number of clock cycles (add < multiply < divide < square ...)
- float vs double
- divide & conquer
	- e.g. vector addition
- registers
	- can be filled diferently
	- larger register: need CPU support --> compatibility issue
	- vector support is better
- Intel SSE (Streaming SIMD Extensions)
	- 128-bit registers
- integral & floating point operations
- scalar vs packed data (whole array)
- ways of leveraging
	- inline assembly
	- intrinsics
	- compiler vectorization
- inline assebly
	- not supported by every compiler