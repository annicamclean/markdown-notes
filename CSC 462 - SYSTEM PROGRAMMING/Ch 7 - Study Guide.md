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
# Classical Problems of Synchronization

### Overview of Synchronization Problems

-   Synchronization problems are essential in concurrent programming to manage access to shared resources.
-   They help in testing newly proposed synchronization schemes.
-   The three classical problems include: Bounded-Buffer Problem, Readers-Writers Problem, and Dining-Philosophers Problem.
-   Each problem presents unique challenges in ensuring data integrity and preventing deadlock.
-   Understanding these problems is crucial for developing efficient synchronization mechanisms.

### Bounded-Buffer Problem

-   Involves a fixed-size buffer that can hold a limited number of items, managed by producer and consumer processes.
-   Utilizes semaphores: `mutex` for mutual exclusion, `full` to count filled buffers, and `empty` to count available buffers.
-   The producer process waits for an empty slot before adding an item and signals when an item is added.
-   The consumer process waits for a filled slot before removing an item and signals when an item is consumed.
-   This problem illustrates the producer-consumer relationship and the need for synchronization to avoid race conditions.

### Readers-Writers Problem

-   Involves multiple processes accessing a shared data set, where readers can read simultaneously but writers require exclusive access.
-   The challenge is to allow multiple readers while ensuring that writers do not face starvation.
-   Semaphores `rw_mutex` and `mutex` are used to manage access and count active readers.
-   The writer process waits for exclusive access, while the reader process increments a count to manage concurrent access.
-   Variations of this problem address issues like starvation and priority between readers and writers.

### Dining-Philosophers Problem

-   A classic synchronization problem where philosophers alternate between thinking and eating, requiring two chopsticks to eat.
-   The challenge is to prevent deadlock and ensure that all philosophers can eat without starvation.
-   Each philosopher must acquire two chopsticks (semaphores) to eat, leading to potential conflicts.
-   The algorithm involves waiting for chopsticks, eating, and then releasing them, but can lead to deadlock if all philosophers pick up one chopstick simultaneously.
-   Solutions often involve introducing a hierarchy or limiting the number of philosophers that can attempt to eat at the same time.

# Tools for Synchronization in Operating Systems

### Synchronization Tools in Linux and Windows

-   Both Linux and Windows provide various synchronization primitives to manage concurrent processes.
-   Common tools include semaphores, mutexes, and condition variables.
-   Linux uses POSIX threads (pthreads) for thread management and synchronization.
-   Windows provides critical sections and events for synchronization, which are easier to use than semaphores in many cases.
-   Understanding these tools is essential for developing robust multi-threaded applications.  
    ![This code snippet shows how to include the pthreads library, declare a mutex variable, and initialize it using `pthread_mutex_init`.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/82b0429f-65fc-4257-948b-e4977f1beab4/images/6e835f50a5cc4b669647fb7f3f1d9870.jpg?Expires=1743599952&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=WN8CarBcIrMLO%2Fq3SUYKHFqoVDmjeLBdU9b0lckh7QRPxukZsRoBMNh2GfEoJUCfgR3OvVWKoBbOd1FCunpuXb7rTXcaGF3QbbCWnJrMDFw6uDjUdwXIPKcchS6%2BMZGHW8cM6xE%2BzO52yfruSXyj1CE0S3Vz%2BFQf70x%2BABZTFXjRxMrpOiv7Mef%2BNnsLkzEJfZCmnu6VtMlaLKRA2CgGoR1uYZWnI9SN7IZCmxMCIoZxoFhBZ9qk7ZOlb6vpC2jM%2B1Ljovk7pLsa6g4rNaEYsv5MyzDEbsGb4AydkiWqzKLjZgAgdQEpcuo41mEka8iWTKnmBasBkFa0Je7032GZiQ%3D%3D)![This code snippet demonstrates acquiring a mutex lock using `pthread_mutex_lock`, executing a critical section, and releasing the lock using `pthread_mutex_unlock`.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/82b0429f-65fc-4257-948b-e4977f1beab4/images/1afde591d93a43509a52562e13867261.jpg?Expires=1743599952&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=O0akXvHxE4TBWH3FJhXcN6s2%2BVEnUdlKjPvkep236msyl8ZlpZR2YnCcn8NeUAH0FE7kNZ3FkKWLgQ725oe6YGC%2Flle2oKMDIbcjJD6qjuTkVqAD4gotxcWhzweHgUCbMzcJRG2lEJLQ2vPdRHvTZPcgWtWSv%2FKy%2BqUnIh2IBhjNfEbRk4%2FqZC9qYZISuFszuG%2B0gNCc%2FcO7DJOKGP9AUbouIye%2B%2BA1R4CDllaR7lo0KrHyUYcZPpzJ37zrE%2BBZRulFuGQ5WOYvPsaMYOrUmVYs2DCexoHAc6%2BDoTidYLdS1JDuqXkKl9KM7d2fOPP70HXc%2F%2Bq0%2BqQyGVA%2FJ%2F8Rxkg%3D%3D)

### POSIX and Java for Process Synchronization

-   POSIX provides a standardized API for thread management and synchronization in Unix-like systems.
-   Java offers built-in synchronization mechanisms through the `synchronized` keyword and `java.util.concurrent` package.
-   Both POSIX and Java allow developers to implement synchronization strategies effectively, reducing the risk of race conditions.
-   Examples include using `ReentrantLock` in Java for more flexible locking mechanisms compared to traditional synchronized methods.
-   Understanding these frameworks is crucial for cross-platform application development.  
    ![This image shows Java code demonstrating the use of a `ReentrantLock` to protect a critical section, ensuring that the `unlock()` method is always called, even if exceptions occur.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/82b0429f-65fc-4257-948b-e4977f1beab4/images/87fd63dbafd345938a65378b6baf2744.jpg?Expires=1743599952&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=YWroephaa7Dd6QbSNPtuYdlCkQWnaf6lFkbibDHzSJ2DRQWkQKO4iRpX3O6Ti8ZQl8uf%2FulacNnBcsh3lSJOI2faFchtpnwibfP3tWyFZTcLnpM1W6Zo87IfNEtMb9C6xToblqE%2FLYI7gXrAK1XBJeC3j302ksn5beuXMtL6T749xd2K0tkJXL4W6AOSMrfw6gk8cnsCffaemXB9n%2BMfDC969P%2BMAiFoJaOD4jT4QO3Dh8fBtK2kwJOZfWporu%2Bbk1TXjAMumFMuFJropDfc7pBonqNVwal0IdfU2au046rjTA0qce%2BnJMzG0nywOhwxA2H%2FEBZKvgr8CYR%2BYGBFoA%3D%3D)

# 1. Dining Philosophers Problem

### 1.1 Overview of the Problem

-   The Dining Philosophers problem is a classic synchronization problem that illustrates the challenges of resource sharing among multiple processes.
-   It involves five philosophers sitting at a table, each needing two forks to eat, leading to potential deadlock and starvation scenarios.
-   The problem is used to demonstrate the importance of proper synchronization mechanisms in concurrent programming.

### 1.2 Monitor Solution

-   A monitor is a synchronization construct that allows safe access to shared resources by encapsulating the shared data and the operations that manipulate it.
-   The monitor for the Dining Philosophers includes an enumeration for states (THINKING, HUNGRY, EATING) and condition variables for each philosopher.
-   The `pickup` method sets the philosopher's state to HUNGRY and checks if they can eat; if not, they wait on their condition variable.

### 1.3 Code Explanation

```c  
monitor DiningPhilosophers {  
enum {THINKING, HUNGRY, EATING} state[5];  
condition self[5];  
void pickup(int i) {  
state[i] = HUNGRY;  
test(i);  
if (state[i] != EATING) self[i].wait;  
}  
void putdown(int i) {  
state[i] = THINKING;  
test((i + 4) % 5);  
test((i + 1) % 5);  
}  
void test(int i) {  
if ((state[(i + 4) % 5] != EATING) && (state[i] == HUNGRY) && (state[(i + 1) % 5] != EATING)) {  
state[i] = EATING;  
self[i].signal();  
}  
}  
initialization_code() {  
for (int i = 0; i < 5; i++) state[i] = THINKING;  
}  
}```

-   The `putdown` method signals neighboring philosophers to check if they can eat after a philosopher finishes.

### 1.4 Key Takeaways

-   The solution prevents deadlock but does not eliminate starvation, as a philosopher may wait indefinitely if neighbors are continuously hungry.
-   The monitor encapsulates the synchronization logic, making it easier to manage concurrent access to shared resources.

# 2. Kernel Synchronization

### 2.1 Windows Kernel Synchronization

-   Windows uses interrupt masks to protect global resources in uniprocessor systems and spinlocks in multiprocessor systems.
-   Spinlocks prevent thread preemption, ensuring that a thread holds the lock until it completes its critical section.
-   Dispatcher objects in Windows can act as mutexes, semaphores, events, and timers, facilitating synchronization.  
    

### 2.2 Linux Kernel Synchronization

-   Prior to kernel version 2.6, Linux disabled interrupts for short critical sections; post-2.6, it became fully preemptive.
-   Linux provides various synchronization primitives including semaphores, atomic integers, and spinlocks, with reader-writer versions available.
-   On single-CPU systems, spinlocks are replaced by enabling/disabling kernel preemption to manage critical sections.

### 2.3 POSIX Synchronization

-   POSIX API offers mutex locks, semaphores, and condition variables, widely used in UNIX, Linux, and macOS environments.
-   Mutex locks are initialized, acquired, and released to ensure mutual exclusion in concurrent programming.
-   POSIX semaphores can be named (accessible by unrelated processes) or unnamed (local to a process).

### 2.4 Key Comparisons
|  |  | 
|--|--|
|  |  |


Feature

Windows

Linux

POSIX

Mutex Support

Yes

Yes

Yes

Semaphore Types

Events, Mutexes

Semaphores, Atomic Integers

Named, Unnamed Semaphores

Condition Variables

Yes

Yes

Yes

# 3. Java Synchronization

### 3.1 Java Synchronization Features

-   Java provides a rich set of synchronization features including monitors, reentrant locks, semaphores, and condition variables.
-   Every Java object has an associated lock; synchronized methods require the calling thread to own the lock before execution.
-   The `wait()` method releases the lock and places the thread in a wait state until notified.

### 3.2 Bounded Buffer Example

-   In a bounded buffer scenario, threads must wait for their turn to access shared resources, ensuring mutual exclusion and preventing race conditions.
-   The shared variable `turn` indicates which thread can proceed, and threads notify each other upon completion of their tasks.

### 3.3 Java Reentrant Locks

-   Reentrant locks allow a thread to acquire the same lock multiple times without causing a deadlock.
-   The `finally` clause in Java ensures that locks are released even if an exception occurs during execution, maintaining resource integrity.

### 3.4 Java Condition Variables

-   Condition variables in Java are associated with reentrant locks, allowing threads to wait for specific conditions to be met before proceeding.
-   A thread can signal another waiting thread using the `signal()` method, moving it from the wait set to the entry set.

# 4. Alternative Synchronization Approaches

### 4.1 Transactional Memory

-   Transactional memory allows a sequence of read-write operations to be executed atomically, simplifying synchronization.
-   The `atomic{S}` construct ensures that statements within S are executed without interruption, providing a higher-level abstraction for concurrency.  


### 4.2 OpenMP

-   OpenMP is a set of compiler directives and APIs that support parallel programming, allowing developers to specify parallel regions in their code.
-   The `#pragma omp critical` directive ensures that the enclosed code block is executed by only one thread at a time, preventing race conditions.  

### 4.3 Functional Programming Languages

-   Functional programming languages, such as Erlang and Scala, treat variables as immutable, reducing the complexity of state management in concurrent applications.
-   The lack of mutable state in functional languages minimizes data races, making them suitable for concurrent programming.  

    
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc4NDc4MDc3OCwyMzEyNTE4ODFdfQ==
-->