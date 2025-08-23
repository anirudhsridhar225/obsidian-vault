TMOD register: to define mode of operation
4 registers: TH, TL, TF, TR
2 timers: T0, T1

3 modes:
1. 13-bit timer (mode 0)
2. 16-bit timer (mode 1)
3. 8-bit auto-reload (mode 2)

# TMOD

GATE | C/T | M1 | M0 | GATE | C/T | M1 | M0

| M1  | M0  | Mode            |
| --- | --- | --------------- |
| 0   | 0   | 13-b            |
| 0   | 1   | 16-b            |
| 1   | 0   | 8-b auto reload |
| 1   | 1   | split timer     |
C/T = 1: counter
C/T = 0: timer

# TCON

TF1 | TR1 | TF0 | TR0 | IE1 | IT1 | IE0 | IT0

tf1/tf0 -> overflow flags
tr1/tr0 -> run control bits

# Code:

1. load tmod value 
2. load th/tl values
3. setb tr
4. poll tf till bit set
5. clear tf and tr

#counters 

1. load tmod value
2. load th value to 0
3. setb tr
4. mov tl value to a, and that to output pin
5. loop till tf is set
6. clear tf and tr
7. loop to step 3