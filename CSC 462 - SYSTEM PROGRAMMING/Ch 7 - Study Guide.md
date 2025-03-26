# Chapter 7 Study Guide

# FILL IN
## **Ch. 7 - Synchronization Problems and Solutions in Operating Systems**

### **Classical Problems of Synchronization**

1.  Synchronization problems are essential in __________ programming to manage access to shared resources.
    
2.  The three classical problems include the __________ Problem, __________ Problem, and __________ Problem.
    
3.  These problems test synchronization schemes, ensure data integrity, and prevent __________.
    

----------

### **Bounded-Buffer Problem**

4.  The Bounded-Buffer Problem involves a __________ buffer managed by producer and consumer processes.
    
5.  The problem uses __________ for mutual exclusion, __________ to count filled buffers, and __________ to count available buffers.
    
6.  The __________ process waits for an empty slot before adding an item, while the __________ process waits for a filled slot before removing an item.
    
7.  This problem illustrates the __________ relationship and the need for synchronization to avoid __________ conditions.
    

----------

### **Readers-Writers Problem**

8.  The Readers-Writers Problem involves multiple processes accessing a shared __________.
    
9.  Readers can read __________, but writers require __________ access.
    
10.  To manage access, the problem uses the semaphores __________ and __________.
    
11.  A major challenge is ensuring writers do not face __________, which means they may wait indefinitely.
    

----------

### **Dining-Philosophers Problem**

12.  The Dining-Philosophers Problem models philosophers sitting at a table, alternating between __________ and __________.
    
13.  Philosophers need two __________ to eat, which can lead to __________ or starvation.
    
14.  Each philosopher uses __________ (synchronization tool) to represent chopsticks.
    
15.  A potential deadlock occurs if all philosophers pick up one chopstick __________.
    
16.  Solutions may involve introducing a __________ or limiting the number of philosophers attempting to eat.
    

----------

### **Tools for Synchronization in Operating Systems**

17.  Both __________ and __________ provide synchronization tools like semaphores, mutexes, and condition variables.
    
18.  __________ uses POSIX threads (pthreads) for synchronization, while __________ offers critical sections and events.
    
19.  Mutexes ensure __________ by preventing multiple threads from accessing a critical section at the same time.
    

----------

### **POSIX and Java for Process Synchronization**

20.  __________ provides a standardized API for synchronization in Unix-like systems.
    
21.  In Java, the __________ keyword and the __________ package offer built-in synchronization.
    
22.  The __________ class in Java provides more flexible locking mechanisms.
    

----------

### **Dining Philosophers Monitor Solution**

23.  A __________ is a synchronization construct that encapsulates shared data and operations.
    
24.  The monitor solution uses states represented as __________, __________, and __________.
    
25.  The philosopher's state is set to __________ when they are ready to eat, and the state is checked using the __________ method.
    
26.  The __________ method changes the state back to THINKING and allows neighboring philosophers to proceed.
    

----------

### **Kernel Synchronization**

27.  __________ uses interrupt masks in uniprocessor systems and __________ in multiprocessor systems for synchronization.
    
28.  In Linux, spinlocks are often replaced by enabling/disabling __________ to manage critical sections.
    
29.  __________ semaphores can be named (shared across processes) or unnamed (local to a process).
    

----------

### **Java Synchronization Features**

30.  In Java, every object has an associated __________ used for synchronization.
    
31.  The __________ method in Java releases the lock and puts the thread in a wait state.
    
32.  The __________ clause ensures locks are released even if exceptions occur.
    

----------

### **Alternative Synchronization Approaches**

33.  __________ memory allows operations to be executed atomically using the `atomic{}` construct.
    
34.  __________ is a set of compiler directives and APIs supporting parallel programming using the `#pragma omp critical` directive.
    
35.  __________ programming languages like Erlang and Scala reduce data races by treating variables as __________.
# ANSWER
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjMxMjUxODgxXX0=
-->