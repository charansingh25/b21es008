# XV Quiz (CSL 3030)

Welcome to the XV Quiz for CSL 3030 - Operating Systems!



## Instructions
- Answer the multiple-choice questions by selecting the correct option.
- For theoretical questions, provide concise and accurate explanations.
- Feel free to use this quiz for self-assessment or educational purposes.

## Multiple-Choice Questions

#### Question 1: Basics
1. What is XV6?
   - a. A programming language
   - b. A Unix-like operating system
   - c. A file system
   - d. An assembly language

#### Question 2: Architecture
2. XV6 is based on which earlier operating system?
   - a. Windows
   - b. Linux
   - c. BSD
   - d. DOS

#### Question 3: File System
3. Which file system is used in XV6?
   - a. FAT32
   - b. NTFS
   - c. ext4
   - d. simple

#### Question 4: System Calls
4. How are system calls implemented in XV6?
   - a. As functions in the C standard library
   - b. As interrupts
   - c. Through the command line
   - d. As external programs

#### Question 5: Processes
5. In XV6, what is the maximum number of processes that can run simultaneously?
   - a. 128
   - b. 256
   - c. 512
   - d. 1024

#### Question 6: Shell
6. What is the name of the shell used in XV6?
   - a. Bash
   - b. Zsh
   - c. Sh
   - d. Fish

#### Question 7: Scheduling
7. How does XV6 handle process scheduling?
   - a. Round-robin scheduling
   - b. Priority-based scheduling
   - c. First-Come-First-Serve (FCFS)
   - d. Random scheduling

#### Question 8: Memory Management
8. Which memory management technique is used in XV6?
   - a. Paging
   - b. Segmentation
   - c. Virtual Memory
   - d. None of the above

#### Question 9: Interrupts
9. How are interrupts handled in XV6?
   - a. Through polling
   - b. Using hardware interrupts
   - c. Using software interrupts
   - d. Both b and c

#### Question 10: Multithreading
10. Does XV6 support multithreading?
    - a. Yes
    - b. No

#### Bonus Question:
11. Who developed XV6?
    - a. Microsoft
    - b. Google
    - c. MIT
    - d. IBM

## Theoretical Questions

#### Question 12: Process States
12. Briefly explain the different states a process can be in within the XV6 operating system.

Ans - 
In the XV6 operating system, a process can be in one of the following states:
Running: process is currently executing on the CPU.
Runnable: process is ready to run but waiting for CPU to be assigned.
Sleeping: process is waiting for some event to occur, such as I/O completion.

#### Question 13: File System Structure
13. Describe the structure of the file system in XV6. Include the key components and their roles.
Ans -
The xv6 file system implementation is organized in 6 layers.
Lowest layer - Buffer Cache (synchronise access to disc blocks in order to guarantee that only one copy of a block is stored in memory and that only one kernel thread use that copy at any given moment.)
Second layer - Logging (It is necessary to write actions to the log before making any changes to the file system. This guarantees that the modifications are recorded before they are implemented into the real structures of the file system.)
Third layer - Indoes Block allocator (xv6’s block allocator maintains a free bitmap on disk, with one bit perblock)
Fourth layer - directory layer, directory indoes (A directory is implemented internally much like a file)
Fifth layer - Recursive lookup (provides hierarchical path names like /usr/rtm/xv6/fs.c, using recursive lookup)
Final layer - File descriptors (abstracts many Unix resources using the file systeminterface, simplifying the lives of application programmers)

#### Question 14: System Calls vs. Library Functions
14. Explain the difference between system calls and library functions in the context of XV6. Provide examples of each.
Ans -
System Call - request made by the program to enter into kernel mode to access a process.
            - the mode is executed from user mode to Kernel mode.

Library Call - request made by the program to access a library function defined in a programming library 
             -  the mode is executed in user mode only

#### Question 15: Memory Paging
15. How does memory paging work in XV6? Discuss the benefits of using paging in memory management.
Ans -
xv6 uses paging to manage its memory allocations. As a result of the fact that xv6 does not support demand paging, the concept of virtual memory does not exist. The page size in xv6 is 4 KB, and the page table structure is constructed with two levels. CR3 is a register on the central processing unit that stores a pointer to the page table of the process that is now active.


#### Question 16: Shell Commands
16. Name and briefly explain three essential shell commands in the XV6 operating system.
Ans -
1) ls (List):  Lists the files and directories in the current directory
2) cp (Copy): Copies files or directories
3) echo : Displays a message or variable value

#### Question 17: Process Synchronization
17. Discuss the concept of process synchronization in XV6. Why is it essential, and what mechanisms are used to achieve it?
Ans - In XV6, process synchronisation is necessary to keep data from getting corrupted and to make sure that multiple processes run in a logical order. It coordinates access to shared resources, protects data security, and stops race conditions with tools like locks, semaphores, and condition variables. These synchronisation tools make it easier for processes to share resources and keep track of important parts.

#### Question 18: Interrupt Handling
18. Explain the role of interrupts in the XV6 operating system. How are interrupts handled, and what is their significance in system operation?
Ans -  Interrupts are events that temporarily pause the CPU's normal flow to handle specific routines. For handling,  XV6 uses Interrupt Service Routines (ISRs) and an Interrupt Descriptor Table (IDT) to manage interrupts. It efficiently handles asynchronous events like I/O completion also enables multitasking through timer interrupts.

#### Question 19: Virtual Memory
19. What is virtual memory, and how is it implemented in XV6? Discuss the advantages of using virtual memory.
Ans -  Virtual memory is an abstraction that extends available physical memory by using disk space. It implements using Page-based system with a 4KB page size, and two-level page tables for address translation also it handles page faults by swapping pages between memory and disk.
Advantages:
Increased address space for processes.
Isolation and protection.

#### Question 20: Boot Process
20. Outline the steps involved in the boot process of XV6. What happens from the moment the computer is powered on to when the XV6 kernel is loaded into memory?
Ans - The XV6 boot process starts with turning on the computer and setting up the hardware. Next, the driver (like GRUB) loads the XV6 kernel into memory. The bootloader gives the kernel power. The kernel sets up important data structures and puts the processor into protected mode. It runs the kernel's main function, which sets up the system even more and starts user-level processes like the init process. Lastly, power is given to user-space programmes, which let the fully initialised XV6 operating system talk to them. At this point, the bootloader, kernel, and initialization processes all work together to turn the system on from being turned off and make it ready to run user programmes.

## Answers
Please write your answers here

Question 1) b. A Unix-like operating system
