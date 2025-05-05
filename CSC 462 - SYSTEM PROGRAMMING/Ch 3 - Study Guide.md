# Chapter 3 Study Guide

# FILL IN
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
# Process Concept

### Definition and Components of a Process

-   A process is defined as a program in execution, which must progress sequentially. Parallel execution of instructions within a single process is not allowed.
-   Key components of a process include: program code (text section), current activity (program counter, processor registers), stack (temporary data), data section (global variables), and heap (dynamically allocated memory).
-   The program is a passive entity stored on disk, while the process is an active entity that is loaded into memory and executed.
-   A single program can have multiple processes running simultaneously, especially in multi-user environments where the same program is executed by different users.![Diagram of a memory layout showing the stack growing downwards from the maximum memory address and the heap growing upwards from the base address, with data and text segments below.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/6584abb7-9051-45bc-8750-4e8509ab2810/images/352b7253177346dba9d4aa5ade5d438a.jpg?Expires=1747059670&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=pySC3Fp2jAktVNDfAnorvKFJ9j6ksDNaJS1fPepdz2fmBsMMiaMWar3LmhFXsBIyAEpg9tlEjLLf9d00goxIwpm1t7me1NzEp0ee0Y5TyBNbpT644M1Up1Qz4rxjAlM%2FYd3MijR6Hju0%2FtqmFptL5Vm6ifiuHJX1frqdYMtg5a46zuRyAfiH1fBn5yYQ4UG%2FtF0tfukcYoRDf4igFcJwi3xbCy1AReGsLMCG%2BJwmnAlEQAMqC%2FGrWgfcWQzkOWLFU%2BOcdRsZvalnvvp8ZJwjBVpz7mdx7hHjPXctkG%2B4yDsWRJABuV59lC%2BZ9Qhr8wTtkJ%2B1gAuJm%2BSKfMH5zPXZ5Q%3D%3D)![Diagram showing the memory layout of a C program, illustrating the stack, heap, initialized data, uninitialized data, and text segments, alongside the corresponding C code that uses dynamic memory allocation.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/6584abb7-9051-45bc-8750-4e8509ab2810/images/dbea505ebbc1412290796dd12d180dce.jpg?Expires=1747059670&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=sA5CKBcjXiZ0Av8VtPmtsoTn%2F2IvWFgqpcy33HL7zURLKPtt%2BiOplEzoL9CD6Zf7cERRv2psOPT5pkpWr73CaiCke3Huns4m69BCmvv3Vj4HjYliJzFgOHrhfR4eQL1eOJgrvoOuFwfbOPabF%2B9ZpkmCihH11sTuzSPGKDPSp0oOofNIHp0QdTQaW%2BU6uWmKq%2FL8zOYwnH%2FbiObpydFfVo9Q1WqATupkzjqtfSM3KIMFkiXXtgfJbjfe8RUQuCS2Lhw%2B4IMeCzxCY%2Fi8FeH7zp2IHb1xocSfrgYJVYkV%2Fw8hlLNRkkjoxW4wf72EZ7dBOmgKBlfLGtsuBHfFq5Ts4Q%3D%3D)

### Process States

-   A process can exist in several states: New (being created), Running (executing instructions), Waiting (waiting for an event), Ready (waiting for CPU assignment), and Terminated (finished execution).
-   The transition between these states is crucial for process management and scheduling in an operating system.
-   A diagram illustrating the process state transitions can help visualize these changes.![This state diagram illustrates the lifecycle of a process in an operating system, showing transitions between states such as new, ready, running, waiting, and terminated.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/6584abb7-9051-45bc-8750-4e8509ab2810/images/5f1a3b497fcc45ffa7b9eefc9c3e3729.jpg?Expires=1747059670&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=yPInebpzzb45c%2Bher54EFEPfdpOLYSVxKchsFi0PctacQjsawnxZVkb8cVjWL11bsAyW39Rz%2BwxSg%2FfiK0LF8O5hWX1V76MxxoFcycLS6l1YNLt0orri2MdhtoIoxWvkNkxNw7%2Bg9geu5nWX%2B3NIam%2BcIN0tVrUVirUDTwn%2FI9EI5UOtZ4SXLZ6Z1shh3gSztSRCkIhaZr1PYWDXkIoxN3AP67zk39DEsYn3JzEaGbWfD9pGWDNMrF8B8f3ByaVfKZKHxfYKNVlgDaeH7KINNBaTMCX0daWHWSalarDgPqa4v%2FZT1r7Fkm%2BKIkWOw2er136NPJ8XJR3F2RpZ4V1nYQ%3D%3D)

### Process Control Block (PCB)

-   The PCB is a data structure that contains important information about a process, including its state, program counter, CPU registers, scheduling information, memory management details, accounting information, and I/O status.
-   Each process has a unique PCB that the operating system uses to manage process execution and scheduling.![Diagram of a process control block showing process state, process number, program counter, registers, memory limits, list of open files, and other information.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/6584abb7-9051-45bc-8750-4e8509ab2810/images/4ec077b1fce5428aad420b0657903979.jpg?Expires=1747059670&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=iPOdRqP9%2BfzA7cDT5C%2B%2Fq58Ppc4o1FslHri4M4uLtFSo3sk7rLOXXK2KSQZLEULelEDJrrykKk58QdHZ6jq0Iw3zd58MDyRM%2BjI%2BaP6YXeDKylHcoYjb1p9dx1E4DTibo%2Bu4bnM3g8rUQhYrkcx60xotuTmo9hgrm2VRlbmLyFmA9sI5FdhNZnj4C%2FwGlu2Ef7vgCAoszLrDgYKwJUe8wj8jkR7lh1IVk8PaepPCxqGcNlSq0SL9bclM0rsvayhK0J%2FqbP%2FbpuXoxe7UWXbWR0VsMrTGidYlzDhnrplmQ5MwA4KPNSEbjogzGc9aYGkvkXhW52t0U3%2BwUbR0E5F3pQ%3D%3D)

### Process Representation in Linux

-   In Linux, processes are represented by the  `task_struct`  C structure, which includes fields such as process identifier (pid), state, scheduling information, parent process pointer, and memory management details.
-   Understanding the structure of  `task_struct`  is essential for kernel programming and process management in Linux.![Diagram showing a round-robin scheduling algorithm where multiple processes ("struct task_struct process information") are cycled through, with one process ("current (currently executing process)") actively running at a time.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/6584abb7-9051-45bc-8750-4e8509ab2810/images/f4a61f70040a4ba3ac13c57d253243b4.jpg?Expires=1747059670&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=3Y%2FHQslyWQcFFL0kC%2FlbAg9XOtC2slgwiYIMDD9F48xjK3cWjWhgi4WoQcF%2F%2FWrQCiCxjFX1Hx8Jh1mHiU7%2Bw182zV5yO4z%2FWpsMBO%2FyX1rKFpvnf9Lwg1jPeRr%2FPhLQyZJB0kDoXOhaayjTHB9KnYFt5jyZnjh3Ipf%2FVSHZPsfzqV0t2%2BzphDbKP07gfRhaEgU8BWjk2eaZF9Nk3JLazxbe0IXjHvRBIIyI51CGEZHo8QAAozxle%2F2a1eR%2B7V5BnCqSMI%2Bz4sY6vrqfnVtt%2FltnRtI8rFFq1P2Qf2PyF%2FsKeEQIPP830ZX0EE5QxsaRAtCi66rUjiMZQtCYIet%2BTQ%3D%3D)

# Process Scheduling

### Overview of Process Scheduling

-   The process scheduler is responsible for selecting which process to execute on the CPU, aiming to maximize CPU utilization and minimize wait times.
-   Scheduling queues include the ready queue (processes ready to execute) and wait queues (processes waiting for an event).
-   Processes can migrate between these queues based on their state and resource availability.![This diagram illustrates two queues, a ready queue and a wait queue, each containing process control blocks (PCBs) linked together, representing a scheduling algorithm.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/6584abb7-9051-45bc-8750-4e8509ab2810/images/60fad14b809f4849b32ce51cf2f8536d.jpg?Expires=1747059670&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=lWseSQ85XPDEIUoU8LmtslTjAtaT%2BzGQwXgXe0dN89B3BJ7R3ulQ26MF4kfZRfiMgP%2F9dS1MaFarhKsi%2BLB2SC7uBwH%2FD9roqXoUoBD9g1N%2FQhYdc23MhXSS0g5lTv%2F%2BQjzCs4oQRuMPWgZmne%2BZtPUUyddPsQo6T8iuYlT5R2i2C4OljftXYNy9NhSFZGQuNmfxIAUP%2FTyJA9sxEXK%2Bc%2Bqnt91P9lBA5%2B9m87OBakWNXqCTiss9vqDW5jKZmu8Nhdt4apVa2j8w0shDWdVTiYVqpK7n59wkIf9GvNYWpVhGUfWkWEN7C1AIBnEfIqlnTcA56PpsZlbv93TfG0KBpA%3D%3D)

### Context Switching

-   A context switch occurs when the CPU switches from executing one process to another, requiring the system to save the state of the old process and load the new one.
-   Context-switch time is considered overhead, as no useful work is done during this transition.
-   The complexity of the operating system and the PCB can affect the duration of context switches.![This diagram illustrates the context switching between two processes (P₀ and P₁) managed by an operating system, showing how the system saves and restores process states using Process Control Blocks (PCBs).](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/6584abb7-9051-45bc-8750-4e8509ab2810/images/78c79487f011470c9a187c0df760626d.jpg?Expires=1747059670&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=Ndj4aySALjhEdvhE95GpumKkmOG%2BARdljb8XrlK4Mvzt%2FfsqfH0le3yiSwQplqzW4uCAsWWTgi1EgqVD7lT0aee7IrP9L0uNpU7tkQJFSf0w12Jh%2BoDcORn07kVTgLmAfdU31wjEnVSslv9Zt%2FtGEa6JUdx9F1q2%2FjPer5uikWY76Ez58zaW4oL1m%2BThM4bXVDDnPoyB5f0ooxLEfpxz2mPzN1OW2xQyxdfV7dkXa72DsvMlvknsiIKuVcu0UbB35Mflt%2FJ%2BdH5MluEYaa8C7kYyfnm6yq8%2B6wBcaIyWJielCPsZbH%2BK9Um53IP92f1K2ttrpmtljP8L4Ifh2vFzlg%3D%3D)

### Multitasking in Mobile Systems

-   Mobile operating systems like iOS and Android handle multitasking differently, with iOS traditionally allowing only one foreground process at a time.
-   Background processes in iOS are limited in functionality, while Android allows more extensive background processing through services.
-   Understanding these differences is crucial for developing applications that run efficiently on mobile platforms.

# Operations on Processes

### Process Creation

-   Processes are created by a parent process, which can spawn child processes, forming a hierarchical tree structure.
-   Each process is identified by a unique process identifier (pid), and resource sharing options can vary: all resources, a subset, or none.
-   The  `fork()`  system call in UNIX creates a new process, while  `exec()`  replaces the process's memory space with a new program.![A process tree diagram shows the parent-child relationships between processes, with systemd (pid=1) as the root process.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/6584abb7-9051-45bc-8750-4e8509ab2810/images/4d0f93f33fca4da889084147f98ed70e.jpg?Expires=1747059670&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=B4RjX%2BLfgc%2Bha1nisCe%2BkFj9YX4G92xnkFvuShsB7QnYAuUdg8mQo3bmtB6izsrA6mODj3kBwQG7uW0yeGMHni2XuR1DIdNtrqgwiRWNBqbT9CqUWpdloNeBFBpNC0ULqUgUxJ86rDJhC6R9rTLkaTSsgzcVPvaxDyXFAQusDuhzyUsjhUciaR8zLBrTw%2BML%2BKAtgy1MAg1PMyJpUxSjYNMoGXMj5RfhFY6vPyoZGL926GKoPDwsACH4OQoX%2BxNI5nFaosu8QB%2BF2AZMc125S0fEof%2FlyAIQoA%2FipJd8oCDhkv9U1JqxfbtLdauesavmYmyEBM%2B%2BildqW5nCQirnGQ%3D%3D)![A state diagram illustrating the fork() system call in which a parent process creates a child process, and the parent process waits for the child process to finish.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/6584abb7-9051-45bc-8750-4e8509ab2810/images/d13a75253b394f8dbba1663175be632c.jpg?Expires=1747059670&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=Wct%2BbKcVPZl7WALIr9m9MJwQCMKg%2BXqJBzUF25zmvtc6CVnSyOL6QQH9AdTsiL9wdTlbTK3zdcmlhBtEnnHVtDjsL0yGpU6nnfhkZgvcMHRR6m57LifVSh%2BiJ%2FLrWevI4g9nUkYKSmaOOPcZpOd4w%2BuI3qd8wtsIqcFXUc1tMqAMFErEPT56eRFCw6SQWde5eVnnu9pIryKqZUpbsfL4TmJ8SBOecXSrimA%2B%2B%2FBmw38Njnqu3J%2FQWnyw6Q%2FtcYnLKyrCMqNOhMNZi4u1FcgAUcoeebW6o8MO5%2FmXD2QgcI8nSV2CoyuqHb7%2FUH9dGwvLnJ710nS9%2BU3Mo2RvKSvRZw%3D%3D)![This image shows C code that uses the  system call to create a child process that executes the  command, and the parent process waits for the child process to complete.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/6584abb7-9051-45bc-8750-4e8509ab2810/images/fa35f2c892a6424db9f923d1cab3033c.jpg?Expires=1747059670&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=cfd9XWeI077cFaBqT4FXKIFS8Ctq0yBfXeRnH0PP8fzg7S0q9GYMyQc3Q3RxweEmmPyw%2FGUXauCQziWP3R9jhn1%2BcBJTTg98sGk1wkfa4NwdaixfdTMpSOtbV6Oi1H2yL8e4AEDuOOG4kNkjkurFLfDCPVGqjd3UWGeTRJ6meebAVm99gFh%2BPLmRXhmw4IDHxleT8tweZsmCycLHv8fmF95o2BW8I7y5%2BpZA71jckPkL0tsxJPuQHDUiHWXH%2FarcdQyb%2BwBk2bsWHJq0sWosE%2BervWQ28ra2TZTRyLuwzggX%2BD2Y9IhbuEOKZ4cYo351%2FReS4H0CxCxS%2FbwlqwZ%2B4A%3D%3D)

### Process Termination

-   A process terminates by executing its last statement and requesting the operating system to delete it using the  `exit()`  system call.
-   The operating system deallocates the resources used by the process, and the parent process can retrieve the termination status of the child process using  `wait()`.
-   The parent can also terminate child processes using the  `abort()`  system call if necessary.

# Process Management

### Process Termination

-   Process termination is a critical aspect of operating systems, where a parent process can terminate its child processes using the  `abort()`system call for various reasons, such as exceeding resource limits or the parent process exiting.
-   If a parent process terminates, all its child processes are also terminated, leading to a phenomenon known as cascading termination, where all descendants of the terminated process are also killed.
-   The  `wait()`  system call allows a parent process to wait for the termination of a child process, returning the child's exit status and process ID (PID). Example:  `pid = wait(&status);`
-   If a child process terminates without a parent waiting for it, it becomes a zombie process, while a child process whose parent has terminated without invoking  `wait()`  becomes an orphan process.
-   The operating system manages the lifecycle of processes, ensuring that resources are properly deallocated upon termination. This includes cleaning up memory and other resources used by the terminated processes.

### Android Process Importance Hierarchy

-   Mobile operating systems, like Android, prioritize process management to reclaim system resources, particularly memory.
-   Processes are categorized from most to least important: Foreground processes (user-facing), Visible processes (partially visible), Service processes (background services), Background processes (not visible), and Empty processes (inactive).
-   Android will terminate processes starting from the least important to free up resources, ensuring that critical user-facing applications remain responsive.

# Multiprocess Architecture

### Chrome Browser Architecture

-   Unlike traditional single-process web browsers, Google Chrome employs a multiprocess architecture to enhance stability and security.
-   The architecture consists of three main types of processes: the Browser process (manages UI and I/O), the Renderer process (handles web page rendering and runs in a sandbox), and the Plug-in process (for various browser plug-ins).
-   Each website opened in Chrome runs in its own Renderer process, which isolates it from others, preventing a single website from crashing the entire browser.
-   The sandboxing of Renderer processes restricts their access to disk and network resources, minimizing the impact of potential security exploits.

# Interprocess Communication (IPC)

### Overview of IPC

-   Interprocess communication (IPC) is essential for processes that need to cooperate and share data, allowing them to affect each other's execution.
-   There are two primary models of IPC: Shared Memory and Message Passing, each with its own advantages and use cases.
-   Cooperating processes may need IPC for various reasons, including information sharing, computation speedup through parallelization, modularity, and convenience.![This diagram illustrates two methods of inter-process communication: (a) shared memory and (b) message passing.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/6584abb7-9051-45bc-8750-4e8509ab2810/images/ec1f4e8734dc4be68f683ee1198b5c12.jpg?Expires=1747059670&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=rvt9nTUY9ALpi4t54Eb5AQpJlEK3yaSqAgMxYbrM9sCnMbXeXnf7BHfet78b7DyeKtnpRgdm0h1UduAIy56vEunKn4Ti7E2anLTmlZfVnaSKpuhd9PD%2BFNWQ3YmDfnNWAW6Sw9sg8rdPcYvqkx0GsO5Oy8VSw7Y%2BWAGh5SJFRyOAUwW6neS4wEyAwiHE3D512hLA02c34Rs1SOBDm3wsdOa6ZGsrwUnhws1SPZeZYnAiqUa5OCkSiLUArQfN6Ww0VProQZbRR6%2Bk6gDNDSHvsK5%2BQ4sZAYZSEJGq96XSAY8vKQb1nQnMXQBYQPekhZeFVaj34%2BIK%2Fg7%2Br7JLle6blw%3D%3D)

### Shared Memory Model

-   In the Shared Memory model, processes communicate by accessing a common memory area, which is controlled by the user processes rather than the operating system.
-   Synchronization is a major concern in shared memory IPC, as multiple processes may attempt to access the shared memory simultaneously, leading to potential data inconsistencies.
-   The Producer-Consumer problem is a classic example of shared memory IPC, where a producer process generates data consumed by a consumer process.![This image shows C code that creates a shared memory object, configures its size, maps it to memory, and writes the strings "Hello" and "World!" to it.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/6584abb7-9051-45bc-8750-4e8509ab2810/images/4adcff28784e4b31af9e5c90ce1d10aa.jpg?Expires=1747059671&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=Wp%2BDLaTTdJn5TmJ%2F6sy6FNs0lXlqXP9aVic7rJXulvx9%2FRBPqv2CnO24ETg2tDVzo8gzQgh09p6IsaMjUq6i1eXhfoaOhWKzeNS4YUOx8WIpk0f1vf8ZHNSseJ9bm070iehaW6ICLng8NnzIMZeE%2B5w3Vjrjs3sZ5h2EiEJ1RnGJQUomft9y%2F8JFb7uug79qOTiGF50SnvTa18pO%2F0V0FtHD6HXVocGZbenlBFShV6%2Ffjw%2FxIWDLpKxa2GmFL%2Bpdp2YJna7AlDmYLov4Uhlbf6LI8gEKpRFdqYohBy0Xzfz8%2BiVv6%2BvRElBGwHWB%2FNqoYpvnY%2BMEqruObQakpjJohg%3D%3D)![This image shows C code that opens, maps, reads from, and removes a shared memory object named "OS".](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/6584abb7-9051-45bc-8750-4e8509ab2810/images/5bb253ac2ab84bf086df4784d1c30bb1.jpg?Expires=1747059671&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=nfbDr2mU3JhSXy1KRgYCdRWktxfBxAvuoJpfl354clF3bFwKXU859fQtTcFNcT68Og4G4tR6BSf9fOKsHbZIDYEsexlhzlfjT3s05LDIHsaKNwsDFu517kFpSTkHeI3VI8QLl3ylRu9fxAu3UhA1JvcVbFLFIhUYGlOUfLx%2FJDZNHUEqTLvLBJSXSCGbvX30AHdtqdscxY49%2BL5XpnQK3DdcvSJWFfpj0S3RrLLYHFmLqHKNw9sI7ksJZXXOl2EVxGDwkWM155fDGE5t0Lp9BJoJQ32exr%2BuWJ1RG94GcTREkwuHp5iR5fbA%2BOKQgGB7ABCB2KH3XC0KbV8iAqWjyw%3D%3D)

### Producer-Consumer Problem

-   The Producer-Consumer problem can be implemented using a bounded buffer, where the producer must wait if the buffer is full, and the consumer must wait if the buffer is empty.
-   A solution involves using a shared buffer and maintaining indices for the next item to produce and consume, ensuring that the buffer does not overflow or underflow.
-   An enhancement to the solution includes using a counter to track the number of filled buffers, allowing for more efficient synchronization between producer and consumer processes.

### Race Conditions

-   Race conditions occur when multiple processes access shared data concurrently, leading to unpredictable results. For example, incrementing a counter without proper synchronization can lead to incorrect values.
-   The initial solution to the Producer-Consumer problem avoided race conditions by ensuring that the buffer could only be filled to a maximum of N-1, preventing simultaneous access issues.
-   Understanding race conditions is crucial for designing robust IPC mechanisms, and further details are discussed in Chapters 6 & 7 of the course material.

# Message Passing Model

### Overview of Message Passing

-   In the Message Passing model, processes communicate by sending and receiving messages, avoiding the need for shared variables.
-   This model provides two primary operations:  `send(message)`  and  `receive(message)`, facilitating communication between processes without direct memory access.
-   Message size can be fixed or variable, and establishing communication links between processes is a key aspect of this model.

### Implementation Issues in Message Passing

-   Key implementation issues include how communication links are established, whether links can be associated with more than two processes, and the capacity of each link.
-   Considerations also include whether the communication link is unidirectional or bi-directional, and the implications of message size on communication efficiency.
-   Effective message passing can enhance modularity and flexibility in process communication, making it suitable for distributed systems.

# Overview of Communication Links

### Physical and Logical Communication Links

-   **Physical Communication Links**: These are the tangible means through which data is transmitted. They include:
    
    -   **Shared Memory**: Allows multiple processes to access the same memory space.
    -   **Hardware Bus**: A communication system that transfers data between components inside a computer.
    -   **Network**: A collection of computers and devices interconnected by communication channels.
-   **Logical Communication Links**: These define how processes communicate logically, including:
    
    -   **Direct or Indirect**: Direct communication requires processes to name each other, while indirect communication uses mailboxes.
    -   **Synchronous or Asynchronous**: Synchronous communication blocks the sender until the message is received, while asynchronous allows the sender to continue processing.
    -   **Automatic or Explicit Buffering**: Buffering can be managed automatically by the system or explicitly by the programmer.

### Direct Communication

-   **Direct Communication**: In this model, processes must explicitly name each other to communicate. The communication can be:
    -   **Symmetric Approach**: Both processes must know each other’s identity. For example:
        -   `send(P, message)`: Sends a message to process P.
        -   `receive(Q, message)`: Receives a message from process Q.
    -   **Properties**:
        -   Links are established automatically between processes.
        -   Each link is associated with exactly two processes.
        -   Links can be unidirectional or bi-directional.

### Indirect Communication

-   **Indirect Communication**: Messages are sent and received through mailboxes (or ports). Key points include:
    -   Each mailbox has a unique identifier.
    -   Processes can only communicate if they share a mailbox.
    -   Links are established only if processes share a common mailbox, allowing multiple processes to communicate through the same mailbox.
    -   **Operations**  include creating, sending, receiving, and deleting mailboxes.

# Synchronization and Buffering

### Synchronization in Message Passing

-   **Synchronization**: Message passing can be blocking or non-blocking:
    -   **Blocking (Synchronous)**: The sender is blocked until the message is received, and the receiver is blocked until a message is available.
    -   **Non-blocking (Asynchronous)**: The sender sends the message and continues processing without waiting for the receiver.
    -   **Rendezvous**: Occurs when both send and receive operations are blocking, requiring both processes to synchronize.

### Producer-Consumer Problem

-   **Producer-Consumer Model**: This is a classic example of message passing where:
    -   **Producer**: Generates messages and sends them.
        
        ```c
        message next_produced;
        while (true) {
            /* produce an item in next_produced */
            send(next_produced);
        }
        
        ```
        
    -   **Consumer**: Receives messages and processes them.
        
        ```c
        message next_consumed;
        while (true) {
            receive(next_consumed);
            /* consume the item in next_consumed */
        }
        
        ```
        

### Buffering Strategies

-   **Buffering**: Messages can be buffered in three ways:
    -   **Zero Capacity**: No messages are queued; the sender must wait for the receiver (rendezvous).
    -   **Bounded Capacity**: A finite number of messages can be queued; the sender waits if the queue is full.
    -   **Unbounded Capacity**: An infinite number of messages can be queued; the sender never waits.

# Examples of IPC Systems

### POSIX IPC

-   **POSIX Shared Memory**: Involves creating a shared memory segment using:
    
    ```c
    shm_fd = shm_open(name, O_CREAT | O_RDWR, 0666);
    ftruncate(shm_fd, 4096);
    
    ```
    
    -   Memory is accessed using  `mmap()`  for reading and writing.

### Mach IPC

-   **Mach Communication**: This system is message-based, where even system calls are treated as messages. Key functions include:
    -   `mach_msg()`  for sending and receiving messages.
    -   Ports are created using  `mach_port_allocate()`.![This image shows a code snippet demonstrating client-side message construction and transmission using the  function, specifying header details, message size, and port configurations.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/6584abb7-9051-45bc-8750-4e8509ab2810/images/74e8b1b5023947d9965519dc99f70130.jpg?Expires=1747059671&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=jb3O9r9nHGPGk21ogStaMciDl0XGqdHQd0JiysY%2FWDfcswhUXbwow%2FG%2Bv%2BMIUSksnHjNJvFNrQ3lIsIQwCgXkZL2HoNikkkisbMOI8joxTgDiC%2F595YuRGQO%2F6bA6UfgIvkhVk5FIrxohlKttOR2nXMKaKPP6Xw4i5v28OH9lkI%2B6b6ME2hZgx7qwIrwUTooErAERkv1FGNpsKzPL9Vhho2hvIwWVqwWuw4bXbmQdtfnmobg4WMNYgFl52FJD1AztQj0Bhq397fkDZhG1xLksePSFkc0iD7lrUtdHCe13W9dKml6Fo4JlEz%2F%2FZZa1YCUaC0pZZQko4ZlqTLJ1eeLaw%3D%3D)![This image shows a code snippet for a server that receives messages, specifying message header, sending method, size, receive port, and timeout settings.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/6584abb7-9051-45bc-8750-4e8509ab2810/images/abff01d496f5410fbe173bf3e685443f.jpg?Expires=1747059671&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=xP%2Fo7x6Sxx4StWb1fAaE9BvnKRRFG0ZqlBNOLFsKm%2Br%2BvNyynkgeyJCXcc4PqO9ytc2GJ1cb9WzaOc7MetpDN7%2BKjpMtEtsD0mT%2Faj9WlwB78zQJUiGSoSEgvPOLBSodFy9VFR9LNdb6y4U6eDnc6m7Mc%2FCkVQd4sFB2%2FURAfHh1WOUGZtI%2BRX4OgowAjJ%2FDITCAq2e%2FVl4UbxDCUz5SC4bVQSniTMXyDLYZ3I3zZ5hSOUfpSLDg%2BG7Yz42S6wSZkVn7XS0yRokIRVswI07Su%2BLLIeVUpxsQttiZiRxeX5uLr18qpTWJkdgmQGZgMIjX2m2a%2F%2BlUTqk5b1cN0A%2BBlw%3D%3D)

### Windows IPC

-   **Windows IPC**: Utilizes advanced local procedure call (LPC) for message-passing. The process involves:
    -   The client opens a handle to the connection port and sends a request.
    -   The server creates private communication ports for the client.![Diagram illustrating client-server communication via connection ports, client and server communication ports, and a shared section object exceeding 256 bytes.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/6584abb7-9051-45bc-8750-4e8509ab2810/images/cb2239620d104c6dbf6e212536c778af.jpg?Expires=1747059671&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=tvIG8HLlp6HVZYlWD5ZO4bsE0mbU7WSk%2B0IcJWkImEZru2i4xYzz6VO0Mtw8hctCnU4edvFuAOjOWXN0yxcrSC5%2B%2Fab1eo4YLrgqzNJuQJ9snxFMFLDLDzyj3Y2aoIVOzUBwCSY2z3wHNCM75TNSMYgB7BdTbWrUCOJZuttY7eBMXLK4hIzTIFbPiOb6YdBcKN3E3doiiF0lpk5Nn8HwAbrfeIjVgOxljCl4g3cH48FxOGsIiEYk2nyzh%2BOQrqHNmVhryS%2FjjZE60o9kEr4oKqKd%2BaC2zsp2xkghErDZsE79Bo74W4T6lQKUaUEP3qtkaEqJ0Yy0ZMDze4UeK9bxIg%3D%3D)

# Advanced Communication Techniques

### Sockets

-   **Sockets**: Defined as endpoints for communication, combining an IP address and a port number. For example:
    -   `161.25.19.8:1625`  refers to port 1625 on host 161.25.19.8.
    -   Sockets can be connection-oriented (TCP) or connectionless (UDP).![Diagram showing a connection between host X (146.86.5.20) and a web server (161.25.19.8) via their respective sockets.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/6584abb7-9051-45bc-8750-4e8509ab2810/images/efd9a563be1c478e8202b65bd3e42c14.jpg?Expires=1747059671&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=R9AuLHCkQrZjGrtVAN0r9zzIxhdYURr%2FfFP1HnERt8LYkEfVJrYB2huXBEJnI6YAq5lNjy4RLvXD%2FGGdraqBUvf6amr%2F%2FKzR%2Bh7SwLY7IT9nhPr1n0peTQPEVrwGkTW%2Brc%2BCxJvRH3BQrhyFm%2FZ%2Ft5Gc%2BpErZwiDtszkluUMyrjss4AwDF77maiPpBooK7hB54J5iN2JBgq2z9p4cRZW5A1NdL5eS%2Fa3LJNXjPN1OOOG86dcqPbMyasVhz0O068C7MMjrpOeQPYSNqrUDlX2LGxOIF5Cu4ZFrSuV5HBKUvRnvybQW5N8PbzpqUJLoM2Rx3a%2F0cFk1z%2BfTKrxpBew0A%3D%3D)

### Remote Procedure Calls (RPC)

-   **RPC**: Abstracts procedure calls between processes on networked systems. Key components include:
    -   **Stubs**: Client-side proxies that marshal parameters for the server.
    -   **Data Representation**: Handled via External Data Representation (XDL) to accommodate different architectures.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ0MTAzOTM0NSwtMTU2MTIxMzI0MywzND
c3MTg1OTRdfQ==
-->