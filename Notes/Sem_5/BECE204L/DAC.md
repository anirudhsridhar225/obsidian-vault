Digital to analog converter
most commonly used: R/2R method due to high precision

DAC resolutions: 8, 10 and 12 bits

# Sawtooth waveform:

```8051 asm
ORG 0000H
SAWTOOTH: MOV A, #00H
BACK: MOV P1, A
	INC A
	CJNE A, #255, BACK
	MOV A, #00
	SJMP SAWTOOTH
	RET
END
```

# Triangular waveform

```8051
ORG 0000H
MAIN:MOV A, #00H
MOV P1, #00H

LOOP1: MOV P1, A
	INC A
	CJNE A, #255, LOOP1
LOOP2: MOV P1, A
	DEC A
	CJNE A, #00, LOOP2
	SJMP MAIN
	RET
END
```

# Staircase waveform

```8051
ORG 0000H
MAIN: MOV A, #00H
MOV P1, A

LOOP: ADD A, #51
	MOV P1, A
	CJNE A, #255, LOOP
	SJMP MAIN
	RET
END
```


