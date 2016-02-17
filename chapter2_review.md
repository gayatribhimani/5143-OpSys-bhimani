# Chapter 2 Review Questions
Name: Gayatri bhimani
Course: 5143 Operating Systems
Date: 17 feb 2016

## 1.What are three objectives of an OS design?

The three objectives of the design are
Convenience: An operating system makes a computer more convenient to use. 
Efficiency: An operating system allows the computer system resources to be used in an efficient manner.
Ability to evolve: An operating system should be constructed in such a way as to permit the effective development, 
testing, and introduction of new system functions without interfering with service.

## 2.What is the kernel of an OS?

The kernel is a portion of the operating system that includes the most heavily used portions of software. 
Generally, the kernel is maintained permanently in main memory. 
The kernel runs in a privileged mode and responds to calls from processes and interrupts from devices. 

## 3.What is multiprogramming?

Multiprogramming is a mode of operation that provides for the interleaved execution of two or more computer programs 
by a single processor. 

## 4.What is a process?

A process is a program in execution. A process is controlled and scheduled by the operating system. 

## 5.How is the execution context of a process used by the OS?

The execution context, or process state, is the internal data by which the operating system is able to supervise and 
control the process. This internal information is separated from the process, because the operating system has information
not permitted to the process. The context includes all of the information that the operating system needs to manage the
process and that the processor needs to execute the process properly. The context includes the contents of the various 
processor registers, such as the program counter and data registers. It also includes information of use to the operating 
system, such as the priority of the process and whether the process is waiting for the completion of a particular I/O 
event. 

## 6.List and briefly explain five storage management responsibilities of a typical OS.

Process isolation: The operating system must prevent independent processes from interfering with each other's memory, 
both data and instructions.
Automatic allocation and management: Programs should be dynamically allocated across the 
memory hierarchy as required. Allocation should be transparent to the programmer. Thus, the programmer is relieved of 
concerns relating to memory limitations, and the operating system can achieve efficiency by assigning memory to jobs only 
as needed. 
Support of modular programming: Programmers should be able to define program modules, and to create, destroy, 
and alter the size of modules dynamically. 
Protection and access control: Sharing of memory, at any level of the memory 
hierarchy, creates the potential for one program to address the memory space of another. This is desirable when sharing 
is needed by particular applications. At other times, it threatens the integrity of programs and even of the
Background image
Long-term storage: Is a process whereby memory is stored for a long period of time.even when the computer is switch off it is stored in the RAM.

## 7. Explain the distinction between a real address and a virtual address.

Real Address/ Physical Address refer to hardware addresses of physical memory.
Physical addressing means that your program actually knows the real layout of RAM. 
When you access a variable at address 0x8746b3, that's where it's really stored in the 
physical RAM chips.
With virtual addressing, all application memory accesses go to a page table, which then 
maps from the virtual to the physical address. So every application has its own "private"address space, and no program can 
read or write to another program's memory. This is called segmentation.

## 8.Describe the round-robin scheduling technique.

Round Robin scheduling technique is one of the oldest and widely used algorithm, in this technique processes are dispatched in 
a FIFO manner but are given a limited amount of CPU time called a time-slice or a quantum.
If a process does not complete before its CPU-time expires, the CPU is preempted and given to the next process waiting in a queue. 
The preempted process is then placed at the back of the ready list.
Round Robin Scheduling is preemptive (at the end of time-slice) therefore it is effective in time-sharing environments in which the 
system needs to guarantee reasonable response times for interactive users.
The only interesting issue with round robin scheme is the length of the quantum. Setting the quantum too short causes too many 
context switches and lower the CPU efficiency. On the other hand, setting the quantum too long may cause poor response time and 
appoximates FCFS.

## 9.Explain the difference between a monolithic kernel and a microkernel.

Monolithic Kernel:
Monolithic kernel is a single large process running entirely in a single address space.
It is a single static binary file. All kernel services execute in the same kernel address space. 
Examples of monolithic kernel based Oss are Unix, Linux.
Microkernel:
In microkernel, the kernel is broken down into separate processes, known as servers. 
Some of the servers run in kernel space and some run in user-space. All servers are kept separate and run in different address spaces. 
Servers invoke "services" from each other by sending messages via IPC (Interprocess Communication). This separation has the advantage
that if one server fails, other servers can still work efficiently. 
Examples of microkernel based OSs: Mac OS X and Windows NT.

## 10.What is multithreading?

Multithreading is the ability of a program or an operating system process to manage its use by more than one user at a time and to 
even manage multiple requests by the same user without having to have multiple copies of the programming running in the computer.

## 11.List the key design issues for an SMP operating system.

Simultaneous concurrent processes or threads: Kernel routines need to be reentrant to allow several processors to execute the same 
kernel code simultaneously.
Scheduling: Scheduling may be performed by any processor, so conflicts must be avoided
Synchronization: With multiple active processes having potential access to shared address spaces or shared I/O resources, care must be 
taken to provide effective synchronization
Memory Management: Memory management on a multiprocessor must deal with all of the issues found on uniprocessor machines. There is a 
problem with the cache memories: Cache memories contain image of a portion of main memory. If a processor changes the contents of the 
main memory, these changes have to be recorded in the cache memories that contain an image of that portion of memory. This is known as 
cache coherence problem and is typically solved in hardware.
Reliability and fault tolerance: The operating system should provide graceful degradation in the face of processor failure




