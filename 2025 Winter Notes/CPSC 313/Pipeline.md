***
**Data Hazards**: When data dependencies potentially lead to incorrect behaviour
* e.g. one instruction reads from a register that another one writes
**Control Hazard**: When control dependencies potentially lead to incorrect behaviour
* e.g. a conditional jump determines the address of the next instruction to execute
**Latency**: End to end time to complete execution of a single instruction
**Retirement Latency**: Time between the completion of one instruction and the completion of the next instruction
**Throughput**: The rate at which instructions complete
* Typically expressed in GIPS: giga instructions per second

###### Conversions
Millisecond (ms): $10^{-3}$
Microsecond (µs): $10^{-6}$
Nanosecond (ns): $10^{-9}$
Picosecond (ps): $10^{-12}$

GIPS: $10^9$ instructions per second

###### Sequential vs Pipeline Performance


