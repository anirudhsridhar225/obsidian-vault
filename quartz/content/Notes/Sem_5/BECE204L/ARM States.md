The state of the ARM core determines which out of the three instruction sets to be executed. The 3 sets are ARM, Thumb and Jazelle.

ARM state: 32-bit instructions
Thumb state: thumb 16-bit instructions
Jazelle state: 8-bit instructions (hybrid mix of s/w and h/w designed to speed up execution of java byte codes)

> you CANNOT intermingle sequential ARM, Thumb and Jazelle instructions.

The Jazelle `J` and Thumb `T` bits in the CPSR #cpsr register reflect state:
- `J=0 && T=0`: ARM state
- `T=1`: Thumb state
- `J=1 && T=0`: Jazelle state

