# RISC 16 Bit Processor
A 16-bit Reduced Instruction Set Computer (RISC) processor is a type of microprocessor designed for efficiency and speed by employing a simplified instruction set. Unlike Complex Instruction Set Computers (CISCs), RISC architectures utilize a smaller number of fixed-length instructions, typically executed in a single clock cycle. This streamlined approach leads to several advantages:   

Simplified Design: The reduced complexity of the instruction set translates to a simpler processor design, requiring fewer transistors. This can result in lower power consumption, smaller die size, and potentially lower manufacturing costs – all crucial considerations for many projects.   
Faster Execution: With most instructions executing in a single clock cycle, RISC processors can achieve higher instruction throughput compared to CISC processors that often have multi-cycle instructions. This can lead to better overall performance for many applications.   
Efficient Memory Access: RISC architectures often feature a load-store architecture, meaning that memory is accessed primarily through dedicated load and store instructions. This separation simplifies instruction formats and can optimize memory management.   
Pipelining Potential: The fixed-length, simple instructions of RISC architectures are well-suited for instruction pipelining, a technique that allows multiple instructions to be in different stages of execution simultaneously, further enhancing performance.   
For a 16-bit implementation, the processor would handle data in 16-bit chunks. This word size is often a good compromise between the processing power needed for many embedded applications and the resource constraints of a project. A 16-bit address bus would typically allow for addressing up to 2^16 = (65,536) memory locations.   

When considering a 16-bit RISC processor for your project, you might look at existing open-source designs or consider defining your own instruction set architecture (ISA) based on the specific requirements of your application. Key design decisions would include:

Instruction Set: Defining the specific set of simple instructions the processor will support (e.g., arithmetic, logical, load/store, control flow). The number of instructions will be significantly less than a CISC architecture.
Register File: Determining the number and size (16-bit) of general-purpose registers, which are used to hold operands and intermediate results, minimizing memory access.
Addressing Modes: Deciding how memory addresses will be calculated (e.g., immediate, direct, register indirect, indexed).

Component Block Diagrams

Register File:

![image](https://github.com/user-attachments/assets/b944a457-f473-46a9-8703-59ce3b86a418)

Data Memory:

![image](https://github.com/user-attachments/assets/bced41e8-1df9-48ad-929a-398b324ae14a)

ALU:

![image](https://github.com/user-attachments/assets/b9e2ddda-af72-44cf-9762-cba0106f7dd3)

Control Unit:

![image](https://github.com/user-attachments/assets/09b80ead-9cdf-48ac-95b4-fea067904cc9)

RISC CPU:

![image](https://github.com/user-attachments/assets/5e7b581f-21f9-4946-b582-5da72b27e05c)


ISA
Instructions
Terms:
R = register
U = unused
rD = destination register
rM = first operand register
rN = second operand register
c = condition bit
I(8)/(5) = immediate data bits, 8 or 5
Instruction	Form	Implementation	Condition bit	OPCODE
ADD	RRR	rD = rM + rN	c: 1/0 = signed/unsigned	0000
SUB	RRR	rD = rM - rN	c: 1/0 = signed/unsigned	0001
NOT	RRU	rD = not rN	c: N/A	0010
AND	RRR	rD = rM and rN	c: N/A	0011
OR	RRR	rD = rM or rN	c: N/A	0100
XOR	RRR	rD = rM xor rN	c: N/A	0101
LSL	RRI(5)	rD = rM << rN	c: N/A	0110
LSR	RRI(5)	rD = rM >> rN	c: N/A	0111
CMP	RRR	rD = cmp(rM, rN)	c: 1/0 = signed/unsigned	1000
B	UI(8)	PC = rM or 8-bit immediate	c: 1/0 = rM/8-bit immediate	1001
BEQ	URR	PC = rM conditional on rN	c: N/A	1010
IMMEDIATE	RI(8)	rD = 8-bit immediate	c: 1/0 = upper/lower 8-bits	1011
LD	RRU	rD = memory(rM)	c: N/A	1100
ST	URR	memory(rM) = rN	c: N/A	1101

Instruction layout

Processor Control Unit Design

![image](https://github.com/user-attachments/assets/4a329095-ecba-4c5f-a4b0-725eda57b23d)

ALU Control Unit Design

![image](https://github.com/user-attachments/assets/06c1f421-e0ae-4df2-8047-42186701f592)

Updates:
All the Data memory had been imposed only instruction memory is not fetched. Working on it to show the complete waveform of the of the processor. It the best we have achieved so faar.

![image](https://github.com/user-attachments/assets/1804a2b5-f1a8-4469-af2b-8c97ba4fa77c)

Schematic:

link to schematic : https://pdflink.to/e50c6e37/









