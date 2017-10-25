# CSC1202 Lecture Slides Answers

## Computer Evolution and Performance Issues

### Chapter 1 - Basic Concepts & Computer Evaluation
1. Distinguish between structure and funciton:

    - Structure: The way in which components relate to each other.
    - Function: The operation of individual components as part of the structure.

2. Name Two Assembly Language applications:
    - Direct hardware manipulation, accessing specialized processor instructions, address critical performance issues.

### Chapter 2 - Performance Issues
1. Processing speed is an important feature of computer's performance. What else is considered important when buying a computer?

## Number Systems and Computer Arithmetic

### Chapter 9 - Number Systems
1.

### Chapter 10 - Computer Arithmetic
1.

## Digital Logic

### Chapter 11 - Digital Logic
1.

## Instruction sets: Characteristics and Functions, Addressing Modes and Formats

### Chapter 12 - Instruction Sets: Characteristics and Functions
1.

### Chapter 13 - Instruction Sets: Addressing Modes and Formats
1.

## Computer Functions and Interconnections, Cache, Internal and External Memory, Input/Output

### Chapter 4 - Cache Memory
1. What is cache memory?
    - A small type of volatile memory that provides high-speed access to a processor. It is the fastest memory in a computer, and is typically integrated into the processor.

2. Why is cache memory considered an essential part of a typical computer memory design?
    - Cache provides faster data access by storing instances of program and data routinely accessed by the processor. Other types of memory are too slwo to keep up with the processor.

### Chapter 5 - Internal Memory
1. What are the differences between SRAM and DRAM in terms of speed and cost?
     SRAM | Both | DRAM
     -----|------|-----
    simpler to build, smaller | volatile | faster
    denser, cheaper | | used for cache memory
    used for main memory |

2. What is ROM? Give to applications of ROM.
    - ROM : contains permanent data that cannot be changed/added to
    - used for : BIOS, game cartridges, firmware

3. Describe flash memory. Identify one popular way that flash memory is used.
    - Uses electrical erasing technologies, does not provide byte-level erasure. Microchip is organized so that a section of memory cells are erased in a flash.
    - Used as RAM, SSD, thumb drives.

### Chapter 6 - External Memory
1. What is a Solid State Drive (SSD)? Identify a common type of SSD.
    - A memory device made with solid state components that can be used as a HDD replacement. A common type of SSD: NAND flash.

### Chapter 7 - Input/Output
1. Describe the weaknesses of programmed and interrupt-driven I/O. What has the industry proposed to overcome these weaknesses?
    - Weaknesses:
        - I/O rate limited by the speed with which the processor can test & service a device.
        - Processor is tied up in managing an I/O transfer; a number of intructions must be executed for each I/O transfer.
    - Proposed:
        - A more efficient technique: Direct Memory Access (DMA)

### Chapter 3 - A Top-Level View of Computer Function and Interconnection
1. Describe the tuerm 'software'.
    - A sequence of codes and instructions, part of the hardware inteprets each instruction and generates control signals, provide a new sequence of codes for each new program instead of rewiring the hardware.

2. What is an interrupt and when would you use it?
    - A pause/stop in program execution. Used when an illegal access is attempted, to allow IS to perform certain function, to signal the end of execution, to signal errors. (hardware and software errors)

3. A key characteristic of a bus in that it is a shared transmission medium. Why is this considered useful?
    - Provides a pathway between components. Multiple buses allow different components at various levels of the computer system hierachy to communicate at the same time.

## Processor Structure and Function, Control Unit Operation, Microprogramming Control

### Chapter 14, 20, 21
1. What are general purpose registers used for?
    - Enables the machine or assembly language programmer to minimize main memory references by optimising use of registers (slide 9)

2. What are condition codes? Discuss one advantage of using such codes.
    - Also referred as flags, they are bits set by the processor hardware as the result of the operations (slide 10) e.g the condition codes can be saved on the stack during subroutine calls along with other register info (slide 11)

3. Explain the role of the Sign bit in the Program Status Word (PSW)
    - Sign of the last arithmetic operation, "1" indicates a negative result, "0" otherwise.

4. What is the advantage of instruction pipelining? What is key to pipeline efficiency?
    - Achieves parallelism wihtout replication, improves processor performance (slide 23). Keeping the pipeline full (slide23)

5. Describe the role of the control unit in the CPU.
    - It generates the control signals for the micro-operations to be executed (slide 38)

6. What is a micro-operation?
    - It is the most basic and fundamental operation that involves registers (slide 39)

7. Discuss the sequencing function of the control unit.
    - Causes the CPU to step through a series of micro-operations in the proper sequence/order, based on the program (slide 44)

8. Name a typical method to implement the control unit.
    - Hardwired/microprogrammed (slide 46)

9. Wbat is a microprogram?
    - A sequence of microinstructions

10. What is a common term for a microprogram?
    - Firmware

11. Briefly describe horizontal microprogramming. How is it different from vertical programming?
    - Wide memory word, high degree of parallelism, little encoding of control information (slide 53).
    - In horizontal, every bit in the control field is attached to the control line.
    - For vertical, it can be decoded to use fewer bits. Parallelism.

12. Name one advantage of implementing microprogramming.
    - Cheaper/less error prone (slide 56)

## RISC, Parallelism, Superscalar Concepts, Multicore Computer, GPUs and Industry Trends

### Chapter 15
1.

### Chapter 16 - 19
1.
