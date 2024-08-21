# Von Neuman Arch
Modern computers use ISA(ix set arch) and are stored program computers.

## Parts
1. CPU
2. Memory Unit
3. I/O

### CPU
1. Control Unit
2. ALU
3. Registers

### Control Unit
Handle signals from and to processor, is incharge of fetching instructions, decoding them and controls their execution, also handles storing data into registers.

[To Read](https://www.geeksforgeeks.org/introduction-of-control-unit-and-its-design/)

### ALU
Handles math and logical operations - Add, sub, mul, div. Also does bitwise and logical operations.

### Registers
High performance storage units for the cpu.
#### Accumulator
Result of ALU is stored here.
#### Program Counter
Keeps track of address of next instruction that needs to be fetched.
It works with the MAR(Memory Address Register) to send it the address of next ix.
#### MAR
The mem address register keeps track of the address of the instructions to be fetched or stored currently.
#### MDR(Memory Data Register)
It stores any instructions fetch from memory or data that is transfered to or stored from memory.
#### Current Instruction Register
Stores the most recently fetched instruction from memory that is currently in process or awaiting execution.
#### Instruction Buffer Register
Instructions that are not to be executed immediately i.e buffered.

### Buses
Data Bus - Carries Data between cpu and memory and I/O.
Address Bus - Carries address of the data between cpu and memory.
Control Bus - Carries Control signals from cpu and other devices to coordinate functions of the computer.

# Harvard
Main difference is separate busses for instruction and data fetch, Modified harvard goes one step further(but starts looking kind of like von neumann)
where it allows fetching instructions as data.
