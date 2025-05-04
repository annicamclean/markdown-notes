# Chapter 9 Study Guide

# FILL IN

# ANSWER
## Chapter 9: Main Memory

### Background of Memory Management

> Memory management is crucial for efficient CPU operation and program execution.

-   Programs must be loaded into memory from disk to be executed, as the CPU can only access main memory and registers directly.
-   The memory unit processes a stream of addresses and requests, which can lead to stalls due to slower main memory access compared to CPU registers.
-   Cache memory is utilized to bridge the speed gap between the CPU and main memory, enhancing performance.
-   Memory protection is essential to ensure that processes do not access memory outside their allocated address space, typically enforced by base and limit registers.![Diagram showing memory segmentation with an operating system, three processes, and base and base + limit registers.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/84b80a37-262d-4e0d-9033-9f3632484dad/images/6cf9f37b4ddb4f04aed289350040e74e.jpg?Expires=1747006305&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=svHrrLeGf0UiPoCRTXCRzGbGnZuQLUqSiWAn%2Fx3AZBKYZ291FXyNJWI05kqZApxq4qanRDjCaHuvwORubtlYRspEX1p2%2FtiLZmp3WM1l8tbQpyxHV1fjYxqsYfwCZMBMRG5d510Ni61E8lyz%2BMtz0M7HQeTurbff3yYCzYlbNtwiS4wx70AupqGWK4bjHj5fwRDZfxaZQLreX%2FzwfJ3bKy7L%2F9VDKaRQnzHtPYTZRYCyDTUx%2FxGE%2B%2FBzBlbEtF3kVpyVYP3UTlSGJ9ay%2BYMbq%2F107b043srf89mU7%2FgTxBN17%2Fc4BIJC2BMoMAVQUP%2FP%2Fyfl7KED1CVP%2Bp1J%2FsJAsA%3D%3D)![This flowchart illustrates a CPU's memory access process, checking if an address is within the valid range (base to base+limit) before accessing memory, otherwise trapping to the operating system.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/84b80a37-262d-4e0d-9033-9f3632484dad/images/df2f6e6ecd9e4b98b091a3fe91e38566.jpg?Expires=1747006305&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=WaXuR4LGPqgJPI%2B5uNYUzl%2FMcIM0PE1qFtB9Bqhp%2FAtXNpltXZLezoBAqGFZkxtsBRdLiCv6I1eFgfhubTKX4Re46fCIxgPbk7O78PpvYmnLhEmSRMnO9bqAzh74o2I8BbQZ15UW41f8FydsfzPvXB4JxM%2FH77aBmZBBqG2MlHTzVW1NZVcsJ6SVdegtAHUV7pL%2FaF4fWi%2FRs0RNa1dIA4wVh7pNbTqu8jrZn9j0RCFELRVzjmaWdgPgf%2FhEEj%2FvibhmiuX3ft4QGVVX1XfWsPLp77017%2BjvdRR5fCGD7xKoEBGpYuoOKHlQP%2BMnZYK4oao0eF%2F7zsjNurto09ch6Q%3D%3D)![This flowchart illustrates the process of address translation in a computer system, where a logical address is compared to a limit register, added to a relocation register to produce a physical address, and if exceeding the limit, results in an addressing error.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/84b80a37-262d-4e0d-9033-9f3632484dad/images/295b37c37a0b495a8a470ebf5922e82c.jpg?Expires=1747006305&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=D%2BpeIMHbirOrbBVDvWFfpFJJOpZpVVYTezO44IjOfB594%2FXmDT2Pw%2F6VmrDDKdgkMsArRvpOiIqHV5dQifa591yN6L65UJuydqQ6exZ%2FX8%2FooEIzfJyqHn6pjUPgeZyiMELqZIYpvD7HqFF3Rp4SfNSDexnH7vyh%2F81%2Bo29H8aHRvDyxKPTR78PElFyPjWNK%2FgdGSNmx5WzYiXAMet%2FRfLhfTCvwj6qz2n2VtupVWlgR9MRkbKt3uPCGZ4pxT2OJ8x8AsZ8GOMOqXEMRpoZF6GGhLdCZ1qZqfqt8nc%2BN7nKcbj2orl9b02pKbqwZzvIb%2Bgeaac7e1ZOuEoYa2Xw9Cw%3D%3D)

### Address Binding and Memory Allocation

> Address binding is the process of mapping logical addresses to physical addresses during different stages of program execution.

-   Programs can be bound to memory addresses at compile time, load time, or execution time, affecting how they are executed and relocated in memory.
-   Compile-time binding generates absolute code if the memory location is known beforehand, while load-time binding generates relocatable code that can be adjusted at runtime.
-   Execution-time binding allows processes to be moved in memory during execution, requiring hardware support for address mapping.
-   The memory-management unit (MMU) plays a critical role in translating logical addresses to physical addresses dynamically.![This flowchart illustrates the process of program compilation and loading, from source program to in-memory binary image, highlighting the stages of compile time, load time, and execution time.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/84b80a37-262d-4e0d-9033-9f3632484dad/images/f6eac25cdc37455c8f01815791c1ba62.jpg?Expires=1747006305&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=FmsBWmYe7kisrBePhOCIjybKivNSe4d7ZfjIodusZMnhbOyVpVHMhUDKDUSSYRGW4cMCe3K6xnCQVB%2FxmN4Qu3AgCJReCgz2SLaXLqXCDdV%2BHQP6xiP0YyIkO4JzmcUSUxEDEZRXaSf62dnJQdqV9hLrRlalEFYEKw7HErcoHOxcvSwDNwAT%2FXVdBb0cNsiLF%2BQw%2BdgKzigIsitS4QO50ZEajVlsvdzEpSZ5fZGTN8RrrRNceewZWf8NURqIH9cSFWxhvNHwvgKWd0Lr1cjjelGhXNCZmm9CicyHBEjs%2F2%2F9HyPysBxevb8BakVBvRZTSSRRs5JJZt19HwGPOQ69Xw%3D%3D)![Diagram showing how a CPU's logical address is translated into a physical address by the MMU (Memory Management Unit) before accessing physical memory.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/84b80a37-262d-4e0d-9033-9f3632484dad/images/b014550216024893ad54688b9788b93d.jpg?Expires=1747006305&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=h3yUZM3l%2BGe6eKVQquP5cMsimYtmKDVHJx1LAtYeEsLhp9Mfyr2uDPvNeqa1EsB%2BZ3H%2FK2YK%2FFQ7qonSYaXouOLkwNXH%2F81Wso6mg0d8c70uagRzPc%2FFtttSNaGt5KczrtmaKqerfnTisZXiEQp%2BBXteL75pa4sHdsR4n9f5MsemisZwp%2B2iyhnvX3NWYvX4euonyig8oI1nC5MiLSli1cD2aBrqwf2jRXUxRmNrWtG%2BrOh3Y0auWwXu%2BvbhJASk53sg6d51IX%2BvTDscs%2BO28NsTIqQrZWmqY8YC7qg0KJxtdFFFi8tJBortfiuUi8Z%2FpaXXRXzO%2FsDymBGb7WjOhg%3D%3D)![Diagram showing how a CPU's logical address (346) is translated to a physical address (14346) by the MMU using a relocation register (14000) before accessing memory.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/84b80a37-262d-4e0d-9033-9f3632484dad/images/3c74fd7b95994f459f9f0e865e922d52.jpg?Expires=1747006305&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=c%2F2d6%2B9otrWfOnDS9RRMgdgi%2FV9WWQtjSzwx51wx%2Bcjf6bBZSvPvQECI3FKsrL2cwCVD%2BiWBPTAFns26WzuJ24wk7Sk%2FtpewXvmHOLtG8yRK7OrIyjBOVhxQw4tOZOiAJvV%2FhtaUZJsCD5DhNM1wCT1o%2FUJkYN8IKXIkbweBa%2BRSLAuflOTlggOPSdRFtE1nXb2yZOV0rwxno7pIGPs3JXyXcdfff8DRHTkeItSvfLDxMetvk%2BbHGTk4vrFzU%2B42TnxMTfEnWGwqJ8PPlXWwInGZ73ToT0eB1qFLQkLS5UhQM%2Fyt2N%2BPGvdZk3vhYbu9YNlui6M6aGAWhNpZHJYOuQ%3D%3D)

### Logical vs. Physical Address Space

> The distinction between logical and physical addresses is fundamental in memory management.

-   Logical addresses are generated by the CPU and are also known as virtual addresses, while physical addresses are the actual addresses seen by the memory unit.
-   The MMU is responsible for mapping logical addresses to physical addresses, ensuring that user programs access memory correctly.
-   In compile-time and load-time binding schemes, logical and physical addresses may be the same, but they differ in execution-time binding schemes.
-   Understanding this distinction is vital for implementing effective memory management strategies.

### Memory-Management Techniques

> Various memory-management techniques are employed to optimize memory usage and process execution.

-   Dynamic loading allows routines to be loaded into memory only when needed, improving memory utilization.
-   Dynamic linking postpones linking until execution time, allowing for shared libraries and easier updates to system libraries.
-   Contiguous memory allocation divides memory into partitions for the OS and user processes, requiring efficient allocation strategies.
-   Variable partition schemes allow for more flexible memory allocation, accommodating processes of varying sizes and optimizing memory usage.
-   The dynamic storage-allocation problem addresses how to efficiently allocate memory from free holes of varying sizes.![This diagram illustrates the process of memory allocation and deallocation in an operating system, showing how processes are loaded and unloaded from memory.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/84b80a37-262d-4e0d-9033-9f3632484dad/images/2ef8bb365ac746eab0f4dabbbc9cb7f5.jpg?Expires=1747006305&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=auTEH9uWqOIQjZca08eQyN3CEfy0hJ6CMKOwCFFMv1NKnmqxoIHw9hxtTZ%2Fk84te2iJ7Nu7brCdOgm9pF8EGtXRWVbIFJP9lIWyQWoUf9gzIWmYUlPZVDDnVPabUSvcZNvDCO%2BzS9LUw7hMEwv3q0%2B4HrxNjvOID4KPclgUp4bKWZsq4e3yOcGRLcGy4gcF0bK0bvw%2B%2Be5aVB7r%2F7iLPKiCOa3g9byOvxULa9GhoupnmHUzTO9snnJjiB54MaPmK0%2B%2F7I038Bvd885Quht5V78g%2F3URTIZt9Z6BRIy0bafxA44VhfmWG80dfy6XEefBVP5KoOW7Jt9kwOduHoV67jw%3D%3D)

# Detailed Memory Management Techniques

### Contiguous Memory Allocation

> Contiguous memory allocation is an early method of memory management that divides memory into fixed partitions.

-   The operating system resides in low memory, while user processes are allocated in high memory, each in a single contiguous block.
-   Relocation registers protect user processes from each other and from the operating system's code, ensuring safe memory access.
-   The base register holds the smallest physical address, while the limit register defines the range of logical addresses for a process.
-   This method can lead to fragmentation and inefficient memory use, necessitating more advanced techniques.

### Dynamic Loading and Linking

> Dynamic loading enhances memory utilization by loading routines only when they are called, rather than at program start.

-   This approach is particularly useful for large programs with infrequently used routines, reducing memory footprint.
-   Dynamic linking allows libraries to be linked at runtime, enabling programs to use updated versions of libraries without recompilation.
-   A stub is used to locate the appropriate library routine, which can be replaced with the actual address during execution.
-   This technique supports shared libraries, facilitating easier updates and patching of system libraries.

### Memory-Management Unit (MMU)

> The MMU is a critical hardware component that translates logical addresses to physical addresses at runtime.

-   It utilizes a relocation register to adjust logical addresses generated by user processes before they are sent to memory.
-   The MMU ensures that user programs operate with logical addresses, maintaining the abstraction from physical memory addresses.
-   This dynamic mapping is essential for execution-time address binding, allowing processes to be relocated in memory as needed.
-   Understanding the MMU's role is vital for grasping modern memory management techniques.

### Fragmentation and Allocation Strategies

> Fragmentation occurs when memory is allocated and deallocated, leading to inefficient use of memory space.

-   Internal fragmentation happens when allocated memory blocks are larger than necessary, while external fragmentation occurs when free memory is split into small, non-contiguous blocks.
-   Strategies to mitigate fragmentation include compaction, which consolidates free memory into larger blocks, and using paging or segmentation.
-   The dynamic storage-allocation problem addresses how to efficiently satisfy memory requests from a list of free holes, balancing allocation and deallocation.
-   Understanding these concepts is crucial for designing efficient memory management systems.

# Memory Allocation Strategies

### Overview of Allocation Strategies

-   **First-fit**: Allocates the first hole that is large enough to satisfy the request, leading to faster allocation times.
-   **Best-fit**: Allocates the smallest hole that is sufficient, which minimizes leftover space but requires searching the entire list unless sorted by size.
-   **Worst-fit**: Allocates the largest available hole, which can lead to larger leftover holes but is generally less efficient in terms of speed and storage utilization.
-   **Performance Comparison**: First-fit and best-fit are generally preferred over worst-fit due to their better speed and storage efficiency.

### Fragmentation Types

-   **External Fragmentation**: Occurs when total free memory is sufficient to satisfy a request, but it is not contiguous. Analysis shows that with N allocated blocks, approximately 0.5N blocks may be lost to fragmentation, leading to the 50-percent rule where up to one-third of memory may be unusable.
-   **Internal Fragmentation**: Happens when allocated memory is slightly larger than requested memory, resulting in unused space within a partition.

### Reducing Fragmentation

-   **Compaction**: A technique to reduce external fragmentation by shuffling memory contents to consolidate free memory into one large block. This requires dynamic relocation and is performed at execution time.

# Paging Mechanism

### Introduction to Paging

-   **Definition**: Paging allows a process to be allocated physical memory in a non-contiguous manner, avoiding external fragmentation and the issues of varying memory chunk sizes.
-   **Frames and Pages**: Physical memory is divided into fixed-sized blocks called frames, while logical memory is divided into blocks of the same size called pages.
-   **Page Table**: A page table is maintained to translate logical addresses to physical addresses.![This diagram illustrates the process of paging in memory management, showing how logical memory pages are mapped to physical memory frames using a page table.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/84b80a37-262d-4e0d-9033-9f3632484dad/images/74fb495cf5184804b9404e1c47948655.jpg?Expires=1747006305&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=B5jvlZIx9EN0fDW%2FsZC5fz0EY3P6eC%2F7sABmBq%2FCvE7%2FXbLwS3zsS60jlQpKQWYAYGvaWj5H27Eey%2FsxkigV%2BqdcyaVhp6u0Sc4MvVRbM%2FvIkkclGRlwugZhCr8wxeMpd0Nfh3Jx7czYN2L6OxDJ%2BcL1kwmT%2BxNWpyh%2Fsmbvbf2MNujjN2%2BREVWKpZRVJuiyzSb5wZQkfjKw3SsBsC56to9YsWtXoI6dXU6%2Fkl12uAr4LrboMnHLy%2BU%2B3Qfl1wHA2%2FBkXpgq8t9%2FouddvG8R6DvEXDP4LBLksKG3bxOjS28G0tw9BH1Pg9hqMqhDue6RUf%2B57SWFLVygovtA6WmiiA%3D%3D)![Diagram showing how logical memory addresses are mapped to physical memory addresses using a page table.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/84b80a37-262d-4e0d-9033-9f3632484dad/images/57d3d9fb8f3f4ed0a6b5cc12344bb061.jpg?Expires=1747006305&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=wZAqUBOaE%2FI7XEXOo8T%2BXTXbOTVm9L9O83Co7OvRYsnMBkbVtC%2B9djUY1NKnLwVlFWT7O3UFI0lmtWzy1StIT%2BWbN8mWGm0SCDTU7zDa8rclTOb2zbEcYbSMAeoy64sBl4gzGrgWdNKG8YJas3QYQ7XqRjUOqZkNSPwV%2FpFCffVM5huG8TzkKfA1SvCPV6g4VVQaTbFo%2FOEIYrJhP4bBzSmjARY6OcY2kq55SW3jkN2wJiRPPrcLdIwUm%2FKxMVyJPUhKguuMe%2BuoFEuk6xiHAS02ZrpfMLmqxzwpRhzugWXoFrGLX5mW1ux5n8memd%2FNkjyTVvZY3ahHQLGVKHSgCQ%3D%3D)![This diagram illustrates the allocation of pages to frames in memory, showing a free-frame list, a new process, and the resulting page table.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/84b80a37-262d-4e0d-9033-9f3632484dad/images/9aac701532384e42b7fa830b0bc9ff4d.jpg?Expires=1747006305&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=0mkr%2BV0eKS5TKyYSkhZs8CDi0tSn1KHVYR5XK7jw20om%2FcWRpiPy6I6uAraacuhVww9CWpalsulK8wuJCOT6tsR%2BrKh51Qgani5vBKdJOhpvkMV3noQNiEwudUVJOqYB655UK511YVMmVu1%2FtbVl7u4y261%2FomTPtRkYpS%2BWblNGGKjCwhPLIUDSTTVkMv70BEbuZsXovAy0cH%2BibIirRBJoOuDTeEvJApfEiv8%2Fq2Kj9zbN4rBwPUlw8uZWgiwhpNqczEqZCCt5vlxgViP27fbpy6ylhNdVXKTzA1v1uIKhMdqZo36v8yKJnohKnj6VokRXN%2BUgYU0oUEfkX7xqRQ%3D%3D)

### Address Translation

-   **Address Structure**: The address generated by the CPU is divided into a page number (p) and a page offset (d). The page number is used to index into the page table, which contains the base address of each page in physical memory.
-   **Example**: For a logical address space of 2^m and page size of 2^n, the translation process is crucial for memory management.

### Internal Fragmentation in Paging

-   **Fragmentation Calculation**: If the memory requirements do not align with page boundaries, the last allocated frame may not be fully utilized. For example, with a page size of 2,048 bytes and a process size of 72,766 bytes, the internal fragmentation can be calculated as 2,048 - 1,086 = 962 bytes.
-   **Average Fragmentation**: On average, fragmentation is about half the frame size, leading to considerations for optimal frame sizes.

# Page Table Implementation and TLB

### Page Table Structure

-   **Location**: The page table is stored in main memory, and the page-table base register (PTBR) points to it.
-   **Efficiency**: Changing page tables only requires updating the PTBR, which reduces context-switch time significantly.

### Translation Lookaside Buffer (TLB)

-   **Functionality**: TLB is a special fast-lookup cache that stores page table entries to speed up address translation.
-   **TLB Lookup Process**: During a TLB lookup, the Memory Management Unit (MMU) checks if the page number is present in the TLB. If found, it retrieves the frame number; if not, it resorts to the page table.![Diagram illustrating the translation of a logical address into a physical address using a Translation Lookaside Buffer (TLB) and page table, showing both TLB hit and miss scenarios.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/84b80a37-262d-4e0d-9033-9f3632484dad/images/87cfcf7e2f564663b89760dc66053365.jpg?Expires=1747006305&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=A4A5ko2BFqw49WsWxsuaI%2BKqnXwt28owl0M68ElyzOBBaLqeuaIwNKEYkyK%2BQ2yZiL6wgpy8eDvpzoWhLryJAP1fUrXRykGlFhN%2FI5d52Stbzm7yghm1FcMWHRwwdTjttN5SuAcDA8Y0480aErr1FRyRmbrZI4ulELRsQmI0HKd2lsn3HYjPKF2dKRXLpUyKGf0KUbhMX4HRpfL3HwRHrdD%2BPnvYctaXJnM6O%2BfcybhDrIi80xAgFWHk4M41fSbz379oJXbCsVED8%2BWvDAlZRG0Oo1wX%2FApR0ER%2F7dYXegHzzNTyaaZ%2FpUYpGWRX2VJOk5G4eOe7KYUNg51RrFX0vQ%3D%3D)

### Effective Access Time (EAT)

-   **Calculation**: EAT is calculated based on the hit ratio of the TLB. For example, with an 80% hit ratio and a memory access time of 10 ns, the EAT can be computed as follows:
    
    EAT = 0.80 x 10 + 0.20 x 20 = 12 ns.
    
-   **Improvement with Higher Hit Ratios**: A 99% hit ratio results in an EAT of 10.1 ns, indicating a minimal slowdown in access time.
    

# Memory Protection

### Mechanisms of Memory Protection

-   **Protection Bits**: Each frame is associated with a protection bit indicating whether it is read-only or read-write.
-   **Violation Handling**: A write attempt to a read-only page triggers a hardware trap, indicating a memory protection violation.

# Overview of Paging and Memory Management

### Introduction to Paging

-   Paging is a memory management scheme that eliminates the need for contiguous allocation of physical memory, thus avoiding fragmentation.
-   It divides the logical address space into fixed-size pages and maps them to physical memory frames.
-   Each process has its own page table that keeps track of the mapping between logical pages and physical frames.

### Valid-Invalid Bit in Page Tables

-   Each entry in the page table has a valid-invalid bit that indicates whether the page is in the process's logical address space.
-   A 'valid' bit means the page is legal and can be accessed, while an 'invalid' bit indicates the page is not accessible, leading to a trap to the kernel if accessed.
-   The page-table length register (PTLR) can also be used to verify the logical address range for a process.![This diagram illustrates a page table's structure and function in memory management, showing how virtual page numbers map to physical frame numbers and a valid/invalid bit indicates whether a page is in memory.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/84b80a37-262d-4e0d-9033-9f3632484dad/images/b2b5f0c43e334289b2ae8ed69b4e040a.jpg?Expires=1747006305&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=z%2FaesC8iddDbptVcVbNBvP5KflAIcII6bNI0GsGWg8Hd1FToVIcIdFVcus%2BB4lqP%2BCUiH3x3r2g%2BmWIwcM06EXdhVYp3OGeGw9r18nuR%2FD7K7VHIYHHKbHViZaMxl2%2FzL2VAjyJ58O%2B0eMlDZ5nqpg3NKpo2IG695%2BjGcy3uopp5SOZ1OjkTcuWDQuGbFfM%2BVPRrzm%2F2EukA5Q2XQhk7wB1xJW5FsdsNRAPEroE7FEGDm000SAAsZRV9EYsXaql94yMMaFbNc7qWFZMqvbdf2OBexSdVfLK1hRUlnQR1y9rBSTVjEBNe%2FvOwC6P3b6e47J3ZPgNt4DhGJwO1lYJ%2Bcw%3D%3D)

# Shared and Private Pages

### Shared Pages

-   Shared pages allow multiple processes to access the same physical memory, which is useful for read-only code like libraries and executables.
-   This mechanism is similar to multiple threads sharing the same process space, enhancing efficiency and reducing memory usage.
-   Shared pages can also facilitate interprocess communication if read-write access is permitted.

### Private Pages

-   Each process maintains its own copy of private code and data, ensuring data integrity and security.
-   The pages for private data can be located anywhere in the logical address space, allowing flexibility in memory allocation.
-   This separation of private and shared pages is crucial for process isolation in modern operating systems.

# Page Table Structures and Hierarchical Paging

### Structure of the Page Table

-   A straightforward page table for a 32-bit logical address space with a 4 KB page size would require over 1 million entries, consuming significant memory.
-   Each entry typically occupies 4 bytes, leading to a total of 4 MB for the page table alone, which is impractical for contiguous allocation.
-   Hierarchical paging techniques are employed to manage large page tables efficiently.

### Hierarchical Paging Techniques

-   Hierarchical paging breaks the logical address space into multiple smaller page tables, reducing memory overhead.
-   A two-level paging scheme divides the logical address into a page number and an offset, allowing for more manageable page table sizes.
-   The logical address is structured such that the outer page table index and inner page table index are used to locate the physical frame.![Diagram showing a two-level page table mapping virtual addresses to physical addresses in memory.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/84b80a37-262d-4e0d-9033-9f3632484dad/images/873bba49e5dc4488aabfe77fc155c1ac.jpg?Expires=1747006305&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=qdaojx6RulWSnXFjrc9NfB0OVdgVVzUbQZ26z3cmn9OO6t95qZp1aLvY0Ukw5apZJEYK%2FX52aYGSPr3IXVXpfeJKIRjRkhU1HNgRaQ5NU5kXeHHzxgIcP1bS7bDy70b6N%2BkO5PxN0SxbkdBfF6Bg77kz%2FcoQJjGJwJB8xW4pCiOiEG9wOmlnjHxGiylyOc0M7tIVM5383QCgufxnSkRtJsIzZ%2FUNcL%2FXbvx7wiyTZM5ZL9FRJ0GbbuGu%2B%2Bjbg1zzhJU72qlbCRayirsbPQk%2BeKog%2BLWDIRWRPwJIYDaZQeRA2NTjyp6pp3z5N8KLlQy8k0u9bZCJrolKqvNgxX4sGw%3D%3D)![Diagram showing a two-level page table translating a logical address into a physical address.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/84b80a37-262d-4e0d-9033-9f3632484dad/images/6d293638d74d408382b029f96e7f1779.jpg?Expires=1747006306&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=OwJiojKbPpUEdvtn7%2BVPkCIhuYEpv3mzb7qL7d%2FkXvwfDap2UlDZVeTUP%2BQ653QakaR7m5CGg2A0TTgYpA0y6hwS%2BZ3O7qVZB1cYZQ5u5mm6sHt2meoXqSRiLkmIPulOp%2BQlaY%2FYjPUshWXirAWrxDym%2FmnmYwSaLV4ZVFudCxf7x%2FrsxC0zkQfIAYvg40NXHzJIWd7SDPoYRUgF2dkUP9%2B19ZWj8lg3hyexeqWk%2Fn%2Fjbr15tBOCmLNnoJakm%2Fmcp%2FZtxZceE7PSueV%2FvxTddy2P%2BEuzZxa7bhf56JZ%2FYN5T8ut2oEnZ3hwoxUrFZyCj4TzvHFvbASKJ%2B5vbnc4WnA%3D%3D)

# Advanced Paging Techniques

### Hashed Page Tables

-   Hashed page tables are used in systems with address spaces larger than 32 bits, where the virtual page number is hashed into a table.
-   Each entry in the hashed page table can contain a chain of elements to handle collisions, improving lookup efficiency.
-   This method is particularly useful for sparse address spaces, where memory references are non-contiguous.![Diagram illustrating how a hash function translates a logical address into a physical address in memory using a hash table.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/84b80a37-262d-4e0d-9033-9f3632484dad/images/f1b68b02c7aa4bd5a68fb63c77b0ae82.jpg?Expires=1747006306&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=2rVuaplQ%2FWjhfsC0cFBiumf2%2FOBkcuzkQfL6PDvbOrQXSshS1m8yWW8vVInkT4vo2jiKpU2JpbjtmALwBI0faljwP3HNR28uRiO88O6zjnrPYxJ5Z8oh%2FRn3tsszBRycuVztMyWZ9IJiImVihE4e%2Fw%2BDbHMsRwBR0cXvr0Piij7cnhdsZ8glDHX6MHV3kQ3g1WmY6CtZRRbRoBYjtwF%2B4hOdB43HrHPmIRLytWBkh6HLhacGzBKLdlvl6mTJV1fmae1JvRwH%2FR3ucobKMBTvuDm%2FubIsHg27uce0R0qWNJvlQ8vTI8PW8CD4oRcSg3CA11ufjMt8DwgF8oAZT7yIBQ%3D%3D)

### Inverted Page Tables

-   Inverted page tables track physical pages instead of logical pages, with one entry for each real page of memory.
-   Each entry contains the virtual address of the page stored in that physical location and the process ID (pid) that owns it.
-   This approach reduces the memory needed for page tables but increases the time required to search for a page reference.![Diagram showing three processes (P₁, P₂, P₃) with their respective page tables and how they are mapped to physical memory.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/84b80a37-262d-4e0d-9033-9f3632484dad/images/0cac7982e9174488a20d48f51e179e3f.jpg?Expires=1747006306&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=Q6E7ipMlA2ecjygLuvdtGXWzsfiRa5JM7Ya2Xq2xY0JiQ4ETl3dCsNPaXCZ6ENpoV%2FQihEXC5VuSJCD16UcwEVESfke9r4LjPjzfsDJVDA7Cz9gqpiLWfMB1b%2BaS4IgXxY5CcbpIsy%2B%2F0Yz%2FdVVx1hV9h%2FXwKTHYq0Lye%2Fhxj83CTbNrj5bswU%2FqPY%2BcGXUsKQCj%2BlU8sCAKVZokomj6tPgHtIBVqnkmtfQZ1CYeZLJ0AzuCM445zSDdjr3VKwp%2FLrrVy4eYdDBTM6PlqfFnLoHdva6dC5AgoCAp5N5uZusE%2BzSYzM0l3UjAs52oGoURY%2B%2F3DotXZN06EUaD02aN%2FA%3D%3D)

# Swapping and Context Switching

### Swapping Mechanism

-   Swapping allows a process to be temporarily moved out of memory to a backing store, enabling more processes to run than the physical memory can hold.
-   The backing store must be fast and large enough to accommodate all memory images, with direct access to these images.
-   Swapping is often triggered when memory demand exceeds a certain threshold, and idle processes are prime candidates for swapping out.![This diagram illustrates the process of swapping a process (P₁) out of main memory and swapping another process (P₂) into main memory from a backing store.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/84b80a37-262d-4e0d-9033-9f3632484dad/images/30209f8a7b974681afddd72b8f0b61e1.jpg?Expires=1747006306&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=nX3E36raTEIuZJf%2FBhbLxHAoKufdFH7k3TTf2qKW9PR1HnW5Cgpzyuf79JlfYtoDcQt%2BHWOPeJWvDkzFE4EPmAFX0qb2%2F4FP1qeFTVzGNkXQcsuK1bThdXqQzxcfwG3ha51PHt9WB06DfKV64SGQGuEZETGems9jcw%2FUw50HB9Yotu3EMXOzpVCv3NTY0cLHnrhkd%2FE9A5egjvbMdcd0aICclO9flQH7YSJAdxmPj2jbCkHHpjISxD94kdn1TRSMEtxvBdpQkql0fHpSJhZG6s88SCzWBXuXDznrYk8CsZaLmOE%2FpgHaKxri2e8fdrJLIKSqAI13fUMU2i%2BtXzh%2BVg%3D%3D)

### Context Switch Time and Swapping

-   Context switching can be time-consuming, especially if the next process to be executed is not in memory and requires swapping.
-   For example, swapping a 100MB process at a transfer rate of 50MB/sec can lead to significant delays, totaling 4000 ms for both swap out and swap in.
-   Modern systems often implement modified swapping techniques to optimize performance and reduce overhead.
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDkzOTMxOTUzXX0=
-->