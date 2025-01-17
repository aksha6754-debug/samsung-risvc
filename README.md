
# RISC-V Internship program powered by SAMSUNG and VSD
## This RISC-V Internship using VSDSquadron Mini is based on RISC-V architecture and uses open-source tools to teach students about VLSI SoC Design and RISC-V. The instructor and guide for this internship is Kunal Ghosh Sir, Founder of VSD.
# Basic Details
## Name: Aksha K B
## College: Sahyadri College of Engineering and Management, Mangalore 575007
## Email ID: aksha.ec22@sahyadri.edu.in
## GitHub Profile: aksha6754-debug
## LinkedIn Profile: Aksha K B
# Task 1
## C based lab screenshots
![Screenshot 2025-01-07 200344](https://github.com/user-attachments/assets/eac3055b-0ed5-45cc-8940-1707054030c9)
![Screenshot 2025-01-07 200141](https://github.com/user-attachments/assets/9618fab5-3a55-45ae-822c-94a22a8d5869)

## RISC-V based lab screenshot 
![riscv prg1](https://github.com/user-attachments/assets/abb2f63f-bcad-4c59-ab5e-d2e14a8e98ec)
![riscv prg2](https://github.com/user-attachments/assets/26e783bd-d7ce-48b7-9650-b2471415ea67)

# Task 3
## The following 15 instructions are shown below:
## Instruction 1: lui a0, 0x2b
Screenshot 2025-01-16 183517
![instr 1 T3](https://github.com/user-attachments/assets/06279cbb-67b7-4559-a412-ff5a1a88b915)

Operation: Load the upper 20 bits of an immediate (0x2b) into register a0.

Opcode: 0110111 (for lui)
Destination Register (rd): a0 → x10 (binary: 01010)
Immediate (imm[31:12]): 0x2b → 0000000000101011 (binary)
Encoding into Machine Code:

imm[31:12] | rd | opcode --->0000000000101011 | 01010 | 0110111

Binary: 0000000000101011010100110111
Hexadecimal: 0x002b537

## Instruction 2: addi sp, sp, -32
Screenshot 2025-01-16 184848
![Instr 2 T3](https://github.com/user-attachments/assets/dffc8915-d600-4bad-b69d-ea5a0fe41a20)

Operation: Add -32 to the stack pointer (sp).

Opcode: 0010011 (for immediate arithmetic operations like addi)
Function (funct3): 000 (for addition)
Source Register (rs1): sp → x2 (binary: 00010)
Destination Register (rd): sp → x2 (binary: 00010)
Immediate (imm[11:0]): -32 → 1111111111100000 (12-bit two’s complement)
Encoding into Machine Code:

imm[11:0] | rs1 | funct3 | rd | opcode -----> 111111111110 | 00010 | 000 | 00010 | 0010011

Binary: 11111111111000010000100110011
Hexadecimal: 0xfe010113

## Instruction 3: sd ra, 24(sp)
Screenshot 2025-01-16 184929
![instr 3 T3](https://github.com/user-attachments/assets/b85e1e8d-ee3c-4e9c-b266-23314dcf9f8c)

Operation: Store the value in ra into memory at offset 24 from sp.

Opcode: 0100011 (for store instructions)
Function (funct3): 011 (for sd, store double-word)
Source Register 1 (rs1): sp → x2 (binary: 00010)
Source Register 2 (rs2): ra → x1 (binary: 00001)
Immediate (imm[11:0]):
imm[11:5]: 0000011
imm[4:0]: 11000
Encoding into Machine Code:

imm[11:5] | rs2 | rs1 | funct3 | imm[4:0] | opcode ------> 0000011 | 00001 | 00010 | 011 | 11000 | 0100011

Binary: 000001100001000100110000100011

Hexadecimal: 0x01801323

## Instruction 4: jal ra, 10438
Screenshot 2025-01-16 184953
![instr 4 T3](https://github.com/user-attachments/assets/e1509d89-7c08-43ad-a2d0-1526aad5888f)

Operation: Jump to the address 10438 and store the return address in ra.

Opcode: 1101111 (for jal).

Destination Register (rd): ra is x1 (binary: 00001).

Immediate (imm[20|10:1|11|19:12]):

Immediate 10438 in binary: 001010001001110 (split into fields):

imm[20]: 0

imm[10:1]: 0100010011

imm[11]: 0

imm[19:12]: 00101000

Encoding into Machine Code:

imm[20|10:1|11|19:12] | rd | opcode -------> 0|0100010011|0|00101000| 00001 | 1101111

Binary: 0000000100100011000101110111
Hexadecimal: 0x370001e7

## Instruction 5: ret
Screenshot 2025-01-17 135951
![instr 5 T3](https://github.com/user-attachments/assets/d9c23c0d-0459-4110-91fd-19ab1aa0a842)

Operation: Return to the calling function. This is equivalent to jalr x0, ra, 0 in RISC-V assembly.

Opcode: 1100111 (for jalr)
Source Register (rs1): ra → x1 (binary: 00001)
Destination Register (rd): x0 → x0 (binary: 00000)
Immediate: 0
Encoding into Machine Code:

imm[11:0] | rs1 | funct3 | rd | opcode -----> 000000000000 | 00001 | 000 | 00000 | 1100111

Binary: 00000000000000010000000001110011
Hexadecimal: 0x00000067

## Instruction 6: bnez a5, offset
Screenshot 2025-01-17 130933
![instr 6 T3](https://github.com/user-attachments/assets/fb3c5ad8-e0a3-40b6-bb5c-6b3e49250b8b)

Operation: Branch to the specified offset if the value in register a5 is not zero.

Opcode: 1100011 (for branch instructions)
Source Register (rs1): a5 → x15 (binary: 01111)
Function (funct3): 001 (for bnez, branch if not zero)
Immediate (offset): Branch target address relative to PC.
Encoding into Machine Code:

imm[12|10:5] | rs2 | rs1 | funct3 | imm[4:1|11] | opcode -----> 000000000000 | 01111 | 01111 | 001 | 00000 | 1100011

Binary: 000000000000011110001000000011
Hexadecimal: 0x000f0043

## Instruction 7: andi a5, a5, 1
Screenshot 2025-01-17 130917
![instr 7 T3](https://github.com/user-attachments/assets/5123a958-7ece-4f21-b73d-bcbd996bb9bf)

Operation: Performs a bitwise AND operation between the contents of register a5 and the immediate value 1, and stores the result back in a5.

Opcode: 0010011 (for immediate arithmetic operations like andi)
Function (funct3): 111 (for andi)
Source Register (rs1): a5 → x15 (binary: 01111)
Destination Register (rd): a5 → x15 (binary: 01111)
Immediate: 1
Encoding into Machine Code:

imm[11:0] | rs1 | funct3 | rd | opcode -----> 000000000001 | 01111 | 111 | 01111 | 0010011

Binary: 00000000000101111000111110010011
Hexadecimal: 0x001f7b13

## Instruction 8: lw a5, 12(sp)
Screenshot 2025-01-17 130856
![instr 8 T3](https://github.com/user-attachments/assets/1491b38c-de4e-4e36-8d6e-0e785af28402)

Operation: Load a word from memory at offset 12 from the stack pointer (sp) into register a5.

Opcode: 0000011 (for load instructions)
Function (funct3): 010 (for lw, load word)
Source Register (rs1): sp → x2 (binary: 00010)
Destination Register (rd): a5 → x15 (binary: 01111)
Immediate (imm[11:0]): 12 → 00000000001100 (binary)
Encoding into Machine Code:

imm[11:0] | rs1 | funct3 | rd | opcode -----> 000000000011 | 00010 | 010 | 01111 | 0000011

Binary: 00000000001100010000101110000011
Hexadecimal: 0x0002c783

## Instruction 9: li a0, 0
Screenshot 2025-01-17 131023
![instr 9 T3](https://github.com/user-attachments/assets/d239740e-11f5-4d0d-befd-8e2ff1e58662)

Operation: Load the immediate value 0 into register a0.

Opcode: 0010011 (for immediate arithmetic operations like li)
Function (funct3): 000 (for addi operation)
Source Register (rs1): x0 (binary: 00000)
Destination Register (rd): a0 → x10 (binary: 01010)
Immediate (imm[11:0]): 0 → 000000000000 (binary)
Encoding into Machine Code:

imm[11:0] | rs1 | funct3 | rd | opcode -----> 000000000000 | 00000 | 000 | 01010 | 0010011

Binary: 00000000000000000000101000010011
Hexadecimal: 0x00000293

## Instruction 10: j 100ec <main+0x3c>
Screenshot 2025-01-17 131055
![instr 10 T3](https://github.com/user-attachments/assets/50828858-8b46-43cc-8d42-e2664dd6eca9)

Operation: Perform an unconditional jump to the target address 100ec, which is main+0x3c.

Opcode: 1101111 (for j jump instructions)
Immediate (imm[20|10:1|11|19:12]):
Immediate 100ec in binary: 000001001110110100000000000000 (split into fields)
imm[20]: 0
imm[10:1]: 0011101101
imm[11]: 0
imm[19:12]: 00000000
Encoding into Machine Code:

imm[20|10:1|11|19:12] | rd | opcode -----> 0|0011101101|0|00000000| 00000 | 1101111

Binary: 00000000001110110101000000001111
Hexadecimal: 0xfe5ff06f

## Instruction 11: ld ra, 24(sp)
Screenshot 2025-01-17 130958

Operation: Load a double-word from memory at offset 24 from the stack pointer (sp) into register ra.

Opcode: 0000011 (for load instructions)
Function (funct3): 011 (for ld, load double-word)
Source Register (rs1): sp → x2 (binary: 00010)
Destination Register (rd): ra → x1 (binary: 00001)
Immediate (imm[11:0]): 24 → 00000000011000 (binary)
Encoding into Machine Code:

imm[11:0] | rs1 | funct3 | rd | opcode -----> 000000000110 | 00010 | 011 | 00001 | 0000011

Binary: 00000000011000010001000110000011
Hexadecimal: 0x01813083

## Instruction 12: auipc ra, 0x0
Screenshot 2025-01-17 142008

Operation: Adds the program counter (PC) value and an immediate value 0x0, and stores the result in ra.

Opcode: 0010111 (for auipc, add upper immediate to program counter)
Destination Register (rd): ra → x1 (binary: 00001)
Immediate (imm[31:12]): 0x0 → 000000000000 (binary)
Encoding into Machine Code:

imm[31:12] | rd | opcode -----> 000000000000 | 00001 | 0010111

Binary: 00000000000000000000000101110111
Hexadecimal: 0x00000097

## Instruction 13: jalr zero, 0x0(main-0x100b0)
Screenshot 2025-01-17 142109

Operation: Perform a jump and link register to the address main-0x100b0 and write the return address to zero.

Opcode: 1100111 (for jalr jump and link register)
Function (funct3): 000 (for jalr with x0 as destination)
Source Register (rs1): main → x1 (binary: 00001)
Immediate (imm[11:0]): 0x0 → 000000000000 (binary)
Encoding into Machine Code:

imm[11:0] | rs1 | funct3 | rd | opcode -----> 000000000000 | 00001 | 000 | 00000 | 1100111

Binary: 00000000000000001000000000001111
Hexadecimal: 0x000000e7

## Instruction 14: jr zero # 0 <main-0x100b0>
Screenshot 2025-01-17 142817

Operation: Perform a jump register to the address main-0x100b0 and write the return address to register zero.

Opcode: 1100011 (for jr jump register)
Function (funct3): 000 (for jr with x0 as destination)
Source Register (rs1): main → x1 (binary: 00001)
Immediate (imm[11:0]): 0x0 → 000000000000 (binary)
Encoding into Machine Code:

imm[11:0] | rs1 | funct3 | rd | opcode -----> 000000000000 | 00001 | 000 | 00000 | 1100011

Binary: 00000000000000001000000000000011
Hexadecimal: 0x00000067

## Instruction 15: mv a1, a0
Screenshot 2025-01-17 142801

Operation: Move the value in register a0 to register a1.

Opcode: 0110011 (for R-type register operations like mv)
Function (funct3): 000 (for mv operation)
Source Register (rs1): a0 → x10 (binary: 01010)
Source Register (rs2): a0 → x10 (binary: 01010)
Destination Register (rd): a1 → x11 (binary: 01011)
Function (funct7): 0000000 (for mv operation)
Encoding into Machine Code:

funct7 | rs2 | rs1 | funct3 | rd | opcode -----> 0000000 | 01010 | 01010 | 000 | 01011 | 0110011

Binary: 00000000010101001010100000000011
Hexadecimal: 0x00050593

