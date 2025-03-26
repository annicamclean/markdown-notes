# Chapter 6 Study Guide

# FILL IN

### **Ch. 6 - Synchronization Tools and Techniques (Fill in the Blank)**

----------

### **Background and Overview**

1.  Synchronization is essential for maintaining __________ in concurrent processes.
    
2.  The __________ problem occurs when multiple processes access shared resources simultaneously, leading to race conditions.
    
3.  An example of the need for synchronization is the __________ problem, where a producer and consumer share a buffer.
    

----------

### **The Critical-Section Problem**

4.  The critical-section problem requires a protocol to manage access to __________ resources.
    
5.  A solution to this problem must satisfy three conditions: __________, __________, and __________.
    
6.  The section of code where a process accesses shared data is called the __________.
    

----------

### **Race Conditions**

7.  A __________ occurs when multiple processes access and manipulate shared data concurrently, leading to unpredictable results.
    
8.  An example of a race condition is when processes using the __________ system call compete for assigning the same process ID.
    

----------

### **Solutions to the Critical-Section Problem**

#### **Software Solutions**

9.  __________ Solution is a two-process algorithm that uses shared variables to control access to the critical section.
    
10.  It ensures __________, __________, and __________ requirements are met.
    
11.  Despite its theoretical effectiveness, Peterson’s Solution may fail on modern architectures due to __________.
    

----------

#### **Hardware Support for Synchronization**

12.  Hardware support ensures critical section code executes correctly, especially on __________ systems.
    
13.  On uniprocessor systems, disabling __________ can prevent preemption, though this is inefficient on multiprocessor systems.
    
14.  Hardware instructions like __________ and __________ are commonly used for atomic operations.
    

----------

### **Memory Barriers**

15.  Memory barriers prevent __________ by ensuring operations occur in the intended order.
    
16.  In __________ memory models, memory operations are immediately visible to all processors.
    
17.  In __________ memory models, memory operations may be delayed, requiring memory barriers to ensure correct visibility.
    

----------

### **Hardware Instructions for Synchronization**

18.  The __________ instruction atomically tests and modifies a boolean variable, commonly used to implement locks.
    
19.  The __________ instruction compares a value to an expected value and swaps it with a new value if they match.
    
20.  Both Test-and-Set and Compare-and-Swap can be used to solve the __________ problem by ensuring only one process accesses the critical section.
    

----------

### **Atomic Variables and Mutex Locks**

21.  __________ variables allow uninterruptible updates on basic data types, preventing race conditions.
    
22.  __________ locks ensure mutual exclusion by allowing only one process to access a resource at a time.
    
23.  The basic operations for mutex locks are __________ to obtain the lock and __________ to release it.
    

----------

### **Semaphores**

24.  A __________ is an integer variable used for synchronization, accessed through two atomic operations: __________ and __________.
    
25.  A __________ semaphore can take any integer value, managing multiple resources, while a __________ semaphore operates like a mutex lock with values of 0 or 1.
    
26.  Improper use of semaphores can lead to issues like __________, where processes wait indefinitely.
    

----------

### **Monitors in Synchronization**

27.  A __________ is a high-level abstraction that encapsulates shared variables and procedures to ensure mutual exclusion.
    
28.  A __________ variable within a monitor allows processes to wait until a specific condition is met.
    
29.  The __________ operation suspends a process until it is signaled, while the __________ operation resumes one waiting process.
    

----------

### **Liveness and Synchronization Issues**

30.  __________ ensures processes make progress without waiting indefinitely for resources.
    
31.  __________ occurs when processes are stuck in a circular wait, unable to proceed.
    
32.  __________ happens when a process is continually denied access to resources, often due to unfair scheduling.
    
33.  __________ occurs when a lower-priority process holds a resource needed by a higher-priority process.
    
34.  The __________ protocol can resolve this by temporarily raising the priority of the lower-priority process.
    

# ANSWER
# Background and Overview

### Introduction to Synchronization

-   Synchronization is essential for maintaining data consistency in concurrent processes.
-   Concurrent execution of processes can lead to data inconsistency if not managed properly.
-   The critical-section problem arises when multiple processes access shared resources simultaneously, leading to potential race conditions.
-   Example: The Bounded Buffer problem illustrates the need for synchronization when a producer and consumer access a shared buffer.

### The Critical-Section Problem

-   The critical-section problem involves designing a protocol to manage access to shared resources among multiple processes.
-   Each process has a critical section where it can modify shared data, and only one process can be in its critical section at a time.
-   Key requirements for a solution include mutual exclusion, progress, and bounded waiting.  


### Race Conditions

-   A race condition occurs when two or more processes access shared data and try to change it simultaneously, leading to unpredictable results.
-   Example: Processes P0 and P1 using the fork() system call can lead to a race condition on the kernel variable next_available_pid, potentially assigning the same PID to different processes.

# Solutions to the Critical-Section Problem

### Software Solutions

-   Software solutions can be implemented to manage access to critical sections without hardware support.
-   Example: Peterson’s Solution uses two shared variables (turn and flag) to control access between two processes, ensuring mutual exclusion and progress.

### Peterson’s Solution

-   Peterson’s Solution is a two-process solution that uses a turn variable and a flag array to indicate readiness to enter the critical section.
-   The algorithm ensures that only one process can enter the critical section at a time, satisfying mutual exclusion, progress, and bounded waiting requirements.

### Limitations of Software Solutions

-   While Peterson’s Solution is effective in theory, it may not work on modern architectures due to instruction reordering by compilers or processors.
-   Example: In a scenario with two threads, the output may be inconsistent if the order of operations is altered, leading to unexpected results.

# Hardware Support for Synchronization

### Overview of Hardware Solutions

-   Hardware support for synchronization is crucial for ensuring that critical section code executes correctly on modern architectures.
-   Uniprocessor systems can disable interrupts to prevent preemption, but this approach is inefficient for multiprocessor systems.

### Types of Hardware Support

-   Common forms of hardware support include memory barriers, atomic operations, and compare-and-swap instructions.
-   These hardware mechanisms help ensure that operations on shared variables are completed without interruption, maintaining data consistency.

### Memory Barriers

-   Memory barriers are used to prevent instruction reordering, ensuring that critical operations occur in the intended order.
-   They are essential for making software solutions like Peterson’s Solution work correctly on modern architectures.

# Evaluation of Synchronization Tools

### Low-Contention Scenarios

-   In low-contention scenarios, where few processes compete for resources, simpler synchronization mechanisms like mutex locks may suffice.
-   Mutex locks provide a straightforward way to ensure mutual exclusion without significant overhead.

### Moderate-Contention Scenarios

-   In moderate-contention scenarios, semaphores can be effective for managing access to shared resources among multiple processes.
-   Semaphores allow for more flexible control over resource allocation compared to mutex locks.

### High-Contention Scenarios

-   In high-contention scenarios, more sophisticated synchronization tools like monitors or condition variables may be necessary.
-   These tools provide higher-level abstractions for managing complex interactions between processes, improving efficiency and reducing the likelihood of deadlocks.

# Overview of Synchronization in Operating Systems

### Uniprocessors and Multiprocessors

-   Uniprocessors can disable interrupts, allowing currently running code to execute without preemption, which is beneficial for certain applications.
-   However, this approach is generally inefficient on multiprocessor systems due to the lack of scalability in operating systems that rely on this model.
-   Multiprocessor systems require more sophisticated synchronization mechanisms to manage concurrent processes effectively.

### Forms of Hardware Support

-   The study focuses on three forms of hardware support for synchronization: memory barriers, hardware instructions, and atomic variables.
-   Memory barriers ensure that memory operations are completed in a specific order, preventing reordering by the compiler or CPU.
-   Hardware instructions like Test-and-Set and Compare-and-Swap provide atomic operations that are crucial for implementing locks and other synchronization primitives.

# Memory Barriers

### Memory Models

-   Memory models define the visibility and ordering of memory operations across different processors.
-   Strongly ordered memory models ensure immediate visibility of changes across processors, while weakly ordered models may delay visibility.
-   Memory barriers (or fences) are instructions that enforce visibility of memory modifications, ensuring that all previous operations are completed before proceeding.

### Memory Barrier Instructions

-   When a memory barrier instruction is executed, it guarantees that all loads and stores are completed before any subsequent operations.
-   This prevents issues that arise from instruction reordering, ensuring that critical data is visible to all processors before further operations are performed.
-   Example: In a multi-threaded environment, using memory barriers can ensure that one thread sees the updates made by another thread before proceeding.

### Example of Memory Barrier Usage

-   In a scenario with two threads, Thread 1 waits for a flag to be set by Thread 2 before printing a value.
-   By adding a memory barrier, we ensure that Thread 1 reads the flag before accessing the value it needs to print.
-   This guarantees that Thread 1 outputs the correct value, demonstrating the importance of memory barriers in synchronization.

# Hardware Instructions for Synchronization

### Test-and-Set Instruction

-   The Test-and-Set instruction atomically tests and modifies a boolean variable, typically used for implementing locks.
-   Definition:
```
boolean test_and_set(boolean *target) {
    boolean rv = *target;
    *target = true;
    return rv;
}
```
-   This instruction returns the original value of the target variable and sets it to true, indicating that the lock is acquired.

### Compare-and-Swap Instruction

-   The Compare-and-Swap (CAS) instruction atomically compares a variable to an expected value and swaps it with a new value if they match.
-   Definition:
```
int compare_and_swap(int *value, int expected, int new_value) {
    int temp = *value;
    if (*value == expected) 
        *value = new_value;
    return temp;
}
```
-   This instruction is crucial for implementing more complex synchronization mechanisms, such as spinlocks.

### Solutions Using Test-and-Set and Compare-and-Swap

-   Both Test-and-Set and Compare-and-Swap can be used to solve the critical-section problem by ensuring that only one thread can access a critical section at a time.
-   Example using Test-and-Set:
```
do {
    while (test_and_set(&lock)); // busy wait
    // critical section
    lock = false; // release lock
} while (true);
```
-   Example using Compare-and-Swap:
```
while (true) {
    while (compare_and_swap(&lock, 0, 1) != 0);
    // critical section
    lock = 0; // release lock
}
```
-   Both methods require busy waiting, which can lead to inefficiencies.

# Atomic Variables and Mutex Locks

### Atomic Variables

-   Atomic variables provide a way to perform uninterruptible updates on basic data types, ensuring thread safety.
-   Example of an increment operation on an atomic variable:
```
void increment(atomic_int *v) {
    int temp;
    do {
        temp = *v;
    } while (temp != compare_and_swap(v, temp, temp + 1));
}
```
-   This ensures that the increment operation is performed atomically, preventing race conditions.

### Mutex Locks

-   Mutex locks are a simpler synchronization tool designed to protect critical sections by allowing only one thread to access a resource at a time.
-   A mutex lock is represented by a boolean variable indicating whether the lock is available.
-   The basic operations are acquire() to obtain the lock and release() to release it, both of which must be atomic.
-   Example of using a mutex lock:
```
while (true) {
    acquire_lock();
    // critical section
    release_lock();
    // remainder section
}
```
-   Mutex locks can lead to busy waiting, similar to Test-and-Set and Compare-and-Swap.

### Semaphores

-   Semaphores are a more sophisticated synchronization tool than mutex locks, allowing for more complex coordination between processes.
-   They can be used to control access to a common resource by multiple processes in a concurrent system.
-   Semaphores can be binary (similar to mutexes) or counting, allowing for a specified number of threads to access a resource simultaneously.

# Introduction to Semaphores

### Definition and Operations of Semaphores

-   A semaphore is an integer variable used for process synchronization, accessed through two atomic operations: `wait()` and `signal()`.
-   Originally named `P()` (proberen) and `V()` (verhogen), these operations control access to shared resources.
-   The `wait()` operation decrements the semaphore value and may block the process if the value is less than or equal to zero, leading to busy waiting.
-   The `signal()` operation increments the semaphore value, potentially waking up a blocked process.

### Types of Semaphores

-   ****Counting Semaphore****: Can take any integer value, allowing for multiple resources to be managed.
-   ****Binary Semaphore****: Can only be 0 or 1, functioning similarly to a mutex lock, ensuring mutual exclusion.
-   A counting semaphore can be implemented using binary semaphores, demonstrating flexibility in synchronization mechanisms.

### Semaphore Usage Example

-   In the critical section (CS) problem, a semaphore named `mutex` is initialized to 1 to control access:
```
wait(mutex);
   // Critical Section Code
signal(mutex);
```
-   For two processes P1 and P2, where S1 must precede S2, a semaphore `synch` initialized to 0 is used:
```
P1:
   S1;
   signal(synch);
P2:
   wait(synch);
   S2;
```
### Problems with Semaphores

-   Incorrect usage can lead to issues such as deadlocks, where processes wait indefinitely for each other to release resources.
-   Common mistakes include omitting `wait(mutex)` or `signal(mutex)`, leading to synchronization failures.
-   Proper understanding and implementation of semaphore operations are crucial to avoid these pitfalls.

# Implementation of Semaphores

### Semaphore Implementation with Busy Waiting

-   Semaphore operations must ensure that no two processes can execute `wait()` and `signal()` simultaneously, leading to critical section problems.
-   Busy waiting can occur if processes frequently check the semaphore state, which is inefficient for long wait times.

### Semaphore Implementation without Busy Waiting

-   Each semaphore has an associated waiting queue to manage processes that are blocked.
-   The waiting queue structure includes an integer value and a pointer to the next process in the queue:
```
typedef struct {
    int value;
    struct process *list;
} semaphore;
```
-   Operations include `block()` to suspend a process and `wakeup()` to resume a process from the waiting queue.

### Code Implementation of Semaphore Operations

-   The `wait()` operation is implemented as follows:
```
wait(semaphore *S) {
   S->value--;
   if (S->value < 0) {
      add this process to S->list;
      block();
   }
}
```
-   The `signal()` operation is implemented as:
```
signal(semaphore *S) {
   S->value++;
   if (S->value <= 0) {
      remove a process P from S->list;
      wakeup(P);
   }
}
```

# Monitors in Synchronization

### Overview of Monitors

-   Monitors provide a high-level abstraction for process synchronization, ensuring mutual exclusion by allowing only one active process at a time.
-   They encapsulate shared variables and procedures, making them accessible only within the monitor's context.

### Monitor Implementation Using Semaphores

-   A monitor uses a semaphore `mutex` initialized to 1 to control access to its procedures:

semaphore mutex;
mutex = 1;

-   Each procedure within the monitor is wrapped with `wait(mutex)` and `signal(mutex)` to ensure mutual exclusion.

### Condition Variables in Monitors

-   Condition variables allow processes to wait for certain conditions to be met before proceeding.
-   Two operations are defined: `x.wait()` suspends the process until `x.signal()` is called, which resumes one of the waiting processes.

### Example of Monitor with Condition Variables

-   In a scenario where P1 and P2 need to execute statements S1 and S2 in order, a monitor can be structured as follows:
```java
monitor ExampleMonitor {
    condition x;
    boolean done;
    void F1() {
        S1;
        done = true;
        x.signal();
    }
    void F2() {
        if (!done) x.wait();
        S2;
    }
}
```
# Liveness and Synchronization Issues

### Understanding Liveness

-   Liveness refers to the properties ensuring that processes make progress and do not wait indefinitely for resources.
-   Indefinite waiting is a violation of liveness, leading to potential deadlocks or starvation.

### Deadlock and Starvation

-   Deadlock occurs when two or more processes are waiting indefinitely for resources held by each other, creating a cycle of dependencies.
-   Starvation happens when a process is perpetually denied access to resources due to scheduling policies.

### Priority Inversion

-   Priority inversion is a scheduling issue where a lower-priority process holds a lock needed by a higher-priority process, leading to inefficiencies.
-   This can be mitigated using a priority-inheritance protocol, where the lower-priority process temporarily inherits the higher priority.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI4NDcwNjYzNF19
-->