Stands for Analog to Digital Converter

ADC resolution in bits: 8, 10, 12, 16, 24

Types:
1. Parallel: 8 or more pins for binary data. Ex. ADC804, ADC808
2. Serial: only one pin for data out. Ex. MAX1112

Step size:
- smallest change in the analog input voltage that can be detected by ADC
- smaller step size allows ADC to detect smaller changes in the sensing signal

Conversion time: time taken by ADC to convert the analog input to a digital(binary) number (doesn't exceed 110 $\mu$s)

| n-bit | number of steps  | step size (in mV) |
| ----- | ---------------- | ----------------- |
| 8     | $2^8$ = 256      | $5/255$ = 19.61   |
| 10    | $2^{10}$ = 1024  | $5/1023$ = 4.89   |
| 12    | $2^{12}$ = 4096  | $5/4095$ = 1.22   |
| 16    | $2^{16}$ = 65536 | $5/65535$ = 0.076 |

Step size = $V_{in}/(No. of steps - 1)$ 
Clock freq = $1/(1.1*RC)$
$D_{out}$(Digital output) = $V_{in}/Step size$

# ADC804

Steps: 
1. Make CS = 0 and send low-to-high pulse to WR pin to start conversion.
2. Monitor INTR pin. If low, then conversion finished, otherwise keep polling.
3. After INTR goes low, make CS = 0 and send high-to-low pulse to RD to read digital data.

--> Assembly program to monitor INTR and bring analog signal into register A

```8051
ORG 0000H

MOV A, #0FFH; set as input to get analog input
BACK: CLR P2.6 ; low-to-high
	SETB P2.6
HERE: JB P2.7, HERE
	SETB P2.5
	MOV A, P1; read analog input
	CLR P2.5; high-to-low
	SJMP BACK
```
