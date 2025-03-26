# Chapter 4 Study Guide

# FILL IN



# ANSWER

# Overview of Threads and Concurrency

### Basic Components of Threads

-   Threads are the smallest unit of processing that can be scheduled by an operating system, consisting of a thread ID, program counter, register set, and stack.
-   Threads share the same memory space of their parent process, allowing for efficient communication and resource sharing.
-   Contrast with processes: processes have separate memory spaces, making inter-process communication more complex and resource-intensive.
-   Threads can be created and managed more efficiently than processes, leading to lower overhead in context switching.
-   Example: In a web server, each request can be handled by a separate thread, allowing multiple requests to be processed simultaneously.  
    

### Benefits and Challenges of Multithreading

-   Benefits include improved responsiveness, as threads can continue executing while others are blocked, crucial for user interfaces.
-   Resource sharing among threads is easier than managing shared memory or message passing, leading to simpler code.
-   Thread creation is less resource-intensive than process creation, making it economical for applications that require frequent task switching.
-   Scalability is enhanced as applications can leverage multicore architectures to run multiple threads in parallel, improving performance.
-   Challenges include complexity in design, potential for race conditions, and difficulties in debugging multithreaded applications.

# Multicore Programming

### Understanding Multicore Systems

-   Multicore systems allow multiple threads to run simultaneously, increasing the potential for parallelism in applications.
-   Programmers face challenges such as dividing tasks effectively, balancing workloads, and managing data dependencies.
-   Testing and debugging become more complex due to the non-deterministic nature of thread execution in multicore environments.
-   Example: A video processing application can split frames across multiple cores for faster processing.  
    

### Concurrency vs. Parallelism

-   Concurrency refers to the ability of a system to manage multiple tasks at once, while parallelism involves executing multiple tasks simultaneously.
-   On a single-core system, concurrency is achieved through time-slicing, where the CPU switches between tasks rapidly.
-   On a multicore system, parallelism allows multiple threads to run at the same time, improving performance significantly.

# Threading Models and Libraries

### User Threads vs. Kernel Threads

-   User threads are managed by user-level libraries, allowing for flexibility but limited by the kernel's scheduling.
-   Kernel threads are managed by the operating system, providing better concurrency and resource management.
-   Examples of user-level thread libraries include POSIX Pthreads, Windows threads, and Java threads, while kernel threads are supported by most modern operating systems.

### Multithreading Models

-   Many-to-One: Multiple user threads mapped to a single kernel thread; blocking one thread blocks all.
-   One-to-One: Each user thread corresponds to a kernel thread, allowing for greater concurrency but with overhead.
-   Many-to-Many: Multiple user threads can be mapped to multiple kernel threads, providing flexibility and efficiency.

# Implicit Threading and Thread Libraries

### Implicit Threading Approaches

-   Implicit threading simplifies thread management by allowing compilers and runtime libraries to handle thread creation and scheduling.
-   Common methods include thread pools, fork-join, OpenMP, Grand Central Dispatch, and Intel Threading Building Blocks.
-   Example: Thread pools maintain a set of threads that can be reused for multiple tasks, reducing the overhead of thread creation.  
    ![This code snippet shows a C function, `runner`, that calculates the sum of integers from 1 to an upper limit provided as a parameter, using pthreads.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/ae0fd761-bf65-4c52-9dd5-c13b43b5f9a7/images/19ecd2b73aef475380b3b2f50629c6ad.jpg?Expires=1743600996&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=BZqoWvfywUsJcjNEonjXa08vSDD6M2p3FGSk%2FJx1I7OaTufBkpRAc7Z6dLneH3hLV2nstQtDw1blbujcYbNE9tNIZPO6DJ6BxFES6zXf1gqWRRjOvS3WDep5l2bVEC%2B5IsyXeqKnuYDSnLHh860XnCPP5adR5zXNXCszpQodBSXHcjsYikAblL8RkzYA55K8%2FhnagdMj0tAhrFlIItvUej9LmJ%2B%2BtQliqqTvGkr6CdU7VD4pRE44upz7n978TI%2BiVIChUl8MiEKBeFu73nbn2K%2BS%2BQO%2Bhsev%2B0S1NRNFOzEgItMmoYaPTJkdvTPgt4n%2FVAKi8qnWwdsENtZBGtWkWw%3D%3D)

### Thread Libraries Overview

-   Thread libraries provide APIs for creating and managing threads, with implementations varying between user space and kernel space.
-   Pthreads is a widely used POSIX standard for thread management in UNIX-like systems, offering a robust API for synchronization and thread control.
-   Java threads are managed by the JVM, allowing for cross-platform thread management and providing the Executor framework for easier thread handling.

# Fork-Join Parallelism

### Overview of Fork-Join Parallelism

-   Fork-Join Parallelism is a computational model that divides tasks into subtasks, which can be executed in parallel, and then combines the results. This model is particularly effective for recursive algorithms.
-   The general algorithm involves two main steps: ****Forking**** (splitting tasks) and ****Joining**** (combining results).
-   This model is widely used in parallel programming to optimize performance on multi-core processors.  
    

### Fork-Join Parallelism in Java

-   In Java, the `ForkJoinTask` is an abstract base class that provides the framework for implementing fork-join parallelism.
-   Two primary subclasses of `ForkJoinTask` are `RecursiveTask` (which returns a result) and `RecursiveAction` (which does not return a result).
-   The `compute()` method is overridden in these subclasses to define the task's logic, allowing for recursive decomposition of the problem.

# OpenMP and Parallel Programming

### Introduction to OpenMP

-   OpenMP is a set of compiler directives and an API designed for parallel programming in shared-memory environments, primarily for C, C++, and FORTRAN.
-   It allows developers to identify parallel regions in code, enabling concurrent execution of code blocks.
-   The directive `#pragma omp parallel` is used to create threads equal to the number of available cores.

### Parallel Loops in OpenMP

-   OpenMP provides constructs to run loops in parallel, significantly improving performance for large iterations.
-   The `#pragma omp for` directive can be used to parallelize for loops, distributing iterations among threads.

# Grand Central Dispatch (GCD)

### Overview of GCD

-   Grand Central Dispatch is a technology developed by Apple for macOS and iOS that simplifies concurrent programming.
-   It provides an API and runtime library that allows developers to identify parallel sections of code and manage threading details automatically.

### Dispatch Queues in GCD

-   GCD utilizes two types of dispatch queues: ****serial**** (FIFO order, one block at a time) and ****concurrent**** (multiple blocks can be executed simultaneously).
-   System-wide queues are categorized by quality of service (QoS), including user-interactive, user-initiated, user-utility, and user-background.

# Threading Issues and Concepts

### Thread Cancellation

-   Thread cancellation refers to terminating a thread before it has completed its execution, which can be done either asynchronously or deferred.
-   Asynchronous cancellation stops the thread immediately, while deferred cancellation allows the thread to check for cancellation requests periodically.
-   In Pthreads, cancellation can be requested using `pthread_cancel()`, and the thread must reach a cancellation point to be terminated.

### Thread-Local Storage (TLS)

-   Thread-local storage allows each thread to maintain its own copy of data, which is crucial in multi-threaded applications to avoid data corruption.
-   TLS is different from local variables, as it persists across function invocations and is unique to each thread.
-   In C, TLS can be declared using the `__thread` keyword, allowing for thread-specific data management.  
    ![This image shows C code for a function called `Summation` that calculates the sum of integers from 1 to a given upper bound using a loop.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/ae0fd761-bf65-4c52-9dd5-c13b43b5f9a7/images/fea5b7242c0c461f9230745fa72338a8.jpg?Expires=1743600996&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=GEelQwm51vMy%2BzAouHFQWlF1LkIyGDHsaW8vvnWVTYk0iY8IQoY5O1ivTbtbxQ0sq8Bg1Wf6AjRz0WH1Yaaf%2BrEX081upReMzcZV2eKIbsXTTHh77%2FpZcXNdvMT9uWrSMVxFtoY3wyg0b86OCdo0ghPP1BoMOyw50Q1B0kH48pT4jpgbfyXf8Zy5qom7NfLar2hlbZMfmZUFPdm7uBxPpuGyHKyblW1RtA2noBzUqUwkmfmZ8ohFC9BmGMwNRPsLJy2%2FF5D5mJRrYrisjdzVYy8i5cI7pxyHrBkPcFT%2BK20xIJZHiuobiLvP7%2FAkKDUZbvvRyBU%2BCWmnjQjOJ8%2FbCQ%3D%3D)

# Operating System Examples

### Windows Threads

-   Windows threads are managed through the Windows API, which implements a one-to-one mapping of user threads to kernel threads.
-   Each thread has a unique thread ID, a register set, and separate stacks for user and kernel modes, collectively known as the thread context.
-   Key data structures include `ETHREAD`, `KTHREAD`, and `TEB`, which store essential information about the thread's execution state.

### Linux Threads

-   In Linux, threads are referred to as tasks, and thread creation is accomplished using the `clone()` system call, which allows sharing of the address space between parent and child tasks.
-   The `task_struct` structure is used to manage thread data, containing pointers to process data structures that can be shared or unique.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzNzE2MjUyNTJdfQ==
-->