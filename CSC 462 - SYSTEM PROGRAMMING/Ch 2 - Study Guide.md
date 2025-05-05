# Chapter 2 Study Guide

# FILL IN
Chapter 2: Operating-System Structures - Study Guide

Chapter 2: Fill-in-the-Blank Study Questions

1. __________ Management handles creation, scheduling, and termination of processes.

2. The __________ program is loaded at power-up and initializes the system.

3. __________ are the interface between a process and the operating system.

4. The __________ approach divides the OS into hierarchical layers.

5. __________ VMs support a full operating system and provide complete isolation.

6. __________ is responsible for organizing, storing, retrieving, naming, and protecting files.

7. A(n) __________ kernel keeps most services in user space, minimizing core kernel functionality.

8. __________ and __________ are examples of user services provided by an operating system.

9. The OS structure that combines features from different models is called a __________ system.

10. System calls for __________ control include create, terminate, and wait operations.

11. The __________ system interprets user commands in CLI or GUI format.

12. __________ and __________ are categories of operating system services.Chapter 2: Operating-System Structures - Study Guide

13. The command __________ system allows interaction with the OS using commands.

14. System VMs provide benefits such as __________ and __________.

15. __________ programs assist with program development and execution.

# ANSWER



Chapter 2: Operating-System Structures - Study Guide

1. System Components

- Process Management: OS handles creation, scheduling, and termination of processes.

- Main-Memory Management: Tracks what memory is used, by whom, and how to allocate/deallocate.

- File Management: Organizes, stores, retrieves, names, and protects files.

- I/O System Management: Buffers, caches, and device drivers to manage I/O operations.

- Secondary-Storage Management: Manages free space, storage allocation, and disk scheduling.

- Networking: Manages data exchange over networks.

- Protection and Security: Controls access to system resources and defends against threats.

- Command-Interpreter System: Interface that interprets user commands (e.g., shell, GUI).

2. Operating System Services

User Services:

- User interface (CLI or GUI)

- Program execution

- I/O operationsChapter 2: Operating-System Structures - Study Guide

- File system manipulation

- Communications

- Error detection

System Services:

- Resource allocation

- Accounting

- Protection and security

3. System Calls

- Interface between process and OS (via APIs).

- Typically accessed via high-level APIs (e.g., POSIX, Win32).Chapter 2: Operating-System Structures - Study Guide

- Categories:

- Process control (create, terminate, wait)

- File manipulation (read, write, open, close)

- Device manipulation

- Information maintenance

- CommunicationsChapter 2: Operating-System Structures - Study GuideChapter 2: Operating-System Structures - Study Guide

4. System Programs

Provide a convenient environment for program development and execution:

- File management

- Status info and debugging

- Programming-language support

- Program loading and execution

- Communications

5. OS Structure

- Simple Structures: e.g., MS-DOS

- Layered Approach: OS divided into layers (e.g., THE operating system)

- Microkernels: Minimal kernel running most OS services in user space

- Modules: Modern OS are modular (e.g., Linux)

- Hybrid Systems: Combine features from multiple structures (e.g., Windows, MacOS)Chapter 2: Operating-System Structures - Study Guide

6. Virtual Machines (VMs)

- Abstract layer that simulates hardware.

- Types:

- Process VMs: Support a single process (e.g., JVM)

- System VMs: Support a full OS (e.g., VMware, VirtualBox)

- Benefits: Isolation, testing, security

7. OS Generation and System Boot

System Boot:

- Bootstrap program loaded at power-up

- Initializes system and loads the kernelChapter 2: Operating-System Structures - Study Guide

OS Generation (SYSGEN):

- Configures OS for specific hardware

Review Tips

- Be familiar with system call categories and examples.

- Understand the differences in OS structures and when they're used.

- Know the purpose of system programs and boot processes.

- Compare and contrast microkernels vs. monolithic kernels.

- Know how virtual machines operate and their advantages.
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDk4OTg3MDg2LDE1MTQ0MTQ5MTNdfQ==
-->