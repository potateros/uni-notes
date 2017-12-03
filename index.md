# Content

<div id="contents"></div>

CSC 1202 - Computer Organization

* [CSC1202 Lecture Slides Answers](#csc1202-lecture)
  * [Chp 1, 2 - Computer Evolution and Performance Issues](#csc1202-compevo)
  * [Chp 9, 10 - Number Systems and Computer Arithmetic](#csc1202-numbers)
  * [Chp 11 - Digital Logic](#csc1202-logic)
  * [Chp 12, 13 - Instruction Sets: Chracteristics and Functions, Addressing Modes and Formats](#csc1202-instsets)
  * [Chp 3, 4, 5, 6, 7 - Computer Functions and Interconnections, Cache, Internal & External Memory, I/O](#csc1202-compfunc)
  * [Chp 14, 20, 21 - Processor Structure and Function, Control Unit Operation, Microprogramming Control](#csc1202-procstruct)
  * [Chp 15, 16-19 - RISC, Parallelism, Superscalar Concepts, Multicore Computer, GPUs and Industry Trends](#csc1202-multicore)

* [CSC1202 8085](#csc1202-8085)

* [CSC1202 Exam Coverage](#csc1202-exam)

PRG 1203 - Object Oriented Programming Fundamentals

* [PRG 1203 Exam Coverage](#prg1203-exam)

SEG 1201 - Database Fundamentals

* [SEG 1201 Lecture Notes](#seg1201-lecture)

WEB 1201 - Web Fundamentals

* [WEB1201 Exam Coverage](#web1201-exam)

<div id="csc1202-lecture"></div>

## CSC1202 Lecture Slides Answers

---------
<div id="csc1202-compevo"></div>

### Computer Evolution and Performance Issues

#### Chapter 1 - Basic Concepts & Computer Evaluation

1. **Distinguish between structure and funciton:**
    * Structure: The way in which components relate to each other.
    * Function: The operation of individual components as part of the structure.

1. **Name Two Assembly Language applications:**
    * Direct hardware manipulation, accessing specialized processor instructions, address critical performance issues.

#### Chapter 2 - Performance Issues

1. **Processing speed is an important feature of computer's performance. What else is considered important when buying a computer?**
    * Storage, RAM size, etc.

[Back to contents](#contents)

---------
<div id="csc1202-numbers"></div>

### Number Systems and Computer Arithmetic

#### Chapter 9 - Number Systems

1. **Find the ASCII hexadecimal code for the character "a"**
    * 61

1. **Find the ASCII decimal code for the character " " (space)**
    * 32

1. **Decipher this person's identity by converting the ASCII hexadecimal codes into their equivalent characters. `45 2E 20 53 61 6C 74`**
    * E. Salt

#### Chapter 10 - Computer Arithmetic

1. **Explain the term "overflow".**
    * If two numbers with the same sign (both positive or negative) are added, then overflow occurs if and only if the result has the opposite sign.

1. **Discuss the responsibilities of the ALU.**
    * Performs arithmetic and logical operations on data.
    * Everything else in the computer is there to service this unit.
    * Handles integers, performs simple Boolean logic operations

1. **What steps would you take to obtain the twos complement representation of a negative number?**
    * Take the positive equivalent's binary form and invert all bits, then add 1. Eg, 55 in binary would be `0011 0111`, so twos complement representation of -55 would be `1100 1000` then added `1` to become `1100 1001`

1. **How would you represent -23 in twos complement form?**
    * 23 would be `0001 0111`, so -23 would be `11101001`

1. **Why is normalization necessary? Give an example of a normalized number.**
    * Normalization is necessary to simplify operations on floating-point numbers. An example of a normalized number would be 1234 becoming 1.234x10

[Back to contents](#contents)

---------
<div id="csc1202-logic"></div>

### Digital Logic

#### Chapter 11 - Digital Logic

1. **Draw a Karnaugh map to simplify in Sum of Products (SOP) and Product of Sums (PSO) forms, if they exist.**

![karnaugh_q](./karnaugh_q.png)

2. **Design the corresponding combinational circuits of the simplified forms in the previous question.**

3. **Differentiate between combinational and sequential circuits.**

4. **What type of circuit has _"two outputs which are complements of each other"_?**


[Back to contents](#contents)

---------
<div id="csc1202-instsets"></div>

### Instruction sets: Characteristics and Functions, Addressing Modes and Formats

#### Chapter 12 - Instruction Sets: Characteristics and Functions

1. **Is it possible to write an instruction using only one address? How would you do this?**

1. **Explain the little-endianbyte ordering scheme.**

1. **Differentiate between the "shift" and "rotate" operations.**

#### Chapter 13 - Instruction Sets: Addressing Modes and Formats

1. **Give an example of an instruction used in direct addressing.**
    * `ADD B` - Add contents of register B to accumulator.
    * `ADD a` - Look in memory at address `a` for operand.

1. **How is register addressing different from register indirect addressing?**
    * Register addressing refers to a register space, indirect addressing refers to a pointer in memory that points to an operand.

1. **How is indirect addressing similar to register indirect addressing?**
    * Indirect addressing and register indirect addressing both refers to a pointer to operand, only difference is the pointer in indirect addressing is stored in memory while the pointer in register indirect addressing is stored in the register.

1. **Identify the addressing modes of the following instructions:**
    * `MVI D,00`
    * `LDA C020`
    * `MOV C,M`
    * `INX H`
    * `MOV B,C`

1. **There are 5 types of addressing modes: (Parentheses are to be interpreted as _contents of_)**

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

[Back to contents](#contents)

---------
<div id="csc1202-compfunc"></div>

### Computer Functions and Interconnections, Cache, Internal and External Memory, Input/Output

#### Chapter 3 - A Top-Level View of Computer Function and Interconnection

1. **Describe the term 'software'.**
    * A sequence of codes and instructions, part of the hardware inteprets each instruction and generates control signals, provide a new sequence of codes for each new program instead of rewiring the hardware.

1. **What is an interrupt and when would you use it?**
    * A pause/stop in program execution. Used when an illegal access is attempted, to allow IS to perform certain function, to signal the end of execution, to signal errors. (hardware and software errors)

1. **A key characteristic of a bus in that it is a shared transmission medium. Why is this considered useful?**
    * Provides a pathway between components. Multiple buses allow different components at various levels of the computer system hierachy to communicate at the same time.

#### Chapter 4 - Cache Memory

1. **What is cache memory?**
    * A small type of volatile memory that provides high-speed access to a processor. It is the fastest memory in a computer, and is typically integrated into the processor.

1. **Why is cache memory considered an essential part of a typical computer memory design?**
    * Cache provides faster data access by storing instances of program and data routinely accessed by the processor. Other types of memory are too slwo to keep up with the processor.

#### Chapter 5 - Internal Memory

1. **What are the differences between SRAM and DRAM in terms of speed and cost?**

     SRAM | Both | DRAM
     -----|------|-----
    simpler to build, smaller | volatile | faster
    denser, cheaper | | used for cache memory
    used for main memory |

1. **What is ROM? Give to applications of ROM.**
    * ROM : contains permanent data that cannot be changed/added to
    * used for : BIOS, game cartridges, firmware

1. **Describe flash memory. Identify one popular way that flash memory is used.**
    * Uses electrical erasing technologies, does not provide byte-level erasure. Microchip is organized so that a section of memory cells are erased in a flash.
    * Used as RAM, SSD, thumb drives.

#### Chapter 6 - External Memory

1. **What is a Solid State Drive (SSD)? Identify a common type of SSD.**
    * A memory device made with solid state components that can be used as a HDD replacement. A common type of SSD: NAND flash.

#### Chapter 7 - Input/Output

1. **Describe the weaknesses of programmed and interrupt-driven I/O. What has the industry proposed to overcome these weaknesses?**
    * Weaknesses:
        * I/O rate limited by the speed with which the processor can test & service a device.
        * Processor is tied up in managing an I/O transfer; a number of intructions must be executed for each I/O transfer.
    * Proposed:
        * A more efficient technique: Direct Memory Access (DMA)

[Back to contents](#contents)

---------
<div id="csc1202-procstruct"></div>

### Processor Structure and Function, Control Unit Operation, Microprogramming Control

#### Chapter 14 - Processor Structure and Function

1. **What are general purpose registers used for?**
    * Enables the machine or assembly language programmer to minimize main memory references by optimising use of registers (slide 9)

1. **What are condition codes? Discuss one advantage of using such codes.**
    * Also referred as flags, they are bits set by the processor hardware as the result of the operations (slide 10) e.g the condition codes can be saved on the stack during subroutine calls along with other register info (slide 11)

1. **Explain the role of the Sign bit in the Program Status Word (PSW)**
    * Sign of the last arithmetic operation, "1" indicates a negative result, "0" otherwise.

1. **What is the advantage of instruction pipelining? What is key to pipeline efficiency?**
    * Achieves parallelism wihtout replication, improves processor performance (slide 23). Keeping the pipeline full (slide23)

#### Chapter 20 - Control Unit Operation

1. **Describe the role of the control unit in the CPU.**
    * It generates the control signals for the micro-operations to be executed (slide 38)

1. **What is a micro-operation?**
    * It is the most basic and fundamental operation that involves registers (slide 39)

1. **Discuss the sequencing function of the control unit.**
    * Causes the CPU to step through a series of micro-operations in the proper sequence/order, based on the program (slide 44)

1. **Name a typical method to implement the control unit.**
    * Hardwired/microprogrammed (slide 46)

#### Chapter 21 - Microprogrammed Control

1. **What is a microprogram?**
    * A sequence of microinstructions

1. **What is a common term for a microprogram?**
    * Firmware

1. **Briefly describe horizontal microprogramming. How is it different from vertical programming?**
    * Wide memory word, high degree of parallelism, little encoding of control information (slide 53).
    * In horizontal, every bit in the control field is attached to the control line.
    * For vertical, it can be decoded to use fewer bits. Parallelism.

1. **Name one advantage of implementing microprogramming.**
    * Cheaper/less error prone (slide 56)

[Back to contents](#contents)

---------
<div id="csc1202-multicore"></div>

### RISC, Parallelism, Superscalar Concepts, Multicore Computer, GPUs and Industry Trends

#### Chapter 15

1. **Compare TWO key characteristics that can differentiate CISC and RISC.**

    CISC | RISC
    -----|-----
    Less register space | More register space
    More addressing modes | Less addressing modes
    Bigger instruction size | Smaller instruction size

1. **How would you decide on the number of colours to be used for the graph colouring approach so as to optimize the number of real registers?**
    * Number of colors to equal the number of registers (slide 13)
1. **What is the objective of optimizing the instruction pipeline?**
    * To enhance performance by running the next instruction cycle's stage as soon as the previous one is done ie. running different stages of a different instrution cycle at the same time.

#### Chapter 16 - 19

1. **What is the advantage of a superscalar implementation?**
    * It allows parallel fetch & execute, enhancing performance.

    * For superscalar, it has multiple functional units which enables the processor to execute streams of instuctions in parallel, one stream for each pipeline. (slide 5)

1. **What is a superpipeline?**
    * Many pipeline stages need less than half a usual clock cycle to finish. A double internal clock speed allows TWO tasks per clock cycle on average, therefore doubling performance compared to regular operations. That is superpipeline.

    * As many pipeline stages need less than half a clock cycle to perform its tasks, superpipline is whereby a double internal clock speed is introduced to allow two tasks per clock cycle. (slide 7)

1. **Explain the concept of parallel processing.**
    * Breaking down large operations into smaller ones, then overlapping of them in parallel, running multiple instructions at the same time.

1. **Briefly describe ONE characteristic of a Symmetric Multiprocessor.**
    * Two or more identical processors are connected to a single, shared main memory.
    * Two or more identical processors that have full access to all I/O devices.
    * Two or more identical processors that are controlled by a single OS that treats all processors equally.

1. **Discuss TWO performance issues that led to the development of multicore computers.**
    Hardware:
    * More complex processors requires more logic.
    * Increasing chip area for coordinating and signal transfer logic (harder to design, manufacture and debug)

    Software:
    * Increasing clock frequency causes heat issues and an exponential increase in energy requirements.

1. **Identify TWO popular applications that have successfully exploited multicore computers.**
    * Multi-threated native applications - characterized by having a small number of highly threaded processes.
    * Multi-process applications - characterized by the presence of many single-threaded processes.
    * Java applications - JVM is a multi-threaded processes that provides scheduling and memory management for Java applications.
    * Multi-instance operations - One application running multiple times at once.

[Back to contents](#contents)

---------

<div id="csc1202-8085"></div>

## 8085 Assembly

### 8085 Characteristics to Note:

* Registers use hexadecimal
* Memory locations uses decimal
* Subroutines == Functions

### 8085 Op Codes

Notes: Acc = Accumulator

Opcode | Function | Mnemonic
-----|-----|-----
`MVI X, Y` | Moves Y (hex/dec) to X immediately | Move Immediately
`MOV X, Y` | Moves content in register Y to register X | Move
`ADD X` | Adds content in register X to Acc | Add
`SUB X` | Subtracts content in register X from Acc | Subtract
`LDA X` | Loads content from memory X into Acc | Load from Accumulator
`STA X` | Stores content in Acc to memory X | Store To Accumulator
`ADI X` | Increments Acc by X | Add to Immediately
`SUI X` | Decrements Acc by X | Subtract from Immediately
`INR X` | Increments Acc by 1 | Increment
`STAX X` | Store contents of Acc into memory address in register X | Store Accumulator To X
`LDAX X` | Load contents of memory address in register X to Acc | Load to Accumulator in X
`PUSH X` | Pushes content in register X to stack | Push to Stack
`POP X` | Retrieves content from top of stack into register X | Pop from Stack
`SPHL` | Forces stack pointer to point to memory address stored in register HL | Stack Pointer to register HL
`<name>: ` | Loop name / Function name
`JNZ <name>` | Ends loop / function
`CALL <name>` | Runs code inside `<name>`
`RET` | Ends functions (required, similar to `break;`)

### 8085 Status Registers/Flags

`S - Z - AC - P - C`

Flag | Name | Function
-----|-----|-----
SF/S | Sign bit | works with C flag to show that result of operation is `0`
Z | Zero | switched on if result of operation at Accumulator is `0`
AC/AF | Auxilary carry | appears if a carry bit is used at 4th bit (exceeds 4 bits)
P | Parity | appears if operation causes EVEN numbers of 1s in binary (Eg:  `1010`, `1100`, `1110 1000`)
C | carry | appears if a carry is performed at 8th bit OR result is a 2's complement (only if `S = 1` as well)

Notes: `SF = 1` , `C = 1` = negative operation result

[Back to contents](#contents)

---------

<div id="csc1202-exam"></div>

## CSC 1201 Exam Coverage

Part A - Two Questions

* Question 1 - MCQ (10m)

* Question 2 - Discussion type (20m)

Part B - Choose TWO out of THREE questions (2x10m)

* Chapters 3 - 7, 9 - 16, 20, 21
* Number systems & computer arithmetic:
  * basic hex to binary,
  * decimal to binary,
  * twos complement,
  * ASCII table will be provided
* Simple Assembly Language code: analyse no more than TEN lines of code to determine contents of register/status flag/memory location
* Internal Memory: cache memory vs regular internal memory
* Big-endian vs little-endian byte ordering schemes, shift vs rotate operations
* Program Status Word (what is this)
* Addressing modes - immediate vs indirect register vs register
* Reduce Boolean function using Karnaugh map (POS, SOP), simple circuit design from reduced Boolean function, combinational vs sequential circuits
* Instruction pipelining (What is it? Why use it? How does it work?), indirect addressing requires additional memory access
* What is RISC? RISC vs CISC, register optimization methods (software vs hardware)
* Concept of parallelism/parallel processing
* Micro-program, micro-program control unit, micro-operations

[Back to contents](#contents)

---------
<div id="prg1203-exam"></div>

## PRG1203 Exam Coverage

Section A - Compulsory (50 marks)

* Q1 - All Topics

Section B - 2 out of 3 (2 x 25 = 50 marks)

* Q2 - Classes, OOP Features
* Q3 - UML, OOP Features
* Q4 - Inheritance, Interface - Theory

[Back to contents](#contents)

---------
<div id="seg1201-lectures"></div>

## SEG1201 Lecture Notes

### The Relational Model

Term | Explanation
-----|-----
Relation | **table** with columns and rows
Database | **collection** of inter-related relations with distinct relation names.
Attribute, Field, Properties | **named column** of a relation.
Tuple, Record | **row** of a relation
Domain | set of **allowed values** for one or more attributes
Degree | the **number of attributes** a relation contains
Cardinality | the **number of tuples** a relation contains
Primary Key | An **attribute that uniquely identifies** any given entity (row). A primary key can be a combination of attributes
Foreign Key | A primary key of one table that **appears again in another table**

## Entity Relationship Diagram

[Back to contents](#contents)

---------
<div id="web1201-exam"></div>

## WEB1201 Exam Coverage

### Exam format

* 5 questions (20 marks each)
* Each question contains 3-4 sections
* 50% practical code (written)
* 50% theory

### Lesson 1 - The internet & web

* The importance of web design
* web design principles
* web client and web server
* domain name
* website organization, pros and cons
* Graphic usage best practices
* web page design page layout

### Lesson 2 - HTML Basics

* HTML, HTML5
* Listing, Hyperlinks

### Lesson 3 - Configure color and text

* CSS advantages and application
* USE CSS to configure color

### Lesson 4 - Visual Elements and Graphic

* Use CSS to Configure border and graphic elements
* Types of graphic: comparison pros and cons
* (Revise the coding learned in practical class)

### Lesson 5 - Page Layout

* Configure Margin and float with CSS
* (Revise the coding learned in practical class)

### Lesson 6 - Tables

* Practical questions
* Give table interface, use full HTML and CSS coding to design out * the same table
* (Revise the coding learned in practical class)

### Lesson 7 - Forms

* Practical Questions
* given a complete form interface, e.g. radio, drop down. comments, submit, etc
* Use full HTML and CSS coding to design out the same form

### Lesson 8 - Web Multimedia and Interactivity

* Audio Formats
* Video formats
* Embed audio and video onto web pages

### Lesson 9 - Programming with JavaScript

* Based on the javascript output, type out and full coding
* (Revise the coding learned in practical class)

### Lesson 10 - Web Publishing and Maintenance

* Steps in publishing a website (explain with full elaboration)

[Back to contents](#contents)
