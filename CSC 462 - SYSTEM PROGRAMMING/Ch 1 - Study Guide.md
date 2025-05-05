# Chapter 1 Study Guide

# FILL IN

## **Process Concept – Fill in the Blank**

### **Definition and Components of a Process**

A process is defined as a _______ in execution, which must progress _______. Parallel execution within a single process is not _______.

Key components of a process include:

-   _______ code (text section)
    
-   current activity (_______, processor registers)
    
-   _______ (temporary data)
    
-   data section (_______ variables)
    
-   _______ (dynamically allocated memory)
    

The _______ is a passive entity stored on disk, while the _______ is an active entity.

A single program can have _______ processes running simultaneously.

----------

### **Process States**

A process can exist in the following states: _______, _______, _______, _______, and _______.

The transition between these states is essential for process _______ and _______.

----------

### **Process Control Block (PCB)**

The PCB contains:

-   process state
    
-   program counter
    
-   CPU _______
    
-   _______ information
    
-   memory _______ details
    
-   accounting info
    
-   I/O _______
    

Each process has a unique _______ used by the OS to manage it.

----------

### **Process Representation in Linux**

In Linux, processes are represented using the _______ C structure. Key fields include:

-   process identifier (___)
    
-   _______ information
    
-   parent process pointer
    
-   memory management details
    

----------

### **Process Scheduling**

The process _______ chooses which process to execute to maximize _______ and minimize _______ time.

Types of scheduling queues:

-   _______ queue (ready to execute)
    
-   _______ queue (waiting for an event)
    

----------

### **Context Switching**

A context switch occurs when the CPU switches from one process to another, saving and loading their _______.

Context-switch time is considered _______.

The _______ and complexity of the PCB affect switch time.

----------

### **Multitasking in Mobile Systems**

-   iOS typically allows only one _______ process.
    
-   Android allows more background execution via _______.
    
-   Understanding the differences is important for _______ development.
    

----------

### **Operations on Processes**

#### **Process Creation**

Processes are created by _______ processes and form a _______ structure.

Each has a unique ___.

The `_______()` system call creates a new process; `_______()` replaces the memory with a new program.

----------

#### **Process Termination**

A process ends via the `_______()` system call, and the parent can retrieve status using `_______()`.

A parent can also terminate a child using `_______()`.

If a child ends and the parent hasn’t waited, it becomes a _______ process.

If a parent ends first, the child becomes an _______ process.

----------

### **Android Process Importance Hierarchy**

Processes are prioritized as follows (most to least important):

1.  _______ processes
    
2.  _______ processes
    
3.  _______ processes
    
4.  _______ processes
    
5.  _______ processes
    

Android reclaims memory starting from the _______ important.

----------

### **Multiprocess Architecture**

#### **Chrome Architecture**

Chrome uses a multiprocess architecture with:

-   Browser process: handles UI and _______
    
-   Renderer process: renders pages in a _______
    
-   Plug-in process: handles browser _______
    

Each tab runs in its own _______ process for isolation.

----------

### **Interprocess Communication (IPC)**

#### **Overview**

IPC allows processes to _______ and affect each other’s _______.

Two models: _______ _______ and _______ _______.

----------

#### **Shared Memory Model**

Processes share a common _______ area.

Main challenge: _______ due to concurrent access.

Classic example: _______ - _______ problem.

----------

#### **Producer-Consumer Problem**

Requires a shared _______.

Producer waits if buffer is _______; consumer waits if buffer is _______.

Enhancement: use a _______ to track filled slots.

----------

#### **Race Conditions**

Race conditions occur when multiple processes access _______ data concurrently.

This can result in _______ behavior.

----------

#### **Message Passing Model**

Processes use `_______()` and `_______()` to communicate.

No shared _______ is needed.

Key considerations:

-   Communication link setup
    
-   Message size (_______ or _______)
    
-   Direction (uni- or _______)
    

----------

### **Communication Links**

#### **Physical Links**

Examples:

-   _______ memory
    
-   Hardware _______
    
-   _______ (networked systems)
    

#### **Logical Links**

Includes:

-   Direct/_______ communication
    
-   Synchronous/_______
    
-   Automatic/_______ buffering
    

----------

#### **Direct Communication**

Processes must name each other explicitly.

Symmetric example:

-   `send(P, message)`
    
-   `receive(Q, message)`
    

Each link is between exactly ___ processes.

----------

#### **Indirect Communication**

Processes use _______ (or ports) to exchange messages.

Mailboxes can be shared by _______ processes.

Operations include _______, send, receive, and _______.

----------

### **Synchronization and Buffering**

#### **Synchronization Types**

-   Blocking (_______): sender waits until message received.
    
-   Non-blocking (_______): sender continues after sending.
    
-   _______: Both sender and receiver block.
    

----------

#### **Producer-Consumer (Message Passing)**

-   Producer: generates and sends messages.
    
-   Consumer: receives and processes them.
    

Example operations: `send(next_produced)` and `receive(next_consumed)`

----------

#### **Buffering Strategies**

1.  Zero Capacity: No queue, sender must _______.
    
2.  Bounded Capacity: Limited queue, sender waits if _______.
    
3.  Unbounded Capacity: Infinite queue, sender _______ waits.
    

----------

### **Examples of IPC Systems**

#### **POSIX IPC**

Create shared memory:
```c
shm_fd = shm_open(name, O_CREAT | O_RDWR, 0666);
ftruncate(shm_fd, 4096);
```

Access memory using `_______()`.

----------

#### **Mach IPC**

Uses _______-based messaging.

Messages sent/received using `_______()`.

Ports created via `_______()`.

----------

#### **Windows IPC**

Uses _______ for local message-passing.

Client opens a handle and sends a _______; server creates _______ ports.

----------

### **Advanced Communication Techniques**

#### **Sockets**

A socket is defined by a _______ and _______ number.

Can be:

-   Connection-oriented (___)
    
-   Connectionless (___)
    

----------

#### **Remote Procedure Calls (RPC)**

Allows processes to invoke functions across _______.

Key components:

-   _______: client-side proxy
    
-   Data representation via _______ (XDL)

# ANSWER

# Chapter 1: Introduction to Operating Systems

### What is an Operating System?

> An operating system (OS) is a program that acts as an intermediary between users and computer hardware.

-   The OS manages hardware resources and provides a user-friendly interface for interaction.
-   It is responsible for executing user programs and solving user problems efficiently.
-   OS goals include convenience, efficiency, and effective resource management.
-   Examples of OS include Windows, Linux, macOS, and mobile operating systems like Android and iOS.![Diagram showing the layered architecture of a computer system, from the user at the top to the hardware at the bottom, with application programs and the operating system in between.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/dc918b5d-5ecc-4bff-8ddd-347697e09c71/images/618b9f02ad94487bba77412f97e5a7f6.jpg?Expires=1747059500&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=id1hvE0W8%2B8krpMyelPKWHZD26Vbiils%2FOuf1lSyJgMf%2BlXstuHLbhqxnCo4cVVINxRax4z1xpxGBRF44XOfCujV8ysf15W%2F6h6PzBPt0D9SV7ghFxDoI6niXy3pk%2B%2BBwJzyorhNhJCuC%2F6ikdG0x7t2D%2FmqJjI6yHrf8mppW83P3HJynuy%2FchqZWLgJ8yg17iBh2v6XXJ0qnUIEFFn6FPDCvX%2BJjZo%2FyV4yA0tdq537nyF3euVsbOmOtpaxOImysOpC9TadQ7BA1%2FW84vzIvb01czfxtlr1%2FGKrkKD7R0fuO5UAjHCnuumK8poUtYlOAXgycCW7EQy9u2aWYoYRQw%3D%3D)![Diagram showing the layered architecture of an operating system, including user mode, kernel mode, and hardware, with system calls, signals, and interrupts indicated.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/dc918b5d-5ecc-4bff-8ddd-347697e09c71/images/69390b412a254226a88ea0a5885b898b.jpg?Expires=1747059500&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=B7mmWWf6RSlpHYp0uOVpAM8EiaUPQVgAA%2FypuPuLKe6%2BOMw8u45kx%2Fwc7rGad9RonDTjjytPGz%2BwVkH2Q16jPxH%2BaRKBBuhtl9Vm4b55nxtS%2BgAbAefhyba7biitV4XLpTs6a%2BR%2FQDcg5IJzyChNjKmHm7LE3ttY1XG2zWXtKs8uMv%2BsPziJjIt%2Fe2hmBmg%2BHRZocd2We%2BjKeBhEx6r2l24eVaWr3XFZzbVjDCcPR%2F1NtVj0R9icSXB8tAdgYo9j0aMJl%2FMKp%2Bxv3ro1yDdaxB9huKygzJs4o5mloseXgzHMWewI4mABAIF0qTjFm2FO5KKFvzXWsvgxb6V%2FhX3J7g%3D%3D)

### Computer System Structure

-   A computer system consists of four main components: hardware, operating system, application programs, and users.
-   **Hardware**: Includes CPU, memory, and I/O devices that provide basic computing resources.
-   **Operating System**: Coordinates the use of hardware among various applications and users.
-   **Application Programs**: Define how system resources are used to solve user problems (e.g., word processors, games).
-   **Users**: Can be people, machines, or other computers interacting with the system.![Diagram of a computer system showing the CPU, memory, disk controller, USB controller, and connections to peripherals such as mouse, keyboard, printer, and monitor.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/dc918b5d-5ecc-4bff-8ddd-347697e09c71/images/11739676a1a8401fa8c33df97b61ee23.jpg?Expires=1747059500&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=M7OOX6Jamme4n845Z4jWbQDCB2s4plDLQW23GsJSU7mprNjaAuSchcGO9tw2im8XHV3orG%2BD8KOENgveUk%2Bu1USSQ5hpRJIZ%2BymD%2BNkTv5pWzBBOKPvZbdtYT24568DCPfSxy7%2FRgPNHVvGBmZSAn%2F3p9xAYmrunpZnjKG7G8JIKRu2QKvoVHOkd1IMuxTl4zZNXGNYQDPc%2FYk5ccDXLYNWtUTBTMFH2iKiF0HAHZB1%2BFSbhcZGL9i6jZf8qnEBy%2BVzrNwVTwnVVTRKFIqxw5IlI1NTjuUMV6I6a3MblyMNURYe5FaPOLUf6%2FYnWx0JU7URyiy9ITAuR43gM7MxkHg%3D%3D)

### Operating System Functions

-   The OS serves as a resource allocator, managing hardware resources and ensuring fair usage among users.
-   It acts as a control program, overseeing the execution of programs to prevent errors and misuse.
-   OSes are designed to handle various computing environments, from dedicated systems to mobile devices.
-   They optimize performance based on user needs, such as usability and battery life in mobile devices.
-   The OS must balance user convenience with efficient resource utilization, especially in shared environments.

### Interrupts and I/O Management

-   Interrupts are signals that inform the CPU of events requiring immediate attention, allowing concurrent execution of I/O devices and the CPU.
-   Each device controller manages a specific device type and has a local buffer for data transfer.
-   The OS uses interrupts to handle I/O operations efficiently, preserving CPU state and determining the type of interrupt.
-   There are two main methods for handling I/O: blocking (waiting for completion) and non-blocking (returning control immediately).
-   The device-status table is crucial for tracking the status of I/O devices and managing requests.![This timeline diagram illustrates the CPU's execution of a user process, interspersed with I/O interrupt processing, while an I/O device cycles between idle and data transferring states.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/dc918b5d-5ecc-4bff-8ddd-347697e09c71/images/fd84ddbee16a4b91b60b8755b5539366.jpg?Expires=1747059500&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=aVQwzkloW21vaPXOkBlIUdiuJOaSaTPKeLgIRoHEaY7f4cl2s%2BAJq3ZwClvGt6m0FH00LCTTaIPauzwkJMm3PnEyLOuZeKuHeXuoXVH2FxAtOyfsahWkG%2FGWIp8BdAe3ix9RsqJeAHKpGlN5LWdOqz4DKm7wb%2FXMKG%2Fu4%2Blcmt94NggRpyAVUv63Y5hbe3dDzkUVh02riYJyEbQeZQ7pKtwzUJ28qaG5ZO9XgzggOVXjxS2POkcrVqwZvzMgKkS3%2F5RIkWSLWPUSvrKVEyQcmvqrvFK04CFCU7Hx%2FAN%2BgmIqvaso8x56Lx0l6zZp8C8Vowlp1jV5ZuAqh%2ByshJ8MVw%3D%3D)![This timing diagram illustrates the CPU and I/O device interactions during I/O interrupt processing, showing the transitions between idle, I/O request, transfer, interrupt signal, and interrupt handling.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/dc918b5d-5ecc-4bff-8ddd-347697e09c71/images/ed2c025b6302405fac3586d96070681b.jpg?Expires=1747059500&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=m25P9aHkwFgRUP00yxarxw%2FazZZqQ0V9abI%2FAJO8oVndlfPLsAUuLXbDcz%2BFVq9hqNr01lLGURQ4%2B0pMq2%2B651wHVcciIGfYHLrPkFMG%2B1cU4zHydCGhMIu4URH901HBPnVKVWgLY0XhlI6UujqlnH9E5x6mgQ%2B6gjpDvpQbQ98B4rCGsqGlSW%2BRKfym96rbMtM5ki5%2Fj%2B0iWos1y3hhxsUzoNPBQTTl%2FoA3oimgA%2BfwBQdU1HaUU1CK5YFBGEBoedrteARnsQMluyI7KxAnDQyrEThjgpWHdmrj4cbu6x12Mz9GFzX0FNTuYkG9iCo%2FWQHyacwfC9%2BL4cByDf2j5Q%3D%3D)

# Computer System Operation

### Computer System Organization

-   A computer system operates with one or more CPUs and device controllers connected via a common bus to shared memory.
-   The concurrent execution of CPUs and devices is essential for efficient operation and resource management.
-   Device controllers are responsible for managing specific devices and communicating with the CPU through interrupts.![Diagram showing the interaction between a CPU, memory, I/O devices, and DMA, illustrating data movement, instruction execution, and interrupt handling.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/dc918b5d-5ecc-4bff-8ddd-347697e09c71/images/e9be89f1aca84ee09c38275b39d9aee3.jpg?Expires=1747059500&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=Pi%2FLHeHsun6G4ILAsOeESkLr0rnVBC9Moaym7%2BfxvgvjCdFKedRfZRT3ArcyFxZHCngDeelay52o7C6ZBel2cqMp%2BXCUJXl9opFzl543720Dg3FEOEl8tfaCyhfr9F8eRSU4bEmXvcZY3r6sBcn3wvV4qGvj5PRXdEbLbQU%2Fdqdpr7LpML9vdt4QT3JyZrKV%2FygTlVfCMqVB4NpMKnSGtIOTtk8XjWUDFM9kaTn%2Bd1glHiKgjUCzfAZeTidZze7b7KczKlpCuXRh4bKLDlOwKA0yVrsj4ETxWxDPGo%2BvaPvYPRzjO5cK7WoFAluYUrJprD1lkMQk4ovUD5KxwwlAaA%3D%3D)

### Interrupt Handling

-   The OS preserves the CPU state during an interrupt by saving registers and the program counter.
-   Different types of interrupts require specific handling routines to determine the appropriate action.
-   The interrupt vector contains addresses of service routines for various interrupts, ensuring quick response to events.

### I/O Structure and Control

-   I/O operations can be handled in two ways: waiting for completion or returning control immediately to the user program.
-   The wait instruction can idle the CPU until the next interrupt, while a system call allows the user to wait for I/O completion.
-   The OS indexes into the device-status table to manage device states and handle interrupts effectively.

# Storage Structure

### Types of Storage

-   **Main Memory**: The only storage directly accessible by the CPU, typically volatile and random-access (e.g., DRAM).
-   **Secondary Storage**: Provides large non-volatile storage capacity, such as Hard Disk Drives (HDD) and Non-Volatile Memory (NVM).
-   HDDs consist of rigid platters and are divided into tracks and sectors for data organization.![This text explains the basic units of computer storage, starting with the bit and progressing to bytes, kilobytes, megabytes, gigabytes, terabytes, and petabytes, noting that networking measurements are an exception and use bits.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/dc918b5d-5ecc-4bff-8ddd-347697e09c71/images/e1c030e89ef343369ae774312d0cfcaa.jpg?Expires=1747059501&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=Ao25yQMqSL%2FnSxExpeQ3l6GS8uNV9Mn1Kb18t24GoF46jMCh9Q0Yys1s%2BzSqGihTMe%2FYOnnOuQJ4rHi5cWlZP%2B5PmFzE98wWJoqnVluUnZDSDcHdWeeC%2FNKKWN9auXXzGg1%2BwFOCrE35gCwtsa2FX0fHOZHAcigBeKexSJFlflgnd064OVWMLKWfri5QfvH%2Bw16apmu7tDj6G%2FYc8iJpkSMP8a%2BJBzIKX0UH5%2FI25dx5PvY8%2BEPJ9p8sqxPDlBmVeeX2fvJnbvjgshrJG1aOxz%2Br%2Fc4%2FCafoL3nOc2kIyvPtQWHM2SOzbhwhLa9TRqFZmJs3S9ZweCgKc7VW65AuYg%3D%3D)

### Storage Definitions and Measurements

-   The basic unit of storage is the bit, with a byte (8 bits) being the smallest convenient chunk of storage.
-   Storage capacity is often measured in bytes, with common units including KB (1,024 bytes), MB (1,024² bytes), GB (1,024³ bytes), and TB (1,024⁴ bytes).
-   Networking measurements differ, typically expressed in bits due to data transmission characteristics.

# Storage Hierarchy

### Overview of Storage Systems

-   Storage systems are organized in a hierarchy based on several factors including speed, cost, and volatility.
-   The hierarchy typically includes registers, cache, main memory (RAM), and secondary storage (like SSDs and HDDs).
-   Each level of the hierarchy has trade-offs; for example, faster storage is usually more expensive and volatile.![A diagram illustrates the memory hierarchy in a computer system, showing the trade-off between storage capacity and access time for different storage types, from registers to magnetic tapes.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/dc918b5d-5ecc-4bff-8ddd-347697e09c71/images/469c11f3649147f995621c9815ab47ff.jpg?Expires=1747059501&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=R6g3azJE2LpC3NPTe5y%2BKZ7PLFJmIqEuTIGMEHXjlPAtHIo15hfcnWj8JDFhTxjTXKqf%2BsF2vMIjQXXhPbnfmivvJNUe6uFDP2ihavkAQoTtj9wyIel%2BTd52rlicsfAm0Q2%2FxldaFbH4%2BTvN3g4y6%2BBOc1AEiu5eEFiYPyAS9bG0hfRhzffgON%2Fyv6U%2B4kZIsuLIVVzR9bqsh4r2p0uBT%2FS9eogtLN%2FceTZWXp1T59Bvrfj0I51d3FaKs1f7G6QSumPRMF3olAWoM9r4uXOPKRPo5LzMOxM6bM5XnrdfirdZ5GHeedn2bntFtcysfwd5kLweEsFK3txrRjAvxC8N4A%3D%3D)![A table comparing five levels of computer memory, including their names, typical sizes, implementation technologies, access times, bandwidths, management, and backing storage.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/dc918b5d-5ecc-4bff-8ddd-347697e09c71/images/f35b1c7327654788b2fb203edfc52f2d.jpg?Expires=1747059501&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=OGTinFKtTnaDoE48byXuqT0IJolQJKOq7eAeuu7v6cpqsUi%2F3U%2FPX%2FcLTp2QPXZpHsiIFQRz94a%2B6XqgtpgiSsHd9MYYoLox4uQPBglgWN7%2BhjfxMq8WiXtnUQ%2BqHqr50H5KhaUKogK9%2Bt4nZXHVyxI4C%2Ffi3JsaqY5ysYroQLQL6UqBIhzSCs7QLit4N%2B3bFwGLsgFBdsIfPTdGzjGIycSr8Gd3jZOolJDays8MkMUR8EWdsVkspxaOniWJ1jEAu9Phx1TvzidhIRwX5KlhJ9EbNWZfRozEzNcTCeXRwsIfWDFYHpmkrVxBW3E79lAMSO9VXM3MCUkH%2FdZsgy59Ww%3D%3D)

### Caching Mechanism

-   Caching involves copying frequently accessed information into a faster storage system to improve access times.
-   Main memory can be viewed as a cache for secondary storage, allowing quicker access to data that is often used.
-   Effective caching strategies can significantly enhance system performance by reducing latency.![Diagram showing memory allocation with the operating system at the top, followed by four processes stacked below.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/dc918b5d-5ecc-4bff-8ddd-347697e09c71/images/f5c634854ed541d7aa1bd888582a32c1.jpg?Expires=1747059501&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=d8tF1oYhH42K4YxxSwpABYrVXR3YBGaRzCZiTkY%2BemravJRAZB6mD%2F2O5m4cb29l1EOYz566hxB8xyYXFHqUQRoDrcL1JHi0i6y0r18Br%2FMcJQcr1mKvRxawxGha22%2FEvvGbLd5paJrJuvpaKKVfKYaTm%2BLWE6cc%2B6%2BJYr5R0jP17txwfGzUhiz8QSlWgyPXmONfB%2BafKv44otKcMIAKxW51YiwfTFOLV9xwsyik%2BqJGCe8WPhmNmz34GpV2KJGuJp4nCabA%2F0gPwlrGWMqyzrj%2FJJGP8M3Ff4xDWlK6vENMUU2%2BI5dSSGmZDHuPOhjIYiTyWSRu13MvsNCPGNwoww%3D%3D)

### Device Drivers and I/O Management

-   Each device controller requires a device driver to manage input/output operations, providing a uniform interface between the controller and the kernel.
-   Device drivers are essential for the operating system to communicate with hardware devices, abstracting the complexities of hardware interactions.![This diagram illustrates the process of a user process calling a system call, transitioning from user mode to kernel mode, executing the system call, and returning to user mode.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/dc918b5d-5ecc-4bff-8ddd-347697e09c71/images/45ee7262fbe6448992780c769b319eb8.jpg?Expires=1747059501&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=wkPw%2BE8YOkLk1uqSuL2r97TXjGPtA8wqMZYZenMvVwNOFAp%2F2gVafkd%2F9F4WEB2QJstNPdJ0LhtDLr64KQ%2BjFAKlqeTLm0Nr0tlyL9%2FD22iZLLkf5faRCm%2BSHTvl%2FDz2UAV9GsXqfoudDywSltMlJtbEocnFXeCJNQvG9En13oPxOP8z1VLF5EMfZIsCm7mrdWfsinQEwKb1ReeTFwx0E%2BoAtKWa4UuzZpspAvMpAEgkejdduAYE2TZKk%2BGuME4Mq2JLVi5KzopOy9HxBlaf9m%2BzwegVxszh7%2Fxr%2F4Wv8l3roc5AJieNOlTYV3cLOPHdwreS7CJxFjLFW9RaZe7Agw%3D%3D)

# How a Modern Computer Works

### Von Neumann Architecture

-   The von Neumann architecture is a foundational model for computer design, consisting of a processing unit, memory, and input/output mechanisms.
-   It operates on the principle of stored-program architecture, where instructions and data are stored in the same memory space.

### Direct Memory Access (DMA)

-   DMA allows high-speed I/O devices to transfer data directly to main memory without CPU intervention, enhancing performance.
-   This method reduces CPU load by minimizing the number of interrupts generated; only one interrupt is generated per block of data transferred.

# Operating System Operations

### Bootstrap and Kernel Initialization

-   The bootstrap program is a simple code that initializes the system and loads the kernel into memory.
-   Once loaded, the kernel provides essential services and starts system daemons, which are background services that operate outside the kernel.

### Interrupt Handling

-   The kernel is interrupt-driven, responding to hardware interrupts from devices and software interrupts (exceptions or traps) such as division by zero errors.
-   System calls are requests made by programs to the operating system for services, allowing user programs to interact with the system.

# Process Management

### Multiprogramming and Multitasking

-   Multiprogramming allows multiple processes to reside in memory, ensuring the CPU is always busy by switching between processes when one is waiting for I/O.
-   Multitasking extends this concept, allowing users to interact with multiple processes simultaneously, with a response time ideally under one second.

### Dual-mode Operation

-   Dual-mode operation distinguishes between user mode and kernel mode, protecting the operating system from user processes.
-   The mode bit, controlled by hardware, indicates whether the system is executing user code or kernel code, ensuring that only privileged instructions can be executed in kernel mode.

### Timer and Resource Management

-   A timer is implemented to prevent processes from hogging resources or entering infinite loops, generating interrupts after a set time period.
-   The operating system sets the timer counter, and when it reaches zero, an interrupt is generated to regain control of the CPU.

### Overview of Processes

-   A process is an instance of a program in execution, requiring resources such as CPU, memory, I/O, and files to accomplish its task.
-   Initialization data is crucial for setting up a process before execution begins.
-   Process termination involves reclaiming reusable resources to maintain system efficiency.
-   Single-threaded processes have one program counter, executing instructions sequentially, while multi-threaded processes have multiple program counters, allowing concurrent execution of threads.

### Process Management Activities

-   The operating system (OS) is responsible for creating and deleting both user and system processes, ensuring efficient resource management.
-   Processes can be suspended and resumed, allowing for better CPU utilization and responsiveness.
-   Mechanisms for process synchronization are provided to prevent race conditions and ensure data consistency.
-   Inter-process communication (IPC) mechanisms are essential for processes to communicate and share data effectively.
-   Deadlock handling mechanisms are implemented to prevent or resolve situations where processes are unable to proceed due to resource contention.

# Memory Management

### Memory Requirements for Execution

-   To execute a program, all or part of its instructions and data must reside in memory, highlighting the importance of memory management.
-   Memory management determines what data is in memory and when, optimizing CPU utilization and user response times.
-   Keeping track of memory usage is essential for efficient resource allocation and deallocation.

### Memory Management Activities

-   The OS tracks which parts of memory are in use and which processes are utilizing them, ensuring efficient memory allocation.
-   Decisions on which processes or data to move in and out of memory are made based on current system demands.
-   Memory allocation and deallocation are performed dynamically to adapt to changing workloads.

# File-System Management

### File System Overview

-   The OS provides a uniform, logical view of information storage, abstracting physical properties into logical storage units called files.
-   Each storage medium is controlled by a device, such as a disk drive or tape drive, with varying properties like access speed and capacity.
-   Files are typically organized into directories, facilitating easier access and management.

### File-System Management Activities

-   The OS is responsible for creating and deleting files and directories, managing the file system structure.
-   Primitives for manipulating files and directories are provided, allowing users to perform operations like read, write, and delete.
-   The OS maps files onto secondary storage and ensures backup onto stable, non-volatile media to prevent data loss.

# Caching and I/O Subsystem

### Caching Mechanisms

-   Caching is a critical principle that improves performance by temporarily storing frequently accessed data in faster storage.
-   The cache is checked first for data; if not found, data is retrieved from slower storage and copied to the cache.
-   Cache management involves determining cache size and replacement policies to optimize performance.

### I/O Subsystem Responsibilities

-   The I/O subsystem hides hardware peculiarities from users, providing a simplified interface for device interaction.
-   It manages memory for I/O operations, including buffering, caching, and spooling to enhance performance.
-   A general device-driver interface is provided, allowing the OS to manage drivers for specific hardware devices.

# Protection, Security, and Virtualization

### Protection and Security Mechanisms

-   Protection mechanisms control access to resources defined by the OS, ensuring that only authorized processes or users can access them.
-   Security involves defending the system against various threats, including denial-of-service attacks, worms, and identity theft.
-   User identities and group identifiers are used to manage access control, associating users with their respective files and processes.

### Virtualization Concepts

-   Virtualization allows multiple operating systems to run on a single physical machine, creating a vast industry for cloud computing and resource management.
-   Emulation is used when the source CPU type differs from the target, while virtualization typically involves running guest OSes natively compiled for the CPU.
-   Use cases for virtualization include development, testing, and managing compute environments in data centers.

# Symmetric Multiprocessing (SMP) and Architecture

### Overview of SMP

-   Symmetric Multiprocessing (SMP) allows multiple processors to perform tasks simultaneously, enhancing performance and efficiency.
-   Each processor in an SMP system has equal access to memory and I/O resources, which facilitates load balancing and redundancy.
-   SMP systems are commonly used in servers and high-performance computing environments to handle large workloads effectively.

### SMP Architecture

-   SMP architecture can be implemented in various designs, including dual-core and multi-chip configurations.
-   Multi-core processors integrate multiple cores on a single chip, improving processing power without increasing physical space.
-   Systems can be designed with multiple separate processors, allowing for scalability and flexibility in computing resources.![Diagram showing a dual-core processor system with each processor containing a CPU, registers, cache, and both processors sharing a main memory.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/dc918b5d-5ecc-4bff-8ddd-347697e09c71/images/52a6b3f5690c42348acdda4ea0dde915.jpg?Expires=1747059501&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=h0XuRiydQeuASX68fPXQPqHVkIq72FOWLhRCsGk%2Fy80XaHUra%2Fz%2BhmiZM%2Fc9knzn%2FzhjF44UUaPsMrpj2eZHfBeAjdkXFVw2Ne1%2F%2BhbKzLl9JYLCFdAeQRAoFrDnykDLflQnkwkXHUFQXSJYhU%2F9kXUlzHhyxo5oc9TifG4y5jypqr5hmy4oAjnvv%2BAA5Np6GjUexRt1YTtNKPAf5DYchMX%2FLhWtFB0K2NzauQp7l10jK9YQAIdgC6rfHzPomnUeip%2Fe0qhJDpA85jiAGPsXan9rghnOmP9vXeJ1hKw5lqto20KMS7Kv5SuaJK4snHemCPXiF9%2BxOpzcDZZIFs9J5A%3D%3D)![Diagram of a processor showing two CPU cores, each with registers and L1 cache, sharing an L2 cache and connected to main memory.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/dc918b5d-5ecc-4bff-8ddd-347697e09c71/images/d539db2d3eff4cd79b088b427149baaf.jpg?Expires=1747059501&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=e%2BnVSk1lvCW3dMnGhOgfKbHtfg7hW2la5P1uWzVykxwpFSGgLi2Wuar39fHB87sDW18ctJBZMFRmTCvskSRlSPPKVr2S%2BXqhnU479rhakAjPsG2htUU4%2FklU%2BsOKC8iAzs51tYHU8q6UpKKsC0z6wWP4F4WPJOMh10c2XOEwtIPP%2BYs4jIsK04VhxTcVAsAI%2BvYyfuBH3by97cTR1SUPVrwrOARK3nPVlMV6jyVn24nzM6X4MYTGKH9QhPGjZoQLkMhBEdTB3cCJUzjUGf0ukv4YLnl5dXuLJ6Os1QLrtENYDkB8P9xNh7FLvKfQpYarwl3qUCo5l3lHAgDnOH6%2F0Q%3D%3D)

### Non-Uniform Memory Access (NUMA)

-   NUMA is a memory design where memory access time depends on the memory location relative to the processor, impacting performance.
-   In NUMA systems, processors can access local memory faster than remote memory, necessitating careful memory management in software.
-   This architecture is often used in large multiprocessor systems to optimize performance and resource utilization.

# Computer System Components

### Core Components of a Computer System

-   The CPU (Central Processing Unit) is the primary component that executes instructions and processes data.
-   A processor can contain one or more CPUs, with each CPU capable of executing multiple threads simultaneously.
-   Multicore processors integrate multiple cores, allowing for parallel processing and improved performance in multi-threaded applications.

### Multiprocessor Systems

-   Multiprocessor systems consist of multiple processors that work together to perform tasks, enhancing computational power.
-   These systems can be configured in various ways, including symmetric and asymmetric configurations, depending on the workload and application requirements.
-   Asymmetric configurations often have one primary processor handling most tasks, while others are in standby mode, providing redundancy.![Diagram of a distributed memory multiprocessor system with four CPUs, each connected to its own memory module and interconnected with each other.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/dc918b5d-5ecc-4bff-8ddd-347697e09c71/images/3560460ecc0e4b5e9dd6e6e5bafcbae1.jpg?Expires=1747059501&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=gCDTT4MKLUemge%2FwGJwe1oZ5h7vmxvXq3oOclQCXusb77OWeGHtTGVWuvqrTb3%2BLunaNLpGOiaqIwgBYwI5cKtZwmYZIw642HW1Tib0DHl8s2QjtYlI4pVk5Y%2BPTpJQ7mLnuSXhUmF2ZbpN3S6H30P%2BbDEUql9fMmleX%2Fa1bhg2iCqL7q%2BbeVPSz8XUTjdYJiELXt1b5tHdDLf36gJTYTVVUm74zM8k9Bizr%2BBqjrgyl6Dks6bO5lsLu%2FD0kO5UwF4kty2jw43eQIxxoUHT5h%2FOr8efoemAYwjOzxtB0wQwd7wDMbF3BmnE0LWYW8%2F9sQClEQVYUETMRBEkrCLKIdw%3D%3D)

# Computing Environments

### Types of Computing Environments

-   Traditional computing environments consist of stand-alone machines, often connected to networks for resource sharing.
-   Mobile computing environments include handheld devices like smartphones and tablets, which utilize wireless connectivity for communication.
-   Client-server models involve dedicated servers providing resources and services to client machines, enhancing resource management and security.![Diagram showing three computers interconnected to a storage-area network (SAN).](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/dc918b5d-5ecc-4bff-8ddd-347697e09c71/images/6fb4aefd4e5f4129bee902ab04201d27.jpg?Expires=1747059501&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=bmF7%2FKoDYm6yMpllsngnIUut51ZA5tD27Aa1pZr2Vl1P8TWh7Ti5lDerLEZDvwUQGKluHX5IFaZ60T3Y9irorlMKmTvBK0lwdXoLhu5mF8%2FLpMX5QmCMUmJ%2FyH%2FmPchfIvSMnISvQa4H8zFDRR0rKhSN7m7eRvdm9RvYHEzk3tBeEUSuyTXSRWlce1PIzsqsYWIyOZw3%2FfW%2BpUyqW%2B46Xl96hjXbvvPBPKCShRqf1%2BfsTHOC8O72gtzoLMQnKBEeGmM5zfbTosCfld2erZ8n6JCABJfuEwOFYIg4L31hzbHHWyCOGJyskSvU4zC6Lor5ESLkcD6JlzaZH03zvE%2BzxQ%3D%3D)

### Peer-to-Peer and Cloud Computing

-   Peer-to-peer (P2P) networks allow nodes to act as both clients and servers, facilitating direct resource sharing without a central server.
-   Cloud computing provides scalable resources and services over the Internet, allowing users to access applications and storage on-demand.
-   Different cloud models include public, private, and hybrid clouds, each serving distinct organizational needs and security requirements.

# Real-Time Embedded Systems and Open-Source Operating Systems

### Real-Time Embedded Systems

-   Real-time embedded systems are designed to perform specific tasks within strict timing constraints, crucial for applications like automotive and medical devices.
-   These systems may use specialized operating systems that prioritize timely task execution and resource management.
-   The design of real-time systems often involves trade-offs between performance, resource usage, and complexity.

### Open-Source Operating Systems

-   Open-source operating systems provide access to source code, allowing users to study and modify the software, promoting innovation and collaboration.
-   The Free Software Foundation (FSF) advocates for free software principles, emphasizing user freedom and community-driven development.
-   Examples of open-source operating systems include GNU/Linux and BSD UNIX, which have become popular in both academic and commercial settings.

# Kernel Data Structures

### Overview of Kernel Data Structures

-   Kernel data structures are essential for managing resources and processes within an operating system, often resembling standard programming data structures.
-   Common data structures include linked lists, binary search trees, and hash maps, each serving specific purposes in resource management and scheduling.

### Types of Kernel Data Structures

-   **Singly Linked List**: A linear data structure where each element points to the next, allowing for efficient insertion and deletion operations.
-   **Doubly Linked List**: Similar to singly linked lists but allows traversal in both directions, enhancing flexibility in data manipulation.
-   **Binary Search Tree**: A hierarchical structure that allows for efficient searching, insertion, and deletion operations, with performance varying based on balance.

### Advanced Kernel Data Structures

-   **Hash Maps**: Utilize hash functions to provide fast data retrieval, essential for managing large datasets efficiently.
-   **Bitmaps**: Represent the status of multiple items using binary digits, useful for resource allocation and management in operating systems.
-   Linux kernel data structures are defined in specific header files, providing a framework for developers to implement and utilize these structures effectively.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzNjY5MDg2Niw2NTk4ODI4NTUsODA1MT
czNDgwLC0xNTk0ODU1MTUwXX0=
-->