2 methods:
1. synchronous - 1 block at a time (USART)
2. async - 1 byte at a time (UART)

registers used:
1. TMOD, TL1, TH1
2. SCON
3. SBUF

hex value = $(-28800/(baudrate))_{16}$

# Code

## To send bytes

1. timer mode 2 is used
2. load th1 with value acc to baudrate
3. load scon with `#50h`
4. setb tr1
5. mov letter into a and call subroutine that moves the letter from a to sbuf
6. once done, loop back to 5
7. one more label that loops TI till bit set, then clears TI and returns

## To receive bytes

1. timer mode 2 is used
2. load th1 with baudrate
3. load scon with `#50h`
4. setb tr1
5. clear ri
6. use ri flag to see if full byte is received or not
7. when ri is raised, sbuf has the byte
8. loop back to step 5