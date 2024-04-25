***
#### Beyond CPU and Memory
`Memory Bus`
* Data/control path connecting CPU, main memory and I/O Bus

`I/O Bus`
* Data/control path connecting Memory Bus and I/O Controllers

`I/O Controller`
* A processor running software for one type of device
* Connects I/O device to I/O bus

`I/O Device`
* I/O mechanism that generates or consumes data
#### PIO Limitations
* Reading/writing large amounts of data slows CPU
	* CPU is mostly waiting for controller

**KEY OBSERVATION**: CPU and I/O controllers are *independent processors*
* They should be permitted to work in parallel
* Either should be able to initiate data transfer to/from memory
* Either should be able to signal the other to get attention

#### Autonomous Controller Operation
* `Direct Memory Access`
	* Controller can send/read data from/to any main memory address
	* CPU is oblivious to these transfers
	* DMA addresses and sizes are programmed by CPU using PIO
* `CPU Interrupts`
	* Controller can signal the CPU when needed
	* CPU checks for interrupts on every cycle
		* Very fast, clock-speed poll
	* CPU jumps to controller's *Interrupt*

#### PIO, DMA and Interrupts
`PIO`
* Data transfer
* CPU $\leftrightarrow$ Controller
* Initiated by CPU

`DMA`
* Data transfer
* Controller $\leftrightarrow$ Memory
* Initiated by Controller

`Interrupt`
* Control transfer
* Controller $\leftrightarrow$ CPU
