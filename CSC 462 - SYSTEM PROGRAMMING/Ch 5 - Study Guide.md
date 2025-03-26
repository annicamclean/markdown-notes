# Chapter 5 Study Guide

# FILL IN

### **Ch. 5 - Basic Concepts of CPU Scheduling (Fill in the Blank)**

----------

### **Overview of CPU Scheduling**

CPU scheduling is a mechanism used by the __________ to allocate __________ resources to processes, maximizing CPU utilization and improving overall system performance.  
It is a fundamental aspect of __________ operating systems, allowing multiple processes to share CPU time effectively.  
__________ switching is a key concept, where the OS switches the CPU core among processes to manage execution efficiently.

----------

### **CPU-I/O Burst Cycle**

Process execution consists of alternating cycles of __________ execution and __________ wait, known as the CPU-I/O burst cycle.  
__________ processes typically have a large number of short CPU bursts, while __________ processes have fewer, longer bursts.  
Understanding the distribution of CPU bursts is crucial for effective __________.

----------

### **CPU Scheduler Functionality**

The CPU scheduler selects processes from the __________ queue to allocate CPU time, making decisions based on process states.  
Scheduling decisions occur during state transitions: when a process switches from running to __________, running to __________, waiting to __________, or __________.  
Situations __________ (running to waiting) and __________ (termination) require immediate scheduling, while situations __________ and __________ allow for choice.

----------

### **Preemptive vs Nonpreemptive Scheduling**

__________ scheduling occurs when the CPU is allocated to a process until it terminates or switches to waiting, while __________ scheduling allows the OS to interrupt a running process.  
Most modern operating systems, including __________, __________, and __________, use preemptive scheduling.  
Preemptive scheduling can lead to __________ conditions, where shared data is accessed inconsistently by multiple processes.

----------

### **Scheduling Criteria and Optimization**

-   **CPU Utilization**: The goal is to keep the CPU as busy as possible, ideally between __________% and __________% utilization.
    
-   **Throughput**: Measures the number of __________ completed per time unit.
    
-   **Turnaround Time**: Total time taken to execute a process, including __________, __________, and __________ time.
    
-   **Waiting Time**: Time a process spends waiting in the __________ queue before execution begins.
    
-   **Response Time**: Time from request submission to the first __________, critical for __________ systems.
    

----------

### **CPU Scheduling Algorithms**

-   **First-Come, First-Served (FCFS)**:  
    FCFS is the simplest scheduling algorithm where processes are executed in the order they __________.  
    The __________ effect occurs when short processes are stuck behind long processes, impacting performance.
    
-   **Shortest-Job-First (SJF)**:  
    SJF schedules processes based on the length of their next __________.  
    The preemptive version, __________, allows interruption of longer processes if a shorter one arrives.
    
-   **Round Robin (RR)**:  
    RR allocates a fixed __________ to each process, cycling through the ready queue to ensure fairness.  
    This algorithm is effective for __________ systems.
    

----------

### **Real-Time CPU Scheduling**

-   Real-time scheduling is crucial for systems that require __________ processing.
    
-   Algorithms ensure critical tasks meet their __________ using priority-based scheduling.
    
-   Examples include embedded systems and __________ applications.
    

----------

### **Operating Systems Examples**

-   **Windows**: Utilizes a __________-based scheduling algorithm for multitasking.
    
-   **Linux**: Employs a __________ scheduler (CFS) that ensures fair CPU time distribution.
    
-   **Solaris**: Combines __________-based and __________ scheduling.
    

----------

### **Time Quantum and Context Switching**

-   The __________ is the fixed time slice allocated to each process in RR scheduling.
    
-   Large time quantum leads to __________ behavior, while a small time quantum leads to __________ scheduling.
    
-   The time quantum should be larger than the __________ switch time to avoid excessive overhead.
    

----------

### **Thread Scheduling**

-   **User-Level Threads**: Managed by a __________ library.
    
-   **Kernel-Level Threads**: Managed by the __________.
    
-   **Process-Contention Scope (PCS)**: Scheduling competition within a __________.
    
-   **System-Contention Scope (SCS)**: Competition among all __________ in the system.
    

----------

### **Multiple-Processor Scheduling**

-   Scheduling becomes more complex with multiple CPUs, requiring efficient __________ balancing.
    
-   **Symmetric Multiprocessing (SMP)**: Each processor __________ schedules tasks.
    
-   **Load Balancing**: Techniques like __________ and __________ migration distribute workloads evenly.
    
-   **Processor Affinity**: Refers to a thread’s tendency to run on the same processor for better __________ utilization.
    

----------

### **Types of Latencies Affecting Performance**

-   **Interrupt Latency**: Time from interrupt signal arrival to the start of the __________.
    
-   **Dispatch Latency**: Time required for the scheduler to switch from the current process to a __________.

# ANSWER

# Basic Concepts of CPU Scheduling

### Overview of CPU Scheduling

-   CPU scheduling is a mechanism used by the operating system (OS) to allocate CPU resources to processes, maximizing CPU utilization and improving overall system performance.
-   It is a fundamental aspect of multiprogrammed operating systems, allowing multiple processes to share CPU time effectively.
-   Context switching is a key concept, where the OS switches the CPU core among processes to manage execution efficiently.

### CPU-I/O Burst Cycle

-   Process execution consists of alternating cycles of CPU execution and I/O wait, known as the CPU-I/O burst cycle.
-   I/O-bound processes typically have a large number of short CPU bursts, while CPU-bound processes have fewer, longer bursts.
-   Understanding the distribution of CPU bursts is crucial for effective scheduling.  
    

### CPU Scheduler Functionality

-   The CPU scheduler selects processes from the ready queue to allocate CPU time, making decisions based on process states.
-   Scheduling decisions occur during state transitions: when a process switches from running to waiting, running to ready, waiting to ready, or terminates.
-   Situations 1 (running to waiting) and 4 (termination) require immediate scheduling, while situations 2 and 3 allow for choice.

### Preemptive vs Nonpreemptive Scheduling

-   Nonpreemptive scheduling occurs when the CPU is allocated to a process until it terminates or switches to waiting, while preemptive scheduling allows the OS to interrupt a running process.
-   Most modern operating systems (Windows, Linux, MacOS) use preemptive scheduling to enhance responsiveness and resource management.
-   Preemptive scheduling can lead to race conditions, where shared data is accessed inconsistently by multiple processes.

# Scheduling Criteria and Optimization

### Key Scheduling Criteria

-   ****CPU Utilization****: The goal is to keep the CPU as busy as possible, ideally between 40% and 90% utilization.
-   ****Throughput****: Measures the number of processes completed per time unit, with short transactions yielding higher throughput.
-   ****Turnaround Time****: Total time taken to execute a process, including waiting, execution, and I/O time.
-   ****Waiting Time****: Time a process spends waiting in the ready queue before execution begins.
-   ****Response Time****: Time from request submission to the first response, critical for interactive systems.

### Optimization Criteria for Scheduling Algorithms

-   The primary goals of scheduling algorithms include maximizing CPU utilization and throughput while minimizing turnaround time, waiting time, and response time.
-   Effective scheduling algorithms balance these criteria to enhance overall system performance and user experience.

# CPU Scheduling Algorithms

### Overview of Scheduling Algorithms

-   Various CPU scheduling algorithms exist, each with unique advantages and disadvantages, including:
-   -   First-Come, First-Served (FCFS)
    -   Shortest-Job-First (SJF)
    -   Round-Robin (RR)
    -   Priority Scheduling
    -   Multilevel Queue Scheduling
    -   Multilevel Feedback Queue Scheduling

### First-Come, First-Served (FCFS) Scheduling

-   FCFS is the simplest scheduling algorithm where processes are executed in the order they arrive in the ready queue.
-   Example: For processes P1 (24), P2 (3), P3 (3), the Gantt chart shows waiting times of 0, 24, and 27 respectively, leading to an average waiting time of 17.
-   The convoy effect occurs when short processes are stuck behind long processes, negatively impacting performance.

### Shortest-Job-First (SJF) Scheduling

-   SJF schedules processes based on the length of their next CPU burst, aiming to minimize average waiting time.
-   The preemptive version, Shortest-Remaining-Time-First (SRTF), allows for interruption of longer processes if a shorter one arrives.
-   Example: For processes P1 (6), P2 (8), P3 (7), P4 (3), the average waiting time is calculated as 7.

### Round Robin (RR) Scheduling

-   RR allocates a fixed time quantum (q) to each process, cycling through the ready queue to ensure fairness.
-   Each process receives CPU time in chunks, with no process waiting more than (n - 1)q time units, where n is the number of processes.
-   This method is particularly effective for time-sharing systems, balancing responsiveness and CPU utilization.

# Real-Time CPU Scheduling

### Real-Time Scheduling Algorithms

-   Real-time scheduling is critical for systems that require timely processing, such as embedded systems and multimedia applications.
-   Algorithms must ensure that critical tasks meet their deadlines, often using priority-based scheduling.

# Operating Systems Examples

### Scheduling in Different Operating Systems

-   ****Windows****: Utilizes a preemptive priority-based scheduling algorithm, allowing for efficient multitasking and responsiveness.
-   ****Linux****: Employs a completely fair scheduler (CFS) that aims to provide fair CPU time to all processes while maintaining high throughput.
-   ****Solaris****: Implements a combination of priority-based and time-sharing scheduling, optimizing for both interactive and batch processes.  
    

# Overview of CPU Scheduling

### Introduction to CPU Scheduling

-   CPU scheduling is the method by which an operating system decides which process runs at a given time.
-   It is crucial for optimizing CPU utilization and ensuring efficient process management.
-   Scheduling algorithms can be classified into preemptive and non-preemptive categories.
-   The choice of scheduling algorithm affects system performance, turnaround time, and response time.
-   Key metrics for evaluating scheduling algorithms include turnaround time, waiting time, and response time.

### Time Quantum and Context Switching

-   The time quantum (q) is the fixed time slice allocated to each process in round-robin scheduling.
-   A large time quantum leads to First-Come, First-Served (FCFS) behavior, while a small quantum leads to Round Robin (RR) scheduling.
-   The time quantum must be larger than the context switch time to avoid excessive overhead.
-   Typical values for q range from 10 milliseconds to 100 milliseconds, while context switch time is usually less than 10 microseconds.
-   An optimal time quantum ensures that 80% of CPU bursts are shorter than q, improving overall system performance.

# Scheduling Algorithms

### Round Robin Scheduling

-   Round Robin (RR) is a preemptive scheduling algorithm that assigns a fixed time quantum to each process.
-   Example: For processes P1 (24), P2 (3), and P3 (3) with a time quantum of 4, the Gantt chart illustrates the execution order and time allocation.
-   RR typically results in higher average turnaround time compared to Shortest Job First (SJF) but offers better response times.
-   The Gantt chart for RR helps visualize the scheduling process and time allocation for each process.

### Priority Scheduling

-   In priority scheduling, each process is assigned a priority number, with lower numbers indicating higher priority.
-   The CPU is allocated to the process with the highest priority, which can be either preemptive or non-preemptive.
-   SJF can be viewed as a priority scheduling algorithm where priority is inversely related to the predicted CPU burst time.
-   A significant issue with priority scheduling is starvation, where low-priority processes may never execute.
-   Aging is a solution to starvation, where the priority of a process increases over time to ensure it eventually gets CPU time.

### Priority-Based Scheduling

-   Priority-based scheduling is essential for real-time systems, where tasks are assigned priorities based on their urgency and importance.
-   Soft real-time systems guarantee that high-priority tasks will be serviced more frequently, while hard real-time systems must meet strict deadlines.
-   Characteristics of periodic tasks include a processing time (t), a deadline (d), and a period (p), with the relationship 0 ≤ t ≤ d ≤ p.
-   The rate of a periodic task is defined as 1/p, indicating how often the task requires CPU time.
-   Example: A periodic task that requires 10ms of CPU time every 100ms has a period of 100ms and a rate of 0.01.

### Rate Monotonic Scheduling (RMS)

-   RMS assigns priorities based on the inverse of the task's period; shorter periods receive higher priorities, while longer periods receive lower priorities.
-   Example: If task P1 has a period of 50ms and task P2 has a period of 100ms, P1 is assigned a higher priority than P2 due to its shorter period.
-   The rationale behind RMS is to ensure that tasks that require the CPU more frequently are prioritized, thus improving system responsiveness.
-   RMS is optimal for periodic tasks under certain conditions, but can lead to missed deadlines if not managed properly.
-   Historical context: RMS was one of the first algorithms developed for real-time scheduling, providing a foundation for later algorithms.

# Advanced Scheduling Techniques

### Multilevel Queue Scheduling

-   Multilevel queue scheduling involves multiple queues, each with its own scheduling algorithm and priority.
-   Processes are assigned to different queues based on their characteristics, such as priority or type.
-   The scheduler selects processes from the highest-priority queue first, ensuring efficient resource allocation.
-   This method can lead to improved performance by segregating processes based on their needs and priorities.

### Multilevel Feedback Queue Scheduling

-   Multilevel feedback queues allow processes to move between different queues based on their behavior and requirements.
-   Parameters include the number of queues, scheduling algorithms for each queue, and methods for upgrading or demoting processes.
-   Aging can be implemented to prevent starvation in this model, ensuring that all processes receive CPU time eventually.
-   Example: A process starts in Q0 with RR and time quantum of 8 ms, moves to Q1 if not completed, and finally to Q2 if still incomplete.

# Thread Scheduling

### User-Level vs Kernel-Level Threads

-   User-level threads are managed by a user-level thread library, while kernel-level threads are managed by the operating system.
-   Many-to-one and many-to-many models describe how user-level threads are scheduled on kernel threads.
-   Process-contention scope (PCS) refers to scheduling competition within a process, while system-contention scope (SCS) refers to competition among all threads in the system.
-   Thread scheduling can be influenced by the programmer's priority settings, affecting overall system performance.

### Pthread Scheduling API

-   The Pthread library allows for specifying scheduling scope during thread creation, either PCS or SCS.
-   Example code demonstrates how to set the scheduling scope and create threads using the Pthread API.
-   The API provides functions to get and set thread attributes, allowing for flexible thread management.
-   Understanding the Pthread API is essential for effective thread scheduling in multi-threaded applications.

# Multiple-Processor Scheduling

### Complexity of Multiple-Processor Scheduling

-   Scheduling becomes more complex with multiple CPUs, requiring efficient load balancing and resource allocation.
-   Symmetric multiprocessing (SMP) allows each processor to self-schedule, potentially using a common ready queue or private queues.
-   Load balancing techniques, such as push and pull migration, help distribute workloads evenly across processors.
-   Processor affinity refers to the tendency of a thread to run on the same processor to take advantage of cached data.

### Real-Time CPU Scheduling

-   Real-time systems require tasks to be completed by specific deadlines to avoid significant losses.
-   Soft real-time systems prioritize critical tasks but do not guarantee scheduling, while hard real-time systems must meet deadlines without fail.
-   Event latency is a critical metric in real-time scheduling, measuring the time from event occurrence to servicing.
-   Effective real-time scheduling is essential for applications where timing is crucial, such as embedded systems.

# Types of Latencies Affecting Performance

### Interrupt Latency

-   Interrupt latency refers to the time taken from the arrival of an interrupt signal to the initiation of the routine that services that interrupt. This latency can significantly impact the responsiveness of a system, especially in real-time applications.
-   Factors affecting interrupt latency include the current state of the CPU, the priority of the interrupt, and the presence of other interrupts.
-   Example: In a real-time operating system, a high interrupt latency can lead to missed deadlines for critical tasks, such as in medical devices or automotive systems.
-   Techniques to minimize interrupt latency include optimizing interrupt handling routines and using hardware features like interrupt coalescing.
-   Historical context: Early operating systems had high interrupt latencies due to inefficient handling mechanisms, which have since improved with advancements in hardware and software design.

### Dispatch Latency

-   Dispatch latency is defined as the time required for the scheduler to take the current process off the CPU and switch to another process. This latency is crucial for the overall performance of multitasking systems.
-   The conflict phase of dispatch latency can occur when a high-priority process is waiting for resources held by a low-priority process, leading to potential delays.
-   Example: In a system where a low-priority process holds a lock needed by a high-priority process, the high-priority process may experience increased dispatch latency, affecting its performance.
-   Strategies to reduce dispatch latency include using priority inheritance protocols and optimizing the scheduling algorithm.
-   Historical context: The evolution of scheduling algorithms has aimed to reduce dispatch latency, particularly in real-time systems where timing is critical.

# Real-Time Scheduling Techniques

### Earliest Deadline First (EDF) Scheduling

-   EDF assigns priorities based on the deadlines of tasks; the earlier the deadline, the higher the priority assigned to the task.
-   This dynamic scheduling approach allows for more flexibility compared to static priority scheduling methods like RMS.
-   Example: If two tasks have deadlines of 30ms and 50ms, the task with the 30ms deadline will be prioritized, regardless of their periods.
-   EDF can theoretically achieve 100% CPU utilization for periodic tasks, making it a powerful scheduling strategy for real-time systems.
-   Historical context: EDF was introduced as a more flexible alternative to RMS, allowing for better handling of varying task loads.

### Proportional Share Scheduling

-   In proportional share scheduling, T shares are allocated among all processes, ensuring that each application receives a fraction of the total processor time based on its shares.
-   An application receiving N shares where N < T will get N/T of the CPU time, promoting fairness among competing processes.
-   This method is particularly useful in environments where multiple applications need to share resources equitably, such as in cloud computing.
-   Example: If an application has 10 shares and the total shares are 100, it will receive 10% of the CPU time.
-   Historical context: Proportional share scheduling emerged as a response to the need for fairness in resource allocation in multi-user systems.

# POSIX Real-Time Scheduling

### POSIX.1b Standard

-   The POSIX.1b standard defines APIs for managing real-time threads, facilitating the development of real-time applications across different operating systems.
-   It includes two primary scheduling classes for real-time threads: SCHED_FIFO (First-Come, First-Served) and SCHED_RR (Round Robin), each with distinct characteristics.
-   SCHED_FIFO does not allow time-slicing for threads of equal priority, while SCHED_RR does, allowing for fairer CPU time distribution among threads.
-   Example: In a system using SCHED_FIFO, a high-priority thread will run until it blocks or is preempted by a higher-priority thread, ensuring responsiveness.
-   Historical context: The introduction of POSIX standards aimed to create a consistent interface for real-time programming across different UNIX-like operating systems.

### POSIX Real-Time Scheduling API Example
```
#include <pthread.h>
#include <stdio.h>
#define NUM_THREADS 5
int main(int argc, char *argv[]) {
   int i, policy;
   pthread_t tid[NUM_THREADS];
   pthread_attr_t attr;
   pthread_attr_init(&attr);
   if (pthread_attr_getschedpolicy(&attr, &policy) != 0)
      fprintf(stderr, "Unable to get policy.\n");
   else {
      if (policy == SCHED_OTHER) printf("SCHED_OTHER\n");
      else if (policy == SCHED_RR) printf("SCHED_RR\n");
      else if (policy == SCHED_FIFO) printf("SCHED_FIFO\n");
   }
}
```
-   This code snippet demonstrates how to retrieve the current scheduling policy for threads in a POSIX-compliant system, showcasing the use of pthread attributes.
-   The `pthread_attr_getschedpolicy` function is used to check the current scheduling policy, which can be either SCHED_OTHER, SCHED_RR, or SCHED_FIFO.
-   The output of the program informs the user of the current scheduling policy, which is crucial for understanding how threads will be managed by the scheduler.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzY5Nzg5MTExXX0=
-->