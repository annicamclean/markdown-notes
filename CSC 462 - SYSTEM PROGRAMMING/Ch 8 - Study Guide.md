
# Chapter 8 Study Guide
# System Model

### Overview of System Resources

-   A system consists of various resources that can be utilized by threads, including CPU cycles, memory space, I/O devices, and network interfaces.
-   Resource types are denoted as R1, R2, ..., Rm, where each type has a certain number of instances (Wi). For example, CPU has four instances, and Network has two instances.
-   Threads interact with resources through three primary actions: Request, Use, and Release.
-   If a resource is not available when requested, the thread must wait until it can acquire it, leading to potential deadlock situations.

### Deadlock with Mutex in Pthreads

-   Deadlock can occur when two threads (T1 and T2) attempt to lock multiple mutexes in an inconsistent order, leading to a situation where each thread is waiting for the other to release a mutex.
-   Example code for T1 and T2 illustrates this scenario, where T1 locks first_mutex and then second_mutex, while T2 does the opposite, creating a circular wait situation.

### Deadlock with Semaphores

-   Similar to mutexes, deadlocks can occur with semaphores when two threads (T1 and T2) attempt to acquire two semaphores (S1 and S2) in a conflicting order.
-   The wait operations on semaphores can lead to a situation where both threads are waiting indefinitely for each other to release the semaphores.

# Deadlock Characterization

### Four Necessary Conditions for Deadlock

-   ****Mutual Exclusion****: Only one thread can use a resource at a time, which is essential for non-sharable resources.
-   ****Hold and Wait****: A thread holding at least one resource is waiting to acquire additional resources, leading to potential deadlock.
-   ****No Preemption****: Resources cannot be forcibly taken from threads; they must be voluntarily released after use.
-   ****Circular Wait****: A set of threads exists where each thread is waiting for a resource held by another thread in the set, creating a cycle.

### Resource-Allocation Graph

-   Deadlocks can be represented using a resource-allocation graph, which consists of vertices (threads and resources) and directed edges (request and assignment edges).
-   The graph helps visualize the relationships between threads and resources, indicating potential deadlock situations.
-   If the graph contains cycles, it may indicate a deadlock, especially if there is only one instance of each resource type.  
    

### Basic Facts about Deadlocks

-   If the resource-allocation graph contains no cycles, there is no deadlock.
-   If there is a cycle and only one instance per resource type, a deadlock is guaranteed.
-   If there are multiple instances per resource type, deadlock is possible but not certain.

# Methods for Handling Deadlocks

### Overview of Deadlock Handling Approaches

-   Deadlocks can be managed through prevention, avoidance, detection, and recovery strategies.
-   ****Deadlock Prevention****: Ensures that at least one of the four necessary conditions cannot hold, thus preventing deadlocks from occurring.
-   ****Deadlock Avoidance****: Requires the operating system to have advance knowledge of resource requests to avoid entering a deadlock state.
-   ****Deadlock Detection****: Allows the system to enter a deadlock state but includes mechanisms to detect it and recover from it.
-   ****Ignoring Deadlocks****: Some operating systems, like Linux and Windows, choose to ignore deadlocks, leaving the problem to application developers.

### Deadlock Prevention Techniques

-   ****Mutual Exclusion****: Not required for sharable resources, but necessary for non-sharable resources.
-   ****Hold and Wait****: Threads must not hold any resources when requesting new ones, which can lead to low resource utilization and potential starvation.
-   ****No Preemption****: If a thread holding resources requests another resource that cannot be allocated, it must release its held resources, which is often impractical for mutexes and semaphores.
-   ****Circular Wait****: Imposing a total ordering of resources can prevent circular wait conditions by requiring threads to request resources in a specific order.

### Deadlock Avoidance Techniques

-   The Banker’s Algorithm is a well-known method for deadlock avoidance, which allocates resources only if it is safe to do so, ensuring that the system remains in a safe state.
-   The algorithm requires knowledge of maximum resource needs and current allocations to make decisions about resource requests.

# Recovery from Deadlock

### Approaches for Recovering from Deadlock

-   Recovery strategies may involve terminating one or more threads involved in the deadlock to break the cycle.
-   Another approach is resource preemption, where resources are forcibly taken from threads to resolve the deadlock situation, although this can lead to inconsistency and requires careful management.
-   The choice of recovery method often depends on the specific application and system requirements, balancing between performance and complexity.

### Process Termination

-   To recover from deadlock, threads can be aborted to eliminate cycles.
-   The order of termination can be based on priority, resource usage, and completion time.
-   Interactive threads may be treated differently than batch processes.

### Resource Preemption

-   Selecting a victim thread for preemption should minimize costs associated with rollback and starvation.
-   Rollback involves returning a thread to a safe state and restarting it from there.
-   Starvation can occur if the same thread is repeatedly chosen as a victim, necessitating careful management.

# Deadlock Avoidance

### Overview of Deadlock Avoidance

-   Deadlock avoidance requires a priori information about resource needs of threads.
-   Each thread must declare the maximum number of resources it may need, allowing the system to make informed decisions.
-   The deadlock-avoidance algorithm dynamically checks the resource-allocation state to prevent circular-wait conditions.
-   Resource-allocation state is defined by available and allocated resources, and maximum demands of threads.

### Safe State Concept

-   A system is in a safe state if there exists a sequence of thread executions that can complete without leading to deadlock.
-   For a thread Ti, if its resource needs are not immediately available, it can wait until all preceding threads Tj have finished.
-   The system can allocate resources to Ti only if it can guarantee that all threads can eventually complete.

### Basic Facts about States

-   If a system is in a safe state, it guarantees no deadlocks will occur.
-   An unsafe state indicates a possibility of deadlock, necessitating avoidance strategies.
-   The goal of avoidance is to ensure the system never enters an unsafe state.

### Avoidance Algorithms

-   For single instances of each resource type, a resource-allocation graph scheme is used.
-   For multiple instances of a resource type, the Banker’s Algorithm is applied, which checks resource allocation against maximum claims.

# Resource-Allocation Graph Scheme

### Graph Representation

-   A claim edge (Ti → Rj) indicates that process Ti may request resource Rj, represented by a dashed line.
-   When a thread requests a resource, the claim edge converts to a request edge.
-   Once the resource is allocated, the request edge becomes an assignment edge, and when released, it reverts to a claim edge.

### Safety Algorithm

-   The safety algorithm checks if a thread's request can be granted without leading to a deadlock.
-   It uses vectors Work and Finish to track available resources and completion status of threads.
-   If all threads can finish, the system is in a safe state.

### Banker’s Algorithm

-   The Banker’s Algorithm requires threads to declare maximum resource needs a priori.
-   It checks if granting a resource request leaves the system in a safe state; if not, the thread must wait.
-   Data structures include matrices for Max, Allocation, and Need, which help in resource management.

### Example of Banker’s Algorithm

-   Consider 5 threads (T0 to T4) and 3 resource types (A, B, C).
-   The system's state is represented in matrices showing Allocation, Max, and Available resources.
-   The Need matrix is calculated as Need[i,j] = Max[i,j] - Allocation[i,j].

# Deadlock Detection

### Detection Mechanisms

-   Systems can be allowed to enter a deadlock state for detection purposes.
-   A detection algorithm checks for cycles in the wait-for graph, indicating deadlocks.
-   The algorithm's complexity is O(n²) for cycle detection, where n is the number of threads.

### Resource-Allocation Graph and Wait-for Graph

-   The resource-allocation graph shows the current allocation of resources to threads.
-   The wait-for graph indicates which threads are waiting for resources held by others.

### Detection Algorithm for Multiple Instances

-   The detection algorithm initializes Work and Finish vectors to track resource availability and thread completion.
-   It checks if any thread can finish with the currently available resources; if not, a deadlock exists.

### Example of Detection Algorithm

-   A snapshot of resource allocation shows the current state of threads and their requests.
-   The algorithm checks if a thread's request can be satisfied with available resources, determining if the system is in a deadlock state.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTUzNDA2Mjg1M119
-->