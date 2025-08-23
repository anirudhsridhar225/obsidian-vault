the different addressing modes are:
1. immediate: `MOV A, 04H`
2. register addressing: any register except IP
	- AH, AL, BH, BL, CH, CL, DH, DL - 8b
	- AX, BX, CX, DX, SP, BP, SI ,DI, CS, SS, DS and ES - 16b
	- never mix 8b and 16b
	- code segment is never used as destination
	- segment to segment MOV not allowed
3. direct addressing: `MOV AX, [5000H]`
4. register indirect: `MOV AX, [BX]`
5. base addressing:
	- calc effective address by adding contents of base reg to displacement value
	- BX relative to DS normal
		- `MOV BX, 2000H`
		- `MOV AX, [BX+6]`
	- BP used to address memory relative to SS (stack segment)
		- `MOV BP, 1000H`
		- `MOV AX, [BP+4]`
6. base indexed addressing: combination of base and indexed
	- ($EA$ = $BX+SI+Displacement$) 
7. indexed addressing:
	- offset is stored in one of the index registers
	- DS is default for DI and SI
	- DS and ES default for SI and DI (for strings)

# physical address calculation

1. direct addressing:
	- EA = $10H*DS$ + Offset
	- in `MOV AX, [4000H]`, 4000 is the offset value

2. register indirect:
	- EA = $10H*DS$ + `[BX]`
	- in `MOV AX, [BX]`, value of `[BX]`, say 2000 is the offset

3. register relative:
	- EA = $10H*DS$ + Offset + `[BX]`
	- ex. `MOV AX, 5000 [BX]`

4. base indexed:
	- EA = $10H*DS$ + `[BX]` + `[SI]`
	- ex. `MOV AX, [BX] [SI]`

5. relative base indexed:
	- EA = $10H*DS$ + offset + `[BX]` + `[SI]`