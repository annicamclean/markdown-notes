# Fill In The Blank

## **Chapter 4: Threads and Concurrency**

1.  A __________ (1) is the smallest sequence of programmed instructions that can be managed independently by a scheduler.
    
2.  Threads run within a __________ (2) and share the same __________ (3) space and system resources.
    
3.  __________ (4) threads are created and managed by the operating system, while __________ (5) threads are managed by a user-level library.
    
4.  The primary states of a thread are __________ (6), __________ (7), and __________ (8).
    
5.  A thread can be in the __________ (9) state while it waits for an event to occur.
    
6.  __________ (10) allows multiple threads to run simultaneously by switching between them rapidly.
    
7.  The two models for threading are __________ (11) and __________ (12).
    
8.  In the __________ (13) model, user-level threads are mapped to kernel threads.
    
9.  The __________ (14) model allows multiple user threads to be mapped to multiple kernel threads.
    
10.  The __________ (15) model is the simplest and maps each user thread to one kernel thread.
    

----------

## **Chapter 5: CPU Scheduling**

1.  The __________ (16) of a CPU determines which processes get to execute and for how long.
    
2.  CPU scheduling is necessary to maximize __________ (17) and reduce __________ (18).
    
3.  The __________ (19) queue contains all processes that are ready to run but are waiting for CPU time.
    
4.  The __________ (20) queue contains processes that are waiting for I/O operations to complete.
    
5.  __________ (21) scheduling selects from the ready queue and allocates the CPU to one of the processes.
    
6.  The four criteria for CPU scheduling are __________ (22), __________ (23), __________ (24), and __________ (25).
    
7.  The algorithm that selects the process with the smallest CPU burst time is called __________ (26).
    
8.  In the __________ (27) scheduling algorithm, each process gets a small unit of CPU time called a time slice.
    
9.  __________ (28) scheduling uses a priority number to determine which process runs next.
    
10.  __________ (29) scheduling ensures that all processes get a fair share of CPU time by rotating through the queue.
    

----------

## **Chapter 6: Synchronization**

1.  __________ (30) occurs when multiple processes or threads try to access shared resources simultaneously.
    
2.  The __________ (31) problem involves multiple threads attempting to enter their critical sections simultaneously.
    
3.  The three requirements for a correct solution to the critical-section problem are __________ (32), __________ (33), and __________ (34).
    
4.  __________ (35) is when a process is prevented from making progress because other processes are constantly accessing resources.
    
5.  __________ (36) is a technique used to solve synchronization problems by using locks or other mechanisms.
    
6.  A __________ (37) allows only one thread to access a resource at a time.
    
7.  __________ (38) provide a way to signal and wait for conditions to be met.
    
8.  A __________ (39) variable is used to allow threads to wait for specific conditions.
    
9.  The two operations associated with semaphores are __________ (40) and __________ (41).
    
10.  A __________ (42) semaphore can only have values of 0 or 1.
    

----------

## **Chapter 7: Memory Management**

1.  Memory is divided into fixed-sized blocks called __________ (43).
    
2.  The process of allocating and managing memory is known as __________ (44).
    
3.  In the __________ (45) allocation method, processes are allocated contiguous memory blocks.
    
4.  __________ (46) is the process of moving data between main memory and secondary storage.
    
5.  __________ (47) memory uses hardware and software to allow a computer to compensate for shortages of physical memory.
    
6.  A __________ (48) table keeps track of where each process's pages are located in physical memory.
    
7.  __________ (49) is when pages are moved in and out of memory too frequently, reducing performance.
    
8.  A __________ (50) algorithm selects which memory pages to remove to make space for new pages.
    
9.  The __________ (51) algorithm removes the page that has not been used for the longest period.
    
10.  __________ (52) is a memory management technique that uses multiple levels of tables to map logical addresses to physical addresses.
    

----------

## **Chapter 8: Understanding Deadlocks in Systems**

1.  A system consists of various __________ (53) that can be utilized by threads, including __________ (54) cycles, __________ (55) space, I/O devices, and __________ (56) interfaces.
    
2.  Resource types are denoted as __________ (57), where each type has a certain number of instances (__________ (58)).
    
3.  Threads interact with resources through three primary actions: __________ (59), __________ (60), and __________ (61).
    
4.  If a resource is not available when requested, the thread must __________ (62) until it can acquire it, leading to potential __________ (63) situations.
    

----------

### **Deadlock with Mutex in Pthreads**

5.  Deadlock can occur when two threads (__________ (64) and __________ (65)) attempt to lock multiple __________ (66) in an inconsistent order.
    
6.  This leads to a situation where each thread is waiting for the other to __________ (67) a mutex.
    

----------

### **Deadlock with Semaphores**

7.  Similar to mutexes, deadlocks can occur with __________ (68) when two threads attempt to acquire two semaphores (__________ (69) and __________ (70)) in a conflicting order.
    
8.  The __________ (71) operations on semaphores can lead to indefinite waiting, causing a deadlock.
    

----------

### **Deadlock Characterization**

#### **Four Necessary Conditions for Deadlock**

9.  __________ (72): Only one thread can use a resource at a time.
    
10.  __________ (73): A thread holding at least one resource is waiting to acquire additional resources.
    
11.  __________ (74): Resources cannot be forcibly taken from threads; they must be voluntarily released.
    
12.  __________ (75): A set of threads exists where each thread is waiting for a resource held by another thread in the set.
    

# Answers

## **Chapter 4: Threads and Concurrency**

1.  **Thread**
    
2.  **Process**
    
3.  **Memory**
    
4.  **Kernel, User**
    
5.  **Running**
    
6.  **Blocked, Ready, Terminated**
    
7.  **Blocked**
    
8.  **Preemptive, Non-preemptive**
    
9.  **Non-preemptive**
    
10.  **Preemptive**
    

----------

## **Chapter 5: CPU Scheduling**

16.  **Scheduling**
    
17.  **Throughput**
    
18.  **Turnaround Time**
    
19.  **Ready**
    
20.  **Blocked**
    
21.  **CPU**
    
22.  **CPU Utilization, Throughput, Turnaround Time, Waiting Time**
    
23.  **Shortest Job First (SJF)**
    
24.  **Round Robin (RR)**
    
25.  **Priority Scheduling**
    
26.  **Round Robin**
    

----------

## **Chapter 6: Synchronization**

30.  **Concurrency**
    
31.  **Critical-section**
    
32.  **Mutual Exclusion**
    
33.  **Progress**
    
34.  **Bounded Waiting**
    
35.  **Mutex**
    
36.  **Semaphore**
    
37.  **Mutex**
    
38.  **Condition**
    
39.  **Semaphore**
    
40.  **Wait**
    
41.  **Signal**
    
42.  **Binary Semaphore**
    

----------

## **Chapter 7: Memory Management**

43.  **Pages**
    
44.  **Memory Management**
    
45.  **Contiguous**
    
46.  **Paging**
    
47.  **Virtual**
    
48.  **Page Table**
    
49.  **Thrashing**
    
50.  **Page Replacement**
    
51.  **FIFO (First-In-First-Out)**
    
52.  **Multilevel Paging**
    

----------

## **Chapter 8: Understanding Deadlocks in Systems**

53.  **Resources**
    
54.  **CPU**
    
55.  **Memory**
    
56.  **Network**
    
57.  **R1, R2, ..., Rm**
    
58.  **Wi**
    
59.  **Request**
    
60.  **Use**
    
61.  **Release**
    
62.  **Wait**
    
63.  **Deadlock**
    

----------

### **Deadlock with Mutex in Pthreads**

64.  **T1**
    
65.  **T2**
    
66.  **Mutexes**
    
67.  **Release**
    

----------

### **Deadlock with Semaphores**

68.  **Semaphores**
    
69.  **S1**
    
70.  **S2**
    
71.  **Wait**
    

----------

### **Deadlock Characterization**

#### **Four Necessary Conditions for Deadlock**

72.  **Mutual Exclusion**
    
73.  **Hold and Wait**
    
74.  **No Preemption**
    
75.  **Circular Wait**
    

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgzMTE1Nzk3OCwtMTY3MTc5OTIwNiwtMT
A1MjU1NzgzXX0=
-->