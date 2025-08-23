
# data transfer instructions

1. MOV
2. PUSH
3. POP
4. XCHG
5. LEA (load effective address)
6. LDS/LES (load DS/ES register)
7. LAHF (load AH from lower byte of flag)
8. SAHF (store AH from lower byte of flag)
9. PUSHF (push flags to stack)
10. POPF
11. IN
12. OUT

# arithmetic instructions

1. ADD
2. ADC
3. INC/DEC
4. SUB
5. SBB
6. CMP
	1. if both operands equal: 0
	2. carry = 1 if source > destination
	3. carry is reset if destination > source
7. DAA (decimal adjust acc)
8. DAS (decimal adjust after subtraction)

# logical instructions

1. AND
2. OR
3. NOT
4. XOR
5. TEST (logical compare instruction)
6. SAL/SHL (shift logical/arithmetic left)
7. SHR (shift logical right)
8. SAR
9. ROR/ROL
10. RCL/RCR

# string manipulation instructions

1. MOVSB/MOVSW
2. REP
3. REPE/REPNE
4. REPZ/REPNZ
5. CMPSB/CMPSW
6. LODS/LODSB/LODSW

# branch instructions

1. JMP
2. LOOP
3. LOOPZ/LOOPNZ
4. LOOPE/LOOPNE
5. CALL
6. RET
7. JC/JNC
8. JE/JNE
9. JZ/JNZ
10. JP/JNP (parity)
11. JPE/JPO (even/odd parity)
12. JO/JNO (overflow)
13. JS/JNS (sign)
14. JL/JNGE (lesser than strictly)
15. JGE/JNL (greater than or equal)
16. JLE/JNG (less than or equal)
17. JG/JNLE (greater than strictly)

# machine control instructions

1. WAIT
2. HLT
3. NOP
4. ESC (escape to ext device)
5. LOCK (bus lock instr prefix)
