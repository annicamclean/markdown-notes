# Chapter 14 Study Guide
# FILL IN
### File-System Structure – Fill in the Blank

#### **Overview of File Structure**

1.  A file structure is a logical storage unit that organizes related information, allowing for efficient __________ management.
    
2.  The file system operates on __________ storage (disks), providing a user interface that maps logical storage to physical storage.
    
3.  It enables efficient access to data, allowing for easy __________, retrieval, and location of files.
    
4.  Disks support in-place rewriting and __________ access.
    
5.  I/O operations are performed in __________, typically 512 bytes.
    
6.  The __________ __________ __________ (FCB) contains metadata about a file.
    

#### **Layered File System Architecture**

7.  The file system is organized into __________ to enhance modularity and maintainability.
    
8.  __________ __________ operate at the I/O control layer.
    
9.  The basic file system translates commands like 'retrieve block 123' into actions performed by the device driver.
    
10.  __________ temporarily hold data in transit, while __________ store frequently accessed data.
    
11.  The __________ __________ module translates logical to physical block numbers.
    

#### **Logical File System Management**

12.  The logical file system manages __________, translating file names into file numbers.
    
13.  It also handles __________ management and file __________.
    
14.  __________ reduces complexity and redundancy but may introduce performance overhead.
    
15.  Examples of file systems include __________ (for CD-ROMs), __________ (for UNIX), and __________ (for Windows).
    

#### **File-System Operations**

16.  __________ __________ provide the interface for file system operations like open, read, write, and close.
    
17.  These are translated from high-level __________ calls.
    
18.  Common system calls include __________(), __________(), and __________().
    

#### **Directory Implementation**

19.  Directories are organizational units that allow hierarchical file __________.
    
20.  Directory entries usually contain the file name, file number, and __________.
    
21.  Common directory structures include __________ lists, hash tables, and __________ trees.
    

#### **Allocation Methods**

22.  Allocation methods determine how __________ are assigned to files.
    
23.  __________ allocation is fast but may cause fragmentation.
    
24.  __________ allocation avoids external fragmentation but may slow access.
    
25.  __________ allocation uses an index block with pointers to data blocks.
    

#### **Free-Space Management**

26.  Free-space management tracks available __________ blocks.
    
27.  Methods include __________, linked lists, and __________.
    
28.  A __________ offers compact representation, while linked lists may use more memory.
    
29.  Counting tracks the address and number of contiguous __________ blocks.
    

#### **Efficiency and Performance**

30.  Performance metrics include access time, __________, and latency.
    
31.  Optimization techniques include __________, prefetching, and __________.
    
32.  Workload analysis (e.g., read-heavy vs. write-heavy) helps tune system __________.
    

#### **Recovery**

33.  Recovery mechanisms include __________, checkpointing, and redundancy.
    
34.  __________ logs file changes for quick recovery.
    
35.  __________ saves the file system state periodically.
    
36.  __________ (e.g., RAID) adds hardware-level protection.
    

#### **WAFL File System**

37.  WAFL stands for __________ __________ __________ __________.
    
38.  It uses **********-**_-_********_ for data integrity and snapshot creation.
    
39.  WAFL is designed for fast access and __________ storage environments.
    

#### **On-Disk and In-Memory Structures**

40.  The Boot Control Block (BCB) contains the file system type and OS __________ location.
    
41.  The Volume Control Block (VCB), also called the __________, contains metadata like block count and free space.
    
42.  The File Control Block (FCB) includes __________ number, permissions, size, and timestamps.
    
43.  The Mount Table records file system __________ and mount types.
    
44.  The System-wide Open-File Table stores __________ for each open file.
    
45.  The Per-Process Open-File Table points to the __________ table.
    

#### **Directory Implementation Techniques**

46.  Linear lists are simple but require __________ search time.
    
47.  B+ trees improve search and insertion but use more __________.
    
48.  __________ tables speed up search but may suffer from collisions.
    

#### **Allocation Method Details**

49.  Contiguous allocation is fast but suffers from __________ fragmentation.
    
50.  __________ allocation links blocks in a chain and avoids external fragmentation.
    
51.  The __________ method uses a table that points to data blocks (e.g., FAT32).
    
52.  Indexed allocation allows __________ access using an index block.
    

#### **Advanced Indexed Allocation**

53.  Multi-level indexing supports large files with layers of __________.
    
54.  The outer index uses displacement Q1, and R1 retrieves __________.
    
55.  The two-level scheme supports files up to __________ GB and improves access time.
    

#### **Free-Space Management Techniques**

56.  A free-space __________ tracks available blocks using bits.
    
57.  A linked free-space list stores only __________ blocks.
    
58.  The __________ method records the address and count of contiguous free blocks.
    
59.  ZFS uses __________ maps and metaslabs for efficient space tracking.
    

#### **TRIM and Performance Optimization**

60.  TRIM informs the storage device that blocks are no longer in use and can be __________.
    
61.  NVM devices need to __________ blocks before reuse, making TRIM important.
    
62.  TRIM helps with __________ collection and overall performance.


# ANSWER
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY2NjcwMjA2MCw0ODkwODA0MzZdfQ==
-->