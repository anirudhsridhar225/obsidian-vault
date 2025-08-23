# arithmetic instructions

1. ADD
2. ADDC
3. SUBB
4. MUL
5. DIV
6. DEC
7. INC
8. DA (decimal acc adjust)
9. CLR
10. CPL
11. RL (rotate left)
12. RLC (rotate left with carry)
13. RR
14. RRC
15. SWAP (Swap nibbles within A)

# logical instructions

1. ANL
2. ORL
3. XRL

# bit-oriented instructions

1. CLR
2. SETB
3. CPL 
4. MOV
5. ANL
6. ORL

# branching instructions

1. JMP
2. SJMP - 8bit signed offset
3. LJMP - 16b address
4. AJMP (absolute jump) - range $2^{11}$
5. LCALL - 16 bit address
6. ACALL - 11 bit address
7. RET
8. RETI
9. JZ/JNZ
10. JC/JNC
11. JB/JNB
12. JBC (jump if bit set and clear bit)
13. CJNE
	1. A, direct, rel
	2. A, `#data`, rel
	3. $R_n$, `#data`, rel
	4. @$R_i$, `#data`, rel
14. DJNZ 
	1. $R_n$, rel
	2. direct, rel
15. NOP

# data transfer instructions

1. MOV
2. MOVC
3. MOVX
4. PUSH
5. POP
6. XCH
7. XCHD (exchange lower bit)

# arithmetic flags

4 flags:
1. Carry (C)
2. Auxiliary Carry (AC)
3. Overflow (OV)
4. Parity (P)

all of these flags are stored in the PSW