- two types of memory: program(ROM) and data(RAM) memory

# program memory

- 4096 locations of internal ROM that can be expanded upto 64k
- 0000h to 0fffh
- to use additional memory,
	- EA = 0 -> completely ignores program memory and only executes from external memory
	- EA = 1 -> first from built-in ROM then external memory

# data memory

- 128 bytes of internal data memory, external data memory interfacing allowed upto 64k
- 3 separate divisions:
	1. register banks - 32 bytes
	2. bit addressable area - 16 bytes (20 - 2F)
	3. scratch pad area - 80 bytes (30 - 7F)

## register banks

1. 00 to 07 - RB0
2. 08 to 0F - RB1 (stack)
3. 10 to 17 - RB2
4. 18 to 1F - RB3

- each of these banks has 8 registers (r0 to r7)
- at one time, only one bank is selected (using rs0 and rs1 in psw) for operations
- by default RB0 is selected after system reboot

## bit addressable area

- this is where individual bits in internal RAM can be set/cleared
- mainly used to store bit variables from application program, like status of LED, etc.

## scratch pad area

- 80 bytes of scratch pad area for general purpose data storage
- used by system stack and in practice, little space is left for general storage
- fast memory access from this area compared to main memory
- can be accessed using direct/indirect addressing modes