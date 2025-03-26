
# Fill In The Blank
## Ch. 4 Overview of Threads and Concurrency

### Basic Components of Threads

Threads are the smallest unit of processing that can be scheduled by an ________, consisting of a thread ID, ________, register set, and stack.

Threads share the same ________ space of their parent process, allowing for efficient communication and resource sharing.

Contrast with processes: processes have separate ________ spaces, making inter-process communication more complex and resource-intensive.

Threads can be created and managed more efficiently than ________, leading to lower overhead in context switching.

Example: In a web server, each request can be handled by a separate ________, allowing multiple requests to be processed simultaneously.

### Benefits and Challenges of Multithreading

Benefits include improved ________, as threads can continue executing while others are blocked, crucial for user interfaces.

________ sharing among threads is easier than managing shared memory or message passing, leading to simpler code.

Thread creation is less resource-intensive than ________ creation, making it economical for applications that require frequent task switching.

________ is enhanced as applications can leverage multicore architectures to run multiple threads in parallel, improving performance.

Challenges include complexity in design, potential for ________ conditions, and difficulties in debugging multithreaded applications.

### Multicore Programming

#### Understanding Multicore Systems

Multicore systems allow multiple threads to run ________, increasing the potential for parallelism in applications.

Programmers face challenges such as dividing tasks effectively, balancing ________, and managing data dependencies.

Testing and debugging become more complex due to the non-________ nature of thread execution in multicore environments.

Example: A video processing application can split ________ across multiple cores for faster processing.

### Concurrency vs. Parallelism

Concurrency refers to the ability of a system to manage multiple tasks at once, while ________ involves executing multiple tasks simultaneously.

On a single-core system, concurrency is achieved through ________, where the CPU switches between tasks rapidly.

On a multicore system, ________ allows multiple threads to run at the same time, improving performance significantly.

### Threading Models and Libraries

#### User Threads vs. Kernel Threads

________ threads are managed by user-level libraries, allowing for flexibility but limited by the kernel's scheduling.

________ threads are managed by the operating system, providing better concurrency and resource management.

Examples of user-level thread libraries include ________ Pthreads, Windows threads, and Java threads, while kernel threads are supported by most modern operating systems.

#### Multithreading Models

-   **Many-to-One:** Multiple user threads mapped to a single ________ thread; blocking one thread blocks all.
    
-   **One-to-One:** Each user thread corresponds to a ________ thread, allowing for greater concurrency but with overhead.
    
-   **Many-to-Many:** Multiple user threads can be mapped to multiple ________ threads, providing flexibility and efficiency.
    

### Implicit Threading and Thread Libraries

#### Implicit Threading Approaches

Implicit threading simplifies thread management by allowing ________ and runtime libraries to handle thread creation and scheduling.

Common methods include thread pools, ________-join, OpenMP, Grand Central Dispatch, and Intel Threading Building Blocks.

Example: ________ pools maintain a set of threads that can be reused for multiple tasks, reducing the overhead of thread creation.

### Thread Libraries Overview

Thread libraries provide ________ for creating and managing threads, with implementations varying between user space and kernel space.

________ is a widely used POSIX standard for thread management in UNIX-like systems, offering a robust API for synchronization and thread control.

Java threads are managed by the ________, allowing for cross-platform thread management and providing the ________ framework for easier thread handling.

### Fork-Join Parallelism

#### Overview of Fork-Join Parallelism

Fork-Join Parallelism is a computational model that divides tasks into ________, which can be executed in parallel, and then combines the results. This model is particularly effective for recursive algorithms.

The general algorithm involves two main steps: ________ (splitting tasks) and ________ (combining results).

This model is widely used in parallel programming to optimize performance on multi-core processors.

#### Fork-Join Parallelism in Java

In Java, the ________ is an abstract base class that provides the framework for implementing fork-join parallelism.

Two primary subclasses of ForkJoinTask are ________ (which returns a result) and ________ (which does not return a result).

The ________ method is overridden in these subclasses to define the task's logic, allowing for recursive decomposition of the problem.

### OpenMP and Parallel Programming

#### Introduction to OpenMP

________ is a set of compiler directives and an API designed for parallel programming in shared-memory environments, primarily for C, C++, and FORTRAN.

It allows developers to identify ________ regions in code, enabling concurrent execution of code blocks.

The directive **#pragma omp parallel** is used to create threads equal to the number of available ________.

#### Parallel Loops in OpenMP

OpenMP provides constructs to run loops in parallel, significantly improving performance for large iterations.

The **#pragma omp for** directive can be used to parallelize ________ loops, distributing iterations among threads.

### Grand Central Dispatch (GCD)

#### Overview of GCD

Grand Central Dispatch is a technology developed by ________ for macOS and iOS that simplifies concurrent programming.

It provides an API and runtime library that allows developers to identify parallel sections of code and manage ________ details automatically.

#### Dispatch Queues in GCD

GCD utilizes two types of dispatch queues: ________ (FIFO order, one block at a time) and ________ (multiple blocks can be executed simultaneously).

System-wide queues are categorized by quality of service (QoS), including user-________, user-initiated, user-utility, and user-background.

### Threading Issues and Concepts

#### Thread Cancellation

Thread cancellation refers to terminating a thread before it has completed its execution, which can be done either ________ or deferred.

In Pthreads, cancellation can be requested using ________, and the thread must reach a ________ point to be terminated.

#### Thread-Local Storage (TLS)

Thread-local storage allows each thread to maintain its own copy of data, which is crucial in multi-threaded applications to avoid data corruption.

TLS is different from ________ variables, as it persists across function invocations and is unique to each thread.

In C, TLS can be declared using the **________** keyword, allowing for thread-specific data management.

### Operating System Examples

#### Windows Threads

Windows threads are managed through the Windows API, which implements a ________ mapping of user threads to kernel threads.

Each thread has a unique thread ID, a register set, and separate stacks for user and kernel modes, collectively known as the thread ________.

Key data structures include ETHREAD, KTHREAD, and ________, which store essential information about the thread's execution state.

#### Linux Threads

In Linux, threads are referred to as ________, and thread creation is accomplished using the ________ system call, which allows sharing of the address space between parent and child tasks.

The **________** structure is used to manage thread data, containing pointers to process data structures that can be shared or unique.


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNTI1NTc4M119
-->