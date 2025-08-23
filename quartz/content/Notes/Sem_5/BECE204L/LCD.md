- `38H` to use 16x2 LCD in 8b mode
- `0FH` cursor blinking on
- `OEH` cursor blinking off
- `01H` clear
- `06H` to move the cursor or write data
- `80H` to write in 1st row, 0th position
	- `81H --> 1st pos`
	- `82H --> 2nd pos` etc.
	- `8FH --> 16th pos`
- `C0H to CFH` is 2nd row

Code:

```8051
ORG 0000H
	LJMP MAIN

ORG 0030H
MAIN:
	AGAIN:
		MOV A, #38H
		ACALL COMMS
		ACALL DELAY
		MOV A, #0FH
		ACALL COMMS
		ACALL DELAY
		MOV A, #01H
		ACALL COMMS
		ACALL DELAY
		MOV A, #06H
		ACALL COMMS
		ACALL DELAY
		MOV A, #80H
		ACALL COMMS
		ACALL DELAY
		MOV A, #'H'
		ACALL WRITE
		ACALL DELAY
		MOV A, #'E'
		ACALL WRITE
		ACALL DELAY
		MOV A, #'L'
		ACALL WRITE
		ACALL DELAY
		MOV A, #'L'
		ACALL WRITE
		ACALL DELAY
		MOV A, #'O'
		ACALL WRITE
		ACALL DELAY
		SJMP AGAIN

	COMMS:
		CLR P2.1 ; CLEAR R/W
		CLR P2.2 ; CLEAR RS
		SETB P2.0 ; PULSE E FROM HIGH TO LOW
		MOV P1, A
		ACALL DELAY
		CLR P2.0
		RET

	WRITE:
		CLR P2.1
		SETB P2.2
		SETB P2.0
		MOV P1, A
		ACALL DELAY
		CLR P2.0
		RET

	DELAY:
		MOV R3, $50
	HERE2:
		MOV R2, #255
	HERE1:
		DJNZ R2, HERE1
		DJNZ R2, HERE2
		RET

END
```