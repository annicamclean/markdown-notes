# Chapter 12 Study Guide
# FILL IN
### **Overview of I/O Systems**

1.  I/O management is a critical component of __________ design and operation.
    
2.  The I/O subsystem must adapt to new types of __________.
    
3.  Ports, buses, and device __________ serve as the primary means of connecting and managing I/O devices.
    
4.  __________ drivers provide a uniform interface for the OS to interact with hardware.
    
5.  Effective performance management of I/O operations is essential for optimizing system __________ and responsiveness.
    

----------

### **I/O Hardware**

**Categories of I/O Devices**  
6. I/O devices are categorized into storage, __________, and human-interface devices.  
7. Storage devices are critical for data __________.  
8. Transmission devices facilitate __________, and human-interface devices enable user __________.

**Ports and Buses**  
9. A __________ serves as a connection point for I/O devices.  
10. The __________ bus is a common interface in PCs and servers.  
11. SAS stands for __________ and is a common disk interface.

**Device Controllers**  
12. Device controllers manage communication between the __________ and I/O devices.  
13. Controllers contain __________, microcode, and __________.  
14. Registers used include data-in, data-out, __________, and control registers.

----------

### **I/O Operations and Performance**

**Polling vs. Interrupts**  
15. Polling involves the CPU repeatedly checking the __________ bit.  
16. Interrupts allow devices to __________ the CPU when ready.  
17. The interrupt-driven approach improves system __________.

**Interrupt Management**  
18. An __________ handler processes interrupts.  
19. Interrupts can be __________ or non-maskable.  
20. The __________ vector maps requests to their handlers.  
21. __________ switching allows the CPU to save and restore process states.

----------

### **Interrupt-Driven I/O Cycle**

22.  Interrupts allow the CPU to perform other __________ while waiting for I/O.
    
23.  A __________ fault is an example of an interrupt-triggered event.
    
24.  macOS can generate around __________ interrupts in 10 seconds.
    

----------

### **Direct Memory Access (DMA)**

25.  DMA allows I/O devices to transfer data directly to and from __________.
    
26.  The DMA controller uses a __________ block specifying source, destination, and byte count.
    
27.  __________ stealing allows DMA to access the bus when the CPU is idle.
    

----------

### **Characteristics of I/O Devices**

28.  Block devices support operations like read, write, and __________.
    
29.  Character devices use commands like __________ and put().
    
30.  The Unix ioctl() call sends arbitrary __________ commands to devices.
    
31.  UNIX identifies devices using a tuple of __________ and minor numbers.
    

----------

### **Kernel I/O Subsystem**

32.  Kernel I/O services include scheduling, __________, caching, and error handling.
    
33.  __________ stores data temporarily during transfers.
    
34.  __________ keeps frequently accessed data in fast storage.
    
35.  Spooling is used when devices can only handle __________ request(s) at a time.
    

----------

### **I/O Performance Considerations**

36.  Reducing __________ switches and data copying enhances performance.
    
37.  STREAMS provide a structured way to manage __________ between processes and devices.
    
38.  Performance metrics like storage and __________ latency are key for I/O efficiency.
    

----------

### **Power Management in I/O Systems**

39.  Power management is crucial in __________ and cloud computing.
    
40.  Android uses __________-level power management.
    
41.  __________ locks prevent devices from sleeping prematurely.
    
42.  The __________ (ACPI) standard manages device power states.
    

----------

### **Advanced I/O Techniques**

**Nonblocking & Asynchronous I/O**  
43. Nonblocking I/O returns __________ with available data.  
44. Asynchronous I/O allows the OS to __________ when an operation completes.  
45. Multi-threading can support __________ I/O operations.

**Vectored I/O**  
46. Vectored I/O uses a single system call to handle __________ I/O operations.  
47. The Unix __________ function accepts a buffer vector.  
48. Vectored I/O is especially useful in __________ environments.

**Error Handling & Protection**  
49. The OS may retry failed operations to recover from __________ errors.  
50. All I/O must go through __________ calls to ensure safety.  
51. I/O protection prevents user processes from executing illegal __________ instructions.
# ANSWER

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgwMjE5NDgxLC0xMjU4NjA2OTAxXX0=
-->