# CSC1202 Lecture Slides Answers

## Computer Evolution and Performance Issues

#### Chapter 1 - Basic Concepts & Computer Evaluation
1. Distinguish between structure and funciton:
    * Structure: The way in which components relate to each other.
    * Function: The operation of individual components as part of the structure.


2. Name Two Assembly Language applications:
    * Direct hardware manipulation, accessing specialized processor instructions, address critical performance issues.


#### Chapter 2 - Performance Issues
1. Processing speed is an important feature of computer's performance. What else is considered important when buying a computer?
    * Storage, RAM size, etc.


----------
## Number Systems and Computer Arithmetic

#### Chapter 9 - Number Systems
1. Find the ASCII hexadecimal code for the character "a"
    * 61


2. Find the ASCII decimal code for the character " " (space)
    * 32


3. Decipher this person's identity by converting the ASCII hexadecimal codes into their equivalent characters. `45 2E 20 53 61 6C 74`
    * E. Salt


#### Chapter 10 - Computer Arithmetic
1. Explain the term "overflow".
    * If two numbers with the same sign (both positive or negative) are added, then overflow occurs if and only if the result has the opposite sign.


2. Discuss the responsibilities of the ALU.
    * Performs arithmetic and logical operations on data.
    * Everything else in the computer is there to service this unit.
    * Handles integers, performs simple Boolean logic operations


3. What steps would you take to obtain the twos complement representation of a negative number?
    * Take the positive equivalent's binary form and invert all bits, then add 1. Eg, 55 in binary would be `0011 0111`, so twos complement representation of -55 would be `1100 1000` then added `1` to become `1100 1001`


4. How would you represent -23 in twos complement form?
    * 23<sub>10</sub> would be `0001 0111`<sub>`2`</sub> , so -23<sub>10</sub> would be `11101001`<sub>`2`</sub>


5. Why is normalization necessary? Give an example of a normalized number.
    * Normalization is necessary to simplify operations on floating-point numbers. An example of a normalized number would be 1234 becoming 1.234x10<sup>3</sup>


----------
## Digital Logic

#### Chapter 11 - Digital Logic
1. Draw a Karnaugh map to simplify

2. Design the corresponding combinational circuits of the simplified forms in the previous question.

3. Differentiate between combinational and sequential circuits.

4. What type of circuit has _"two outputs which are complements of each other"_?

----------

## Instruction sets: Characteristics and Functions, Addressing Modes and Formats

#### Chapter 12 - Instruction Sets: Characteristics and Functions
1. Is it possible to write an instruction using only one address? How would you do this?

2. Explain the little-endianbyte ordering scheme.

3. Differentiate between the "shift" and "rotate" operations.

#### Chapter 13 - Instruction Sets: Addressing Modes and Formats
1. Give an example of an instruction used in direct addressing.
    * `ADD B` - Add contents of register B to accumulator.
    * `ADD a` - Look in memory at address `a` for operand.


2. How is register addressing different from register indirect addressing?
    * Register addressing refers to a register space, indirect addressing refers to a pointer in memory that points to an operand.


3. How is indirect addressing similar to register indirect addressing?
    * Indirect addressing and register indirect addressing both refers to a pointer to operand, only difference is the pointer in indirect addressing is stored in memory while the pointer in register indirect addressing is stored in the register.


4. Identify the addressing modes of the following instructions:
    * `MVI D,00`
    * `LDA C020`
    * `MOV C,M`
    * `INX H`
    * `MOV B,C`


5. There are 5 types of addressing modes: (Parentheses are to be interpreted as _contents of_)
    Addresing Mode | Algorithm | Main Advantage | Main Disadvantage
    -----|-----|-----|-----
    Immediate | Operand = A | No memory reference | Limited operand magnitude
    Direct | EA = A | Simple | Limited address space
    Indirect | EA = (A) | Large address space | Multiple memory references
    Register | EA = R | No memory reference | Limited address space
    Register Indirect | EA = (R) | Large address space | Extra memory reference
    Stack | EA = top of stack | No memory reference | Limited applicability


    **Examples of addressing modes**
    Addresing Mode | Explanation | Example
    -----|-----|-----
    Immediate | Operand is part of instruction | `ADD 5` - Add 5 to accumulator
    Direct | Address field contains address of operand | `ADD (a)` - Add contents of memory location `(a)` to accumulator
    Indirect | Memory cell pointed to by address field contains the address of (pointer to) the oprand | `ADD (a)` - add contents of the memory location pointed to by `(a)` to accumulator (`(a)` is a pointer in a memory cell)
    Register | Operand is held in register named in address filed | `MOV A, B` - move contents of register `B` to register `A`
    Register Indirect | Operand is in memory location pointed to (pointer) by contents of register R | `ADD (a)` - add contents of the memory location pointed to by `(a)` to accumulator (`(a)` is a pointer in register)
    Stack | Operand is (implicitly) on top of stack | `PUSH B` - copy values from register B onto stack


----------
## Computer Functions and Interconnections, Cache, Internal and External Memory, Input/Output

#### Chapter 4 - Cache Memory
1. What is cache memory?
    * A small type of volatile memory that provides high-speed access to a processor. It is the fastest memory in a computer, and is typically integrated into the processor.


2. Why is cache memory considered an essential part of a typical computer memory design?
    * Cache provides faster data access by storing instances of program and data routinely accessed by the processor. Other types of memory are too slwo to keep up with the processor.


#### Chapter 5 - Internal Memory
1. What are the differences between SRAM and DRAM in terms of speed and cost?

     SRAM | Both | DRAM
     -----|------|-----
    simpler to build, smaller | volatile | faster
    denser, cheaper | | used for cache memory
    used for main memory |


2. What is ROM? Give to applications of ROM.
    * ROM : contains permanent data that cannot be changed/added to
    * used for : BIOS, game cartridges, firmware


3. Describe flash memory. Identify one popular way that flash memory is used.
    * Uses electrical erasing technologies, does not provide byte-level erasure. Microchip is organized so that a section of memory cells are erased in a flash.
    * Used as RAM, SSD, thumb drives.


#### Chapter 6 - External Memory
1. What is a Solid State Drive (SSD)? Identify a common type of SSD.
    * A memory device made with solid state components that can be used as a HDD replacement. A common type of SSD: NAND flash.


#### Chapter 7 - Input/Output
1. Describe the weaknesses of programmed and interrupt-driven I/O. What has the industry proposed to overcome these weaknesses?
    * Weaknesses:
        * I/O rate limited by the speed with which the processor can test & service a device.
        * Processor is tied up in managing an I/O transfer; a number of intructions must be executed for each I/O transfer.
    * Proposed:
        * A more efficient technique: Direct Memory Access (DMA)


#### Chapter 3 - A Top-Level View of Computer Function and Interconnection
1. Describe the term 'software'.
    * A sequence of codes and instructions, part of the hardware inteprets each instruction and generates control signals, provide a new sequence of codes for each new program instead of rewiring the hardware.


2. What is an interrupt and when would you use it?
    * A pause/stop in program execution. Used when an illegal access is attempted, to allow IS to perform certain function, to signal the end of execution, to signal errors. (hardware and software errors)


3. A key characteristic of a bus in that it is a shared transmission medium. Why is this considered useful?
    * Provides a pathway between components. Multiple buses allow different components at various levels of the computer system hierachy to communicate at the same time.


----------
## Processor Structure and Function, Control Unit Operation, Microprogramming Control

#### Chapter 14 - Processor Structure and Function
1. What are general purpose registers used for?
    * Enables the machine or assembly language programmer to minimize main memory references by optimising use of registers (slide 9)


2. What are condition codes? Discuss one advantage of using such codes.
    * Also referred as flags, they are bits set by the processor hardware as the result of the operations (slide 10) e.g the condition codes can be saved on the stack during subroutine calls along with other register info (slide 11)


3. Explain the role of the Sign bit in the Program Status Word (PSW)
    * Sign of the last arithmetic operation, "1" indicates a negative result, "0" otherwise.


4. What is the advantage of instruction pipelining? What is key to pipeline efficiency?
    * Achieves parallelism wihtout replication, improves processor performance (slide 23). Keeping the pipeline full (slide23)


#### Chapter 20 - Control Unit Operation
1. Describe the role of the control unit in the CPU.
    * It generates the control signals for the micro-operations to be executed (slide 38)


2. What is a micro-operation?
    * It is the most basic and fundamental operation that involves registers (slide 39)


3. Discuss the sequencing function of the control unit.
    * Causes the CPU to step through a series of micro-operations in the proper sequence/order, based on the program (slide 44)


4. Name a typical method to implement the control unit.
    * Hardwired/microprogrammed (slide 46)


#### Chapter 21 - Microprogrammed Control
1. What is a microprogram?
    * A sequence of microinstructions


2. What is a common term for a microprogram?
    * Firmware


3. Briefly describe horizontal microprogramming. How is it different from vertical programming?
    * Wide memory word, high degree of parallelism, little encoding of control information (slide 53).
    * In horizontal, every bit in the control field is attached to the control line.
    * For vertical, it can be decoded to use fewer bits. Parallelism.


4. Name one advantage of implementing microprogramming.
    * Cheaper/less error prone (slide 56)


----------
## RISC, Parallelism, Superscalar Concepts, Multicore Computer, GPUs and Industry Trends

#### Chapter 15
1. Compare TWO key characteristics that can differentiate CISC and RISC.
    CISC | RISC
    -----|-----
    Less register space | More register space
    More addressing modes | Less addressing modes
    Bigger instruction size | Smaller instruction size


2. How would you decide on the number of colours to be used for the graph colouring approach so as to optimize the number of real registers?

3. What is the objective of optimizing the instruction pipeline?
    * To enhance performance by running the next instruction cycle's stage as soon as the previous one is done ie. running different stages of a different instrution cycle at the same time.


#### Chapter 16 - 19
1. What is the advantage of a superscalar implementation?
    * It allows parallel fetch & execute, enhancing performance.


2. What is a superpipeline?
    * Many pipeline stages need less than half a usual clock cycle to finish. A double internal clock speed allows TWO tasks per clock cycle on average, therefore doubling performance compared to regular operations. That is superpipeline.


3. Explain the concept of parallel processing.
    * Breaking down large operations into smaller ones, then overlapping of them in parallel, running multiple instructions at the same time.


4. Briefly describe ONE characteristic of a Symmetric Multiprocessor.
    * Two or more identical processors are connected to a single, shared main memory.
    * Two or more identical processors that have full access to all I/O devices.
    * Two or more identical processors that are controlled by a single OS that treats all processors equally.


5. Discuss TWO performance issues that led to the development of multicore computers.
    Hardware:
    * More complex processors requires more logic.
    * Increasing chip area for coordinating and signal transfer logic (harder to design, manufacture and debug)

    Software:
    * Increasing clock frequency causes heat issues and an exponential increase in energy requirements.


6. Identify TWO popular applications that have successfully exploited multicore computers.
    * Multi-threated native applications - characterized by having a small number of highly threaded processes.
    * Multi-process applications - characterized by the presence of many single-threaded processes.
    * Java applications - JVM is a multi-threaded processes that provides scheduling and memory management for Java applications.
    * Multi-instance operations - One application running multiple times at once.


----------
## Exam Coverage

Part A - Two Questions
- Question 1 - MCQ (10m)
- Question 2 - Discussion type (20m)

Part B - Choose TWO out of THREE questions (2x10m)
- Chapters 3 - 7, 9 - 16, 20, 21
- Number systems & computer arithmetic: basic hex to binary, decimal to binary, twos complement, ASCII table will be provided
- Simple Assembly Language code: analyse no more than TEN lines of code to determine contents of register/status flag/memory location
- Internal Memory: cache memory vs regular internal memory
- Big-endian vs little-endian byte ordering schemes, shift vs rotate operations
- Program Status Word (what is this)
- Addressing modes - immediate vs indirect register vs register
- Reduce Boolean function using Karnaugh map (POS, SOP), simple circuit design from reduced Boolean function, combinational vs sequential circuits
- Instruction pipelining (What is it? Why use it? How does it work?), indirect addressing requires additional memory access
- What is RISC? RISC vs CISC, register optimization methods (software vs hardware)
- Concept of parallelism/parallel processing
- Micro-program, micro-program control unit, micro-operations
