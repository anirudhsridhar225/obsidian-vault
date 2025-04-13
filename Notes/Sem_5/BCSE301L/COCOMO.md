3 types of projects:
	1. organic type: small (2-50 KLOC)
	2. semidetached type: medium (50-300 KLOC)
	3. embedded type: large (>300 KLOC)

3 models:
	1. basic
	2. intermediate
	3. detailed

# Basic COCOMO
$E$ = $a*(KLOC)^b$
$Time$ = $c*(E)^d$
Persons req = E/Time
Productivity = KLOC/E

| S/W Proj      | a   | b    | c   | d    |
| ------------- | --- | ---- | --- | ---- |
| organic       | 2.4 | 1.05 | 2.5 | 0.38 |
| semi-embedded | 3.0 | 1.12 | 2.5 | 0.35 |
| embedded      | 3.6 | 1.20 | 2.5 | 0.32 |

# Intermediate COCOMO
Cost drivers:
1. Product Attributes
	1. required s/w reliability
	2. size of application database
	3. complexity of the product
2. Hardware Attributes
	1. runtime performance constraints
	2. memory constraints
	3. virtual machine volatility
	4. turnaround time
3. Personal Attributes
	1. analyst capability
	2. programmer capability
	3. application experience
	4. virtual m/c experience
	5. prog lang experience
4. Project Attributes
	1. modern programming practices
	2. use of software tools
	3. req dev schedule

![[{330F27D7-3429-4EE5-9682-C236D9A23269}.png]]
![[{19FE1EA8-CCCE-4F23-A842-29E29A069B02}.png]]

