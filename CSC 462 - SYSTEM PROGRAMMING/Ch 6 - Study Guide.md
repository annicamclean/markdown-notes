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

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI2OTc4NDk4MV19
-->