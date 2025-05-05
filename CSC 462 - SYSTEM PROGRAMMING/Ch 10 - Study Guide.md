# Ch 10 Study Guide

# FILL IN
  

Overview of Virtual Memory

  

  

Definition and Benefits of Virtual Memory

  

1.  Virtual memory separates __________ memory from __________ memory.
2.  It enables larger __________ address spaces than physical memory.
3.  Reduces __________ operations, increasing CPU __________.
4.  Programs are not constrained by physical memory limits, improving __________ management.
5.  Supports shared memory and dynamic linking of __________.

  

  

  

  

  

Virtual Address Space and Physical Memory

  

  

6.  Virtual address space is a __________ view of memory, starting at address _____.
7.  Physical memory is divided into __________ __________.
8.  The __________ (abbreviation) maps logical to physical addresses.
9.  Stacks grow __________, heaps grow __________, leaving holes.
10.  Shared __________ can be mapped into the virtual address space.

  

  

  

  

  

Demand Paging

  

  

Concept of Demand Paging

11. Demand paging loads pages only when __________.

12. A __________ swapper loads pages only when referenced.

13. A __________ manages which pages are in memory.

  

Handling Page Faults

14. A __________ occurs when a page is not in memory.

15. OS checks the - bit in the page table.

16. The page is loaded from __________ storage into a free frame.

17. The instruction that caused the fault is __________.

  

  

  

  

Page Replacement Algorithms

  

  

Overview of Page Replacement

18. Page replacement is used when there are no free __________.

19. __________ replaces the oldest page.

20. __________ algorithm replaces the page not used for the longest future period.

21. __________ replaces the least recently used page.

  

Working Set Model

22. A working set is the set of __________ a process actively uses.

23. Locality of __________ explains frequent access to nearby memory.

  

Basic Page Replacement Process

24. May involve writing a __________ page to disk before replacement.

  

  

  

  

Operating System Implementations

  

  

25.  Linux, Windows 10, and Solaris each have unique __________ management approaches.
26.  --on-demand is used to initialize memory securely.

  

  

  

  

  

Stages in Demand Paging

  

  

Overview & Steps

27. Demand paging begins with a __________ to the OS.

28. OS saves process __________ before handling the page fault.

29. OS checks legality and finds the page on __________.

30. Updates the __________ __________ after loading the page.

  

Performance of Demand Paging

31. Page fault rate (p) ranges from ___ to .

32. Effective Access Time (EAT) = (1 - p) x memory time + p x (_______ + __________ + __________).

  

  

  

  

Demand Paging Optimizations

  

  

33.  __________-on-Write allows sharing pages until modified.
34.  Mobile systems often avoid __________.

  

  

  

  

  

Memory Management Strategies

  

  

Frame Allocation Strategies

35. __________ allocation: equal frames per process.

36. __________ allocation: based on process size.

  

Global vs. Local Allocation

37. Global replacement selects frames from the entire __________.

38. Local replacement restricts replacement to __________-owned frames.

  

Thrashing & Page Fault Management

39. __________ occurs with excessive page faults and low CPU utilization.

40. __________ is a metric to dynamically adjust memory allocation.


Advanced Techniques

  

Buddy System

41. Allocates memory in powers of ___.

42. Splits memory chunks into __________.

  

Slab Allocator

43. Uses contiguous pages to create __________ for kernel data structures.

44. Linux slab variants include __________, __________, and __________.
# ANSWER
# Overview of Virtual Memory

### Definition and Benefits of Virtual Memory

-   Virtual memory separates logical memory from physical memory, allowing programs to execute without needing the entire code in memory at once.
-   It enables larger logical address spaces than physical memory, simplifying program development and allowing for concurrent execution of multiple programs.
-   Reduces I/O operations needed for loading and swapping programs, leading to increased CPU utilization and throughput.
-   Programs can run faster as they are not constrained by physical memory limits, allowing for more efficient resource management.
-   Facilitates shared memory and dynamic linking of libraries, enhancing the flexibility of program execution.![Diagram showing how virtual memory pages are mapped to physical memory and swapped to a backing store.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/af8c1b93-7bc6-4047-81a6-6ade440d0fbe/images/13c7b772af124c80939ad40a339368ba.jpg?Expires=1747008079&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=f6ifsy0pFjswUpByMj%2Fp6kVkYEq4RJKVae%2FE1LbU4zXQrgLB2wQOJrhBShwRJmtkHPv2ofuAMWB7M5GHhDKMcbRo8Chjqyy64fPAMSFm0YAPmcBCCutJ5XzFhc3GbnuceW%2BcB4wOV4whIOf%2BahOEbqs2tHeJovHNEFpALzal3TRZeFNXtbPR%2FYl8PejLOHajZS8BCqcS7zcc1XE4aovwmaxfmkzT7q5meVbg2k%2BZB%2Ba5%2BDwXQhxLyY5%2B8te18SR5MpLzKkk6KtyS07jxrQBB7uv3EkNYPTFVjDgM%2Fh%2FQ%2B5XTG92tA9Td7eentjipr8S2lgJF3hbcfTnem4F%2FW4qz2g%3D%3D)![Diagram showing logical memory, a page table with valid-invalid bits, physical memory, and backing store illustrating the concept of virtual memory management.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/af8c1b93-7bc6-4047-81a6-6ade440d0fbe/images/65cb705616e6455387770a4da9c07329.jpg?Expires=1747008079&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=lh2VgyRXK%2BVIwIIRiukmK%2FlfGfVKzJPs3S%2FVs2pX0E5CKsGkNeM3LCurABABQPCTFJSeCGPmAa5MZB%2B9DvYNGWP3%2B77n5RxGa3clZLhzb6ahs7cHhaBvHmNd%2BqvjhIBFtop97%2B3%2BX4ZZZZicfQ0YcODtGLe2LiMzwHgo3FNXOFcf1%2BD5sFcHSSV0jcL%2FByIhnNreOX5VlUBY3vnetJraZaP%2B6qYTD%2F3u6RWjFKi%2FYKZua9RQuW0sTFuoVTVEaj9QmbjxMa7MNVEfFG6LeflmEiE5xWTaCBtRi9%2FZBEm8rNcXMmFhnnJfSgWeVTHlRoHmaHO1qrpnjmFzCdRwDN8kjw%3D%3D)

### Virtual Address Space and Physical Memory

-   The virtual address space is a logical view of how a process is stored in memory, typically starting at address 0 and organized in contiguous addresses.
-   Physical memory is divided into page frames, with the Memory Management Unit (MMU) responsible for mapping logical addresses to physical addresses.
-   Logical address spaces can be designed to maximize usage, with stacks growing downwards and heaps growing upwards, leaving holes for future growth.
-   Shared libraries can be mapped into the virtual address space, allowing multiple processes to use the same library without duplicating memory usage.![Diagram showing memory allocation in a computer program, with the stack at the top, the heap in the middle, data below, and code at the bottom.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/af8c1b93-7bc6-4047-81a6-6ade440d0fbe/images/26b9c09675c648688cacc318eb5de05d.jpg?Expires=1747008079&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=ekpoU%2FoPq84uY30ip00%2B1ArpiZs8QbvocBB3P5vHmCnB2A8yzABV0ZCXEp8Z9wi7RCBrbnyDOXAGX29MTecHRgZad2wdSOwBH083hYmWQ0yHTVATY4ArqYOakoI6bBmhurYa4a0aI4UfiC0Jzvm%2BBmSQ8euq5owD6Aogu8DKkYzUrEXfdPFU5OeLG3ay0DrZbQd8wMkYufIcGHhC5285PGIstp0jl17dN1NjxAzcMDRuKP%2Fxbz7Vuiw9QypVgxm%2BwBt68si0Zoad6J%2BYMOr7r7vrIrKUzfxpyN%2B%2Fsb2kSqV1ajodhtRXvO6A6KIo032MlP9aGsHAGBrkTXsJZP9SKw%3D%3D)![Diagram showing two processes sharing a section of memory (shared pages) containing a shared library, with each process having its own stack, heap, data, and code segments.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/af8c1b93-7bc6-4047-81a6-6ade440d0fbe/images/500af0f2fba8425aa144fc86de00b6fc.jpg?Expires=1747008079&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=oS1yU2gDdEHP%2B4mtsg1q3dV%2Fuq3sLfClB1S6SBbwawwkZqi15YKrptQ9zx3YFpIuT8NTzYzLVeKK7AAed4d1QNSCAmz%2FzzU1Vsyw1pn87lMEmpfDoDilkZeXBin3b6yZxxBA%2FUVgH68AhrCSCFEudqvZVpyOdvev%2FJT8RfL40R2hNkVnbUEtx5HtQcS%2FE%2BoH0qI%2BdeLa3Tnjm2b%2FjTkc6XoR00cjiVYryLBJEsR%2FQstSLuP%2BguHhNd2q%2Bwezdotes6U3P44lQYE0cziTX7yLYnsc2Lrd7yfUDN7alP2MflC3N7koJu5jmmOxae%2FA9Y00acnnpsA869OW6nB7mdTOvA%3D%3D)

# Demand Paging

### Concept of Demand Paging

-   Demand paging allows pages to be loaded into memory only when they are needed, reducing unnecessary I/O and memory usage.
-   This method improves response times and allows for more users to run concurrently on the system.
-   The lazy swapper only loads pages into memory when they are referenced, optimizing memory usage and performance.
-   A pager is responsible for managing the pages and ensuring that only necessary pages are in memory, similar to a traditional paging system with swapping.![This diagram illustrates the swapping of program segments between main memory and secondary storage, showing how program A is swapped out and program B is swapped in.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/af8c1b93-7bc6-4047-81a6-6ade440d0fbe/images/d1542224ea384ae9a9656aa7a27f2ef4.jpg?Expires=1747008079&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=ySos9%2FXJPxwac4%2FiQQBz0mTJ36UTKvJ7YnGf74q728OgQXqLiAy1aYDI5jBFTOtUXXHZpSqxK2vSwO7QV7P5g0IDvnE%2F%2F8q4TuUWOzi9L%2FxGWaoYPpGlq2eKa9eOpTnFd17SOhV85Hm7OYGc3Hr0iOiAWbsJF7IHAclXSqCCQg6DNdJBs3HHqDXTgw0jC9qJ%2B6CwLi3HgD1vnauJlXSZEnYJVmwGvqY1Rv26T6WuAxVyFSZ89%2BhckaFSWIgCrBfbu4sIX95JPCzF8zuClpFzHKAg7RYpSqN03RltnuyZV7yTtMefCimH2ngBwNpCN9f1k15Oc3PppOqYrc7x7qijfg%3D%3D)![This diagram shows a page table with a "valid-invalid" bit indicating whether each frame is currently in use (V) or not (i).](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/af8c1b93-7bc6-4047-81a6-6ade440d0fbe/images/68692e07a125463abc7f90c59c4a1e10.jpg?Expires=1747008079&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=bp0JTAudSLXK%2BtnhsGxVDRFCeyNhjbXlgvN2xjSsy6Z%2FvgdimDW5DPIdhKEmXSM5Ch2tYb5u9XbjdJuSTiokMg9UieGlrRbX7Z%2Fwbhu%2F6j5jVo%2B2tfMJJMkRuNYLSa9RHG5ExQRQyAC5MAYBb4r4uqxXjULwitlKIVs7nzeeJy%2Fqd%2Foi2lpq3JphOSldIxZlysqW%2FJrMRhFWrQM0Sp9xVt%2ByqFRM5zE0cQI9%2BdKT4QZoa%2BRR1wJFN0liXY9qOy8bumECbMchiptJgVKGO0UQ2iIczX3h%2FK14hBZD9ueF0kp0N1b%2Bz8cgKtnu1J9wrilVkw4NP3sWVZyYyVlrxjyNEA%3D%3D)

### Handling Page Faults

-   A page fault occurs when a program references a page that is not currently in memory, triggering the operating system to handle the fault.
-   The OS checks the page table for the valid-invalid bit; if the bit indicates the page is not in memory, it will find a free frame and load the page from secondary storage.
-   The page table is updated to reflect that the page is now in memory, and the instruction that caused the page fault is restarted.
-   The process of handling page faults involves several steps, including checking for invalid references and managing free frames.![This diagram illustrates the steps involved in handling a page fault, including a trap, page table lookup, finding a free frame in physical memory, bringing in the missing page from backing store, resetting the page table, and restarting the interrupted instruction.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/af8c1b93-7bc6-4047-81a6-6ade440d0fbe/images/21032f63edd7473eb8970ff562d805a8.jpg?Expires=1747008079&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=oFkjGu0H7XvKKyGVApN8eTrmlyjzNO63ycRZbOqa%2BSJMkTT1Wx20NJ5D8Zro0HNIarbLqmZDIaHciLUruMULaB%2BJLt8H9NU2Bl9o7WMVpx51Fo%2BzuCOJD7hCx1JJP7F%2BBUle8ztifMAUaPAZloxtFtkcz9dsM4QpDqtahVUEzpgqlpKOGBjaPMO41uSf6aUVbjZFPofHZ96E5P9eEGKhV7HVGXr3MfnGBCTc144Klt5Rycd6QOiggOaS2KVf7jkP2lyjg%2BPhFOnc%2B%2B5CecnwC1Fuuv%2FyTZX8nk1xE7goVtYtchCjD%2FPlpK3rRs%2F8eeYJNHLFmvQHou4GdjHod%2BhLhA%3D%3D)

# Page Replacement Algorithms

### Overview of Page Replacement

-   Page replacement algorithms are crucial for managing memory when a page fault occurs and there are no free frames available.
-   Common algorithms include FIFO (First-In-First-Out), Optimal, and LRU (Least Recently Used), each with different strategies for selecting which page to replace.
-   FIFO replaces the oldest page in memory, while Optimal replaces the page that will not be used for the longest period in the future.
-   LRU keeps track of page usage over time and replaces the least recently used page, balancing performance and memory efficiency.![This diagram illustrates the page replacement process in memory management, showing how a victim page is swapped out of physical memory and replaced with a desired page, updating the page table accordingly.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/af8c1b93-7bc6-4047-81a6-6ade440d0fbe/images/c10e1e72a05841b89e759ca24a2e0036.jpg?Expires=1747008079&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=kWR39hONOON8bx1KORNFW7A110wh%2FDcWGNTyfR0rDRdIP3o5RvGhYtOYc09v%2F25mVXPfCuJWz8yDEkaxKplRUO8AdrJzCOc2%2BZT7Bc3OiXdb5p6yKUXwPN7OVGdDLZ8K0kcmQapB0nArhlv98ANPMsKvtdH8TX3f%2BBpluxje7c78UmLN7UfcO7%2BuvGe0NCWsGp77YralULtZiDOOnUuum%2BKyMDS%2FjT57GcV1sXSnp4oOk4ZxGdGqljtWyC35ePtGdejBnujCOY6HOweCVgpjWSICLPSAKyoJs%2FjwYh%2FOW7zw8h4b1FTjbyAERLFHuNjUACEi%2Bg2%2BdEwwc9cAsV2iOQ%3D%3D)

### Working Set Model

-   The working set of a process refers to the set of pages that are actively used by the process at any given time, which is related to program locality.
-   Understanding the working set helps in optimizing memory allocation and reducing page faults by ensuring that frequently accessed pages remain in memory.
-   The concept of locality of reference indicates that programs tend to access a relatively small set of pages repeatedly over time, which can be leveraged for efficient memory management.![A graph shows the decreasing number of page faults as the number of frames increases, illustrating the relationship between memory allocation and program efficiency.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/af8c1b93-7bc6-4047-81a6-6ade440d0fbe/images/3b03b3ac1b024d999b6a71a4d9acef45.jpg?Expires=1747008079&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=NrM%2FLIv7b1vxRtG%2FQ6PKCB5t9AYIUcO8igFL0ve3U6sg5qfi2rupbBSDNPtX6I9J5s5rRxdNCka9PkMZZiMUW238fJZUnKjfV5aRXfWHu0ONbrG%2BaNG1TZgNdXJzUAekDIzGBuMZZnHt6eqQkCEMt6VLIRCJraQ0378WMNOziJ482xhbWsyp2oP2BRK08sp%2FXz830PA%2BXD2xI4LwypHcf266%2BprnUHY9SoZ2FND7noHwTIrSP3mMGJbB%2BXovjy%2BTpgHpiFGExmcWze0i2ccBwkNnJZEJw5FFsWz6mDWauFvl7gMjmPWq6frc8DGs9u3Qmpzz%2FF9QGsNOmt3LRcy2Lw%3D%3D)

### Need for Page Replacement

-   Page replacement is necessary when there are no free frames available for new pages, requiring the system to select a victim page to evict.
-   The performance of page replacement algorithms is critical to minimizing page faults and optimizing memory usage.![This diagram illustrates a page replacement algorithm, showing a reference string and how page frames are allocated and replaced using a specific algorithm (likely FIFO or LRU).](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/af8c1b93-7bc6-4047-81a6-6ade440d0fbe/images/84a574735fbd4bfaac9fa30b6689ee4e.jpg?Expires=1747008079&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=g3bSAxfPhWqlJbyaT%2F%2BXsnO%2FciLl%2Bkv9nf3nG%2BLQMQeshhUalIsXrbmff0CnzZlVj16YSourbZ99wehJBx4cwGs0XXG9GUZxITFTn%2BX1fdN1UqrWR4P3ULIjH28CbEPrlafsOeSwW7uwaNT5JNVrxduQC2y7GeXtqR%2B2KyGck%2Ba0VkGiFjPahaXGnqvG0gUcTKuFN0E61SsuHZ0qA4lDlGewhw4M7jdBTwDgAgohKXKg5now1PIU6v3CrJHB0UKwywPiulJd8WHVqggLUiLg8sR39YOf2haOVR9TgQKMLIdh5m1vyKsSXMGT8PhTzgXjKzSSBJgyEcMSH0NVhSxLjA%3D%3D)![This diagram illustrates a page replacement algorithm, showing a reference string and how page frames are allocated and replaced.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/af8c1b93-7bc6-4047-81a6-6ade440d0fbe/images/9c98211816374906b47e10ee624dc6f1.jpg?Expires=1747008079&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=beHdyq%2F0uxPkJKBQ29dw1m%2FSelfYyA0vZVD8sRUXzJYhFuj5Azm9YjAObo6L6VmuE%2FI1sndaqFEjtrmWkvf2gy4wtDu%2FapwSbarAyBKCQWmMqH789rSHU6AUqxLzHzEe8ROMy8VLZAe9UJhPP%2F%2BnhQtbHEWz%2BoeEP95t%2Bl96GK3WmPSk%2Fcs2uvVz32ofAVn54SoFxy%2BE7sqaTN3UddkjQAcHOqOHX77PqW8%2BQr4erP8wxzuULUs5PcRRH7s7SA9%2Bl%2FoDA%2FMl%2FusMLe%2F17dlqv5cKc%2Fvg73fmxXptFQ7J1AqCv%2BPuIc%2BKZWWiJkGUS%2FsKG5OE3BqZuZznuwAkNZuLbA%3D%3D)

### Basic Page Replacement Process

-   The process involves finding the desired page on disk, locating a free frame, and potentially writing a dirty page back to disk before loading the new page.
-   The page and frame tables must be updated to reflect the changes in memory allocation.![Diagram showing a reference string of numbers and their corresponding page frames in a memory management system.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/af8c1b93-7bc6-4047-81a6-6ade440d0fbe/images/a71447d353cf4cc89420151ddb897863.jpg?Expires=1747008079&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=WhlPI%2BGDfQAmGUT3D3antATq0zEVJi7bCbxm2U4mPJOjgGFXVZCpkUhLgv2fIjZ%2BuOihkczubd2ohLZUGhK53AeKDQUyCAHZCOQLs6eABWLmlmM2AvaXoCyXPJvZuOiwBH69oOcKo9PGPXdXyJeEfTJSsze%2FaHbjV8eHzXXHIyO17cyXStzRlPwDM6Z6ofl0%2BMID40JIc2Aqr1b%2FwqSZWjvVZbCp6HlnxjOdAX23v9WSH8iSmYPIsDcu1TPxC1uE0aV%2FzqHFF4s1ICk1bVIipMeAmjdeU1RbykYo25%2BGW0iVWVo980i63KMbGWNZzkBMLQo%2FKlUqWCeP61PXGEi02g%3D%3D)

# Operating System Implementations

### Virtual Memory Management in Different OS

-   Linux, Windows 10, and Solaris each have unique approaches to managing virtual memory, reflecting their design philosophies and target use cases.
-   Linux uses a combination of demand paging and a page replacement algorithm to manage memory efficiently, with support for shared memory and memory-mapped files.
-   Windows 10 employs a similar demand paging strategy, with additional features for managing memory across multiple applications and processes.
-   Solaris implements advanced memory management techniques, including the use of a virtual memory manager that optimizes performance based on workload characteristics.![This diagram illustrates a virtual memory system with two processes, showing logical memory, page tables, physical memory, and backing store, highlighting page mapping and potential page faults.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/af8c1b93-7bc6-4047-81a6-6ade440d0fbe/images/48d1152fd63847958fa466ae33a58eb2.jpg?Expires=1747008079&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=JRFTm04kqQRVPnB9GGueXJNtBQVa69t9JJXR7G4FmkbaFcpvrLZoDJJKBk2JBztCKZCK%2B8Jtbjg44%2Fbg6zGIiheH8xcRcRjHnu4EJPyivE%2FyA%2Fst9C0%2FsHu68RiU5l0J7LMWabojgrOvG2FEdXaSH1M6g5YV9DPMEe1EEPQuwY4OFb6gU8K39LjBnjTg984QnF8%2Bel2Ik0bbZFAHbNSRwPNCrXPvFGL5U2khJMSeslC7Vgs1lUv7iUBZ%2B%2FUGXOmf59NBNT8PCQ7dqxsHvYbjlHt4YpcOZB2ie2GJ9wpPSpX94RATVCLSPpUNOadSKNrfmOYFwi%2B3PaXxwZe4%2FPwIVg%3D%3D)

### Kernel Memory Allocation

-   Allocating kernel memory is a critical aspect of virtual memory management, as the kernel requires memory for its operations and data structures.
-   Operating systems typically use a free-frame list to manage available memory frames, ensuring efficient allocation and deallocation of memory resources.
-   The zero-fill-on-demand technique is often used, where newly allocated frames are initialized to zero, preventing data leakage between processes.
-   Proper management of kernel memory is essential for system stability and performance, as it directly impacts the overall efficiency of the operating system.![A graph shows how the kernel suspends and resumes reclaiming pages based on minimum and maximum free memory thresholds.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/af8c1b93-7bc6-4047-81a6-6ade440d0fbe/images/a8d5b7d7a3f3481da23a27d0bbcb3edc.jpg?Expires=1747008079&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=lt%2BhrDSrjNrGssfOPleb1%2FppJeBqGmPdQY3rZBd7DAv2xJ7Z8u2OB2SuTmGnSuOQgo%2B44uRUE5%2BphKjEO4%2BAPk3HrdXMv7KN4vELIUe6liD4A59OoKQac8IVaof%2F2NvqUL%2BUFeDnhL1LZPF%2B6Zkjxr40%2FMtNpgbj%2BFyPCgpP5iY43jY4Wf9tAj7ypmlMT3RN9vKJIGVbqRdMYN5MA9sk6cI8f%2F9D5W6E8TUj%2FEk7lHGMbIa5ievWlkSSVhy21l%2BSXjRUO1BRopPJvE01GXiUZd62txDdqDzGS57Ecqx6MtLYdT%2Fe9TMrUUvLHXA8OrPd4DW%2FdaFN39rMou7PctyuWg%3D%3D)

# Stages in Demand Paging

### Overview of Demand Paging Stages

-   Demand paging is a memory management scheme that loads pages into memory only when they are needed, reducing memory usage and improving efficiency.
-   The process begins with a trap to the operating system when a page fault occurs, indicating that the required page is not in memory.
-   The operating system saves the current process state and registers before handling the page fault, ensuring that the process can be resumed later.![A graph illustrates how CPU utilization increases with the degree of multiprogramming until it reaches a peak, after which it sharply decreases due to thrashing.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/af8c1b93-7bc6-4047-81a6-6ade440d0fbe/images/6dec197f595a4f24a6eda54860e5507f.jpg?Expires=1747008079&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=r1PXcF3NaNLeuLMHqurOSwSvxZI%2BwndjPDKocC54wfGnEHc%2B7IcW60mOYwdZz6aVFS1napBImGknjd9EKVygkhe2tq0VoQrCcLbZqzO1Sjau%2FyJAp9YEORLP9hucUsKTnv8m06XoWjVd6zetzd66DhOtlskoKOTuKjGDZVYOGEPqIsw1Ur6BoU0RV89Kan5LbZEGgxsV3ut8kwt75Hn6NegBfg0k8rPxcu0WcJcZrllPFosqY7UiZu2d71BJqDRJPSyllzaykn1ZlEHc5IGRWBzfoy%2B9dUm2DoOKu6NKvKcKbtgJ4YvdIC52AOEoPF%2BYy47k125bKO%2F6ghzkWqY2WQ%3D%3D)

### Detailed Steps in Demand Paging

-   The operating system checks if the page reference is legal and determines the location of the page on the disk.
-   A read request is issued to transfer the page from disk to a free frame in memory, which may involve waiting for the disk I/O to complete.
-   Once the page is read into memory, the page table is updated to reflect the new location of the page, allowing the process to resume execution.![Diagram of a distributed memory multiprocessor system with four CPUs, each connected to its own memory module and interconnected with each other.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/af8c1b93-7bc6-4047-81a6-6ade440d0fbe/images/cb5a42deb303486db3dbd66a9abcff63.jpg?Expires=1747008079&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=tly6kP%2Frxyt0ZghJzFfpptH9enw9DrswzhZT%2FsxWdqCKoNoazX0rfntpcmHLCU%2BQvY4lAqxn7qg3Y%2B9o9q9DoU68MbR1yCwuJcFAXeO4Qd5r6hgxdjBh62nYvKxgPcZF2uv3%2FZQTiwoz3b6Eg%2FY8ooXx2B24hnbgx%2B2%2BLaAPPqIRANa0fDMlIDUnfdW3%2BlY%2Fb9PtQ8UFh2F4DVPa3mH4yz9lEATk%2BErN1cIWeOPcqZs8JJ%2F3div9G1XgjI3fSE2WGxkOgk954Z%2FXL2Shjwy%2BO6J23bnkzxxzquiJw%2BgzHVIrIpcKFYrx4ff%2Bkx7dkVwPjaN7FJkhd%2FOxADTt5j04tA%3D%3D)

# Performance of Demand Paging

### Key Performance Metrics

-   The performance of demand paging is evaluated based on the page fault rate (p), which ranges from 0 (no faults) to 1 (every reference is a fault).
-   Effective Access Time (EAT) is calculated using the formula: EAT = (1 - p) x memory access time + p x (page fault overhead + swap page out + swap page in).
-   A high page fault rate significantly increases the EAT, leading to performance degradation.![This diagram illustrates a page reference table showing two sliding windows, WS(t₁) = {1,2,5,6,7} and WS(t₂) = {3,4},  with their respective positions indicated on a numerical sequence.](https://storage.googleapis.com/qzlt-prod-services-notes-notes-data/af8c1b93-7bc6-4047-81a6-6ade440d0fbe/images/3379fd5f405a49dfb79688a2272f2317.jpg?Expires=1747008079&GoogleAccessId=notes-svc%40qzlt-prod-webapp.iam.gserviceaccount.com&Signature=TWy%2F9ULjp49ePzZbQYO1d3ArMYFots4ksee4kNG5tgpUS3Q%2F7oGqXzYDKUkkKlcn367GExopLsMHHcY9RKdzjTy%2BsyL4OE2h3P0S5ELpK3CxEqoE07QyS1sP1vHO4PFBijuJuJR4sRuai03fZ3B7OuL9TDhFbHENFPIIRzfTMWKq3ulZNggE4%2Bnd0V7MzIjLgUF7%2FdCm0wud6euPixQ8msWazG%2FyE5zM6uqfnNoYPtzRADrNDJ4agA1tfmxTj9aKbipVWZ9VCz1L23LNm7rBvcxz7liveSbJhgG0uGIRPxWsrz3QIcn02LdI%2BCk9LUEmKAd9D0oy0Tcpy5wPJbMtWw%3D%3D)

### Example Calculation of EAT

-   For a memory access time of 200 nanoseconds and an average page-fault service time of 8 milliseconds, the EAT can be computed as follows:

```plaintext
EAT = (1 - p) x (200 ns) + p x (8,000,000 ns)

```

-   If one access out of 1,000 causes a page fault, the EAT becomes 8.2 microseconds, indicating a slowdown by a factor of 40 due to demand paging.

# Demand Paging Optimizations

### Techniques for Improving Demand Paging

-   Swap space I/O is generally faster than file system I/O, allowing for more efficient page management.
-   Copy-on-Write (COW) allows parent and child processes to share pages until a modification occurs, reducing memory usage during process creation.
-   Mobile systems often do not support swapping and instead demand pages from the file system, reclaiming read-only pages when necessary.

### Memory Management Strategies

-   The system should maintain a pool of zero-fill-on-demand pages to ensure quick allocation for demand paging.
-   Pages that are modified in memory but not yet written back to the file system are referred to as anonymous memory, which requires careful management.

# Evaluation of Page Replacement Algorithms

### Performance Metrics and Analysis

-   The effectiveness of page replacement algorithms is evaluated based on the number of page faults that occur during execution.
-   Different reference strings can yield varying results, highlighting the importance of the chosen algorithm and the number of frames available.

### First-In-First-Out (FIFO) Algorithm

-   The FIFO algorithm replaces the oldest page in memory, which can lead to Belady’s Anomaly, where adding more frames results in more page faults.
-   An example reference string demonstrates how the FIFO algorithm can lead to 15 page faults with three frames available.

### Optimal Page Replacement Algorithm

-   The optimal algorithm replaces the page that will not be used for the longest period of time, providing the best theoretical performance.
-   However, implementing this algorithm requires future knowledge of page references, making it impractical in real-world scenarios.

# Overview of Page Replacement Algorithms

### Introduction to Page Replacement

-   Page replacement algorithms are crucial for managing memory in operating systems, especially when physical memory is limited.
-   These algorithms determine which memory pages to swap out when new pages need to be loaded into memory.
-   The performance of these algorithms is often measured by the number of page faults that occur during execution.

### Least Recently Used (LRU) Algorithm

-   LRU uses historical data to make decisions about which page to replace, specifically targeting the page that has not been used for the longest time.
-   It can be implemented using two main methods: counter implementation and stack implementation.
-   LRU is generally more efficient than FIFO but less efficient than the optimal page replacement algorithm (OPT).

### Implementation of LRU

-   **Counter Implementation**: Each page entry has a counter that records the time of last use. When a page needs to be replaced, the page with the smallest counter value is selected.
-   **Stack Implementation**: A stack of page numbers is maintained, where the most recently used pages are at the top. This method requires more pointers to manage but eliminates the need for searching during replacement.

### LRU Approximation Algorithms

-   Due to hardware limitations, LRU can be slow; thus, approximation algorithms are used to simplify the process.
-   **Reference Bit**: Each page has an associated reference bit that is set when the page is accessed. Pages with a reference bit of 0 are candidates for replacement.
-   **Second-Chance Algorithm**: A modified FIFO approach that checks the reference bit before replacing a page, giving pages a 'second chance' if they have been recently used.

# Advanced Page Replacement Strategies

### Enhanced Second-Chance Algorithm

-   This algorithm improves upon the second-chance algorithm by using both reference and modify bits to make more informed replacement decisions.
-   Pages are categorized into four classes based on their reference and modify bits, allowing for a more nuanced approach to page replacement.

### Counting Algorithms

-   Counting algorithms track the number of references to each page, with two main types: LFU (Least Frequently Used) and MFU (Most Frequently Used).
-   LFU replaces the page with the smallest reference count, while MFU assumes that the page with the smallest count is likely to be less useful.

### Page-Buffering Algorithms

-   These algorithms maintain a pool of free frames to reduce the penalty of page faults by preloading pages into memory.
-   They can also keep track of modified pages to optimize write operations to disk, enhancing overall system performance.

# Memory Management Techniques

### Frame Allocation Strategies

-   Each process requires a minimum number of frames to operate effectively, with two primary allocation schemes: fixed and priority allocation.
-   **Fixed Allocation**: Equal allocation of frames among processes, ensuring each has a fair share of memory resources.
-   **Proportional Allocation**: Allocates frames based on the size of each process, allowing for dynamic adjustments as process sizes change.

### Global vs. Local Allocation

-   **Global Replacement**: Allows processes to select replacement frames from the entire pool, which can lead to higher throughput but inconsistent performance.
-   **Local Replacement**: Each process only replaces pages from its allocated frames, ensuring more consistent performance but potentially underutilizing memory.

### Reclaiming Pages

-   This strategy involves proactively managing memory by triggering page replacement when free frames fall below a certain threshold, ensuring sufficient memory is always available for new requests.

# Performance Issues in Memory Management

### Non-Uniform Memory Access (NUMA)

-   NUMA architectures have varying access speeds to memory, which can impact performance significantly.
-   Optimal performance is achieved by allocating memory close to the CPU that is executing the thread, reducing latency.

### Thrashing

-   Thrashing occurs when a process does not have enough pages, leading to excessive page faults and low CPU utilization.
-   It can be mitigated by using local or priority page replacement strategies to manage memory more effectively.

### Working-Set Model

-   The working-set model helps manage memory by tracking the set of pages that a process is currently using, defined by a fixed number of recent page references.
-   If the total demand for frames exceeds available memory, the system can suspend or swap out processes to alleviate thrashing.

# Page Fault Management

### Page-Fault Frequency (PFF)

-   PFF is a metric used to determine the efficiency of memory management in operating systems. It establishes an acceptable rate of page faults that a process can experience without degrading performance.
-   If the actual PFF is lower than the acceptable rate, the process may lose memory frames, which can lead to performance issues.
-   Conversely, if the PFF is higher than acceptable, the process gains additional frames to accommodate its memory needs.
-   This approach is more direct than the Working Set Strategy (WSS), which focuses on the recent history of page accesses.
-   The local replacement policy is employed to manage frames based on the PFF, allowing for dynamic adjustments to memory allocation.

### Working Sets and Page Fault Rates

-   The working set of a process refers to the set of pages that are actively used by the process at any given time.
-   There is a direct relationship between the size of the working set and the page-fault rate; as the working set increases, the page-fault rate typically decreases.
-   The working set is not static; it changes over time, exhibiting peaks and valleys based on the process's execution behavior.
-   Understanding the working set is crucial for optimizing memory allocation and minimizing page faults.
-   Monitoring the working set can help in adjusting the PFF to maintain system performance.

# Memory Allocation Strategies

### Kernel Memory Allocation

-   Kernel memory is treated differently from user memory, often allocated from a free-memory pool to ensure efficient management.
-   Memory requests from the kernel can vary in size, and some structures require contiguous memory allocations, particularly for device I/O operations.
-   The allocation strategy must consider the need for both contiguous and non-contiguous memory to optimize performance.
-   Kernel memory management is critical for system stability and performance, as it directly impacts the operating system's ability to handle processes.

### Buddy System

-   The Buddy System is a memory allocation technique that uses fixed-size segments of physically-contiguous pages.
-   Memory is allocated in units that are powers of 2, which simplifies the allocation and deallocation process.
-   When a smaller allocation is needed than is available, the current chunk is split into two 'buddies' of the next lower power of 2, continuing until an appropriately sized chunk is available.
-   This system allows for quick coalescing of unused chunks into larger ones, but it can lead to fragmentation.
-   Example: A 256KB chunk can be split to satisfy a 21KB request, demonstrating the splitting process.

# Advanced Memory Management Techniques

### Slab Allocator

-   The Slab Allocator is an alternative memory management strategy that uses one or more physically contiguous pages to create caches for kernel data structures.
-   Each cache is dedicated to a unique data structure and is filled with objects that can be marked as free or used.
-   When a cache is full, new objects are allocated from an empty slab, and if no empty slabs are available, a new slab is created.
-   Benefits of the slab allocator include reduced fragmentation and fast memory request satisfaction, making it efficient for kernel operations.
-   The slab allocator in Linux has evolved from the original SLAB to include SLOB and SLUB allocators, each optimized for different memory conditions.

### Performance of Demand Paging

-   Demand paging is a memory management scheme that loads pages into memory only when they are needed, reducing the initial load time of processes.
-   The worst-case scenario for demand paging involves multiple stages, including trapping to the OS, saving process state, and waiting for disk I/O to complete.
-   The performance of demand paging can be affected by the page fault rate, which is influenced by the working set of processes and the efficiency of the page replacement algorithm.
-   Memory compression is a technique that allows multiple frames to be compressed into a single frame, reducing the need for paging and improving memory usage efficiency.
-   Priority allocation schemes can be used to manage page replacement based on process priorities, ensuring that higher-priority processes retain their memory frames.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMxMzA4ODE3OSw4NjIyODI4NjVdfQ==
-->