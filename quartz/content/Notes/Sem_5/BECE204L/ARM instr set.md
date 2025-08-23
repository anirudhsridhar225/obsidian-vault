# Load/Store instructions

- there are 3 types of load-store instructions:
	1. Single-register transfer
	2. Multiple-register transfer
	3. Swap


- LDR: Load word into register
- STR: Store word into register

# Data processing instructions

1. MOV- Move a 32b value into register
2. MVN- Move the NOT of a 32b value into register
3. LSL/LSR- Logical shift left/right `MOV R0, R2, LSR #2; R0 = R2>>2`
4. ASR- Arithmetic shift right `MOV R0, R2, ASR #2; R0 = R2>>2 but replaces MSB with MSB after shifting instead of a 0`
5. ROR- Rotate right `MOV R0, R2, ROR #2`
6. RRX- Rotate right extended `MOV R0, R2, RRX #2; R0 = R2 rotate 2, C`
7. ADD- add 2 32b values
8. ADC- add 2 32b values and carry
9. SUB- subtract 2 32b values `SUB R0, R1, R2; R0 = R1-R2`
10. SBC- subtract 2 32b values and carry
11. RSB- reverse subtract 2 32b values `SUB R0, R1, R2; R0 = R2-R1`
12. RSC- reverse subtract w carry
13. MUL- multiply 2 32b numbers
14. MLA- MAC 2 32b numbers `MLA R0, R1, R2, R3; R0 = (R1*R2)+R3`
15. AND- logical bitwise AND
16. ORR- logical bitwise OR
17. EOR- logical bitwise XOR
18. BIC- logical bit clear `BIC R0, R1, R2; R0 = R1 AND (NOT R2)`
19. CMP- compares Rn-N `CMP R0, R9; if R0-R9 = 0, CPSR.Z is set`
20. CMN- compare negate Rn+N

# Branch instructions

1. B- branch forwards
2. BL- branch with link, after executing return from subroutine using LR copied to PC
3. conditionals:
	1. EQ
	2. NE
	3. CS
	4. MI
	5. PL
	6. VS
	7. VC
	8. HI
	9. LS
	10. GE
	11. LT
	12. GT
	13. LE
	14. AL