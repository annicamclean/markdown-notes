# Chapter 13 Study Guide

# FILL IN
### 1.1 Overview of File Systems

-   Information is stored on various __________ media.
    
-   The OS provides a __________ logical view of stored information.
    
-   A file is defined as a logical __________ unit.
    
-   The OS maps files onto physical __________.
    
-   This organization enables structured data __________ and retrieval.
    

### 1.2 Types of Files

-   Files can be categorized as: __________, __________, character files, binary files, and __________ files.
    
-   Examples include: __________ files, source files, and __________ files.
    
-   Understanding file __________ is crucial for handling and processing.
    

### 1.3 File Attributes

-   Common file attributes include: __________, identifier, __________, location, size, protection, and __________.
    
-   The only human-readable attribute is the __________.
    
-   The __________ is a unique tag in the file system.
    
-   __________ attributes control who can read, write, or execute a file.
    

### 1.4 Directory Structure

-   A directory structure is a collection of __________ containing file information.
    
-   Both files and directories reside on the __________.
    
-   Newer systems include extended attributes like file __________ for data integrity.
    

----------

## **2. File Operations**

### 2.1 Basic File Operations

-   Basic operations: create, open, read, __________, reposition, delete, and __________.
    
-   The open operation searches the __________ structure.
    
-   The close operation writes any changes back to __________.
    

### 2.2 Open Files Management

-   Open files are tracked using an __________ table and file pointers.
    
-   A file pointer marks the last **********/********** location per process.
    
-   __________ rights are essential for file operation security.
    

### 2.3 File Locking Mechanisms

-   File locking controls __________ to files across processes.
    
-   Two types of locks: __________ (reader) and __________ (writer).
    
-   __________ locks enforce strict access denial, while __________ locks are cooperative.
    

----------

## **3. Access Methods**

### 3.1 Sequential Access

-   In sequential access, you can read/write the __________ item in order.
    
-   Reading after the last write is __________.
    
-   This method is __________ but not always efficient.
    

### 3.2 Direct Access

-   Direct access uses __________ block numbers.
    
-   It allows random access by directly reading or writing to __________ blocks.
    
-   Ideal for fixed-length __________ records.
    

### 3.3 Other Access Methods

-   Indexes allow faster __________ of data.
    
-   When too large, multilevel __________ is used.
    
-   An example is IBM's __________ system for sorted files.
    

----------

## **4. Directory Structure**

### 4.1 Directory Organization

-   Directory structures allow for better file __________ and naming.
    
-   Users can have files with the same __________.
    
-   Files can also have multiple __________.
    

### 4.2 Directory Operations

-   Common operations: __________ for files, creating, __________, listing, and renaming.
    
-   Directory __________ is essential for file system performance.
    

### 4.3 Directory Structures

-   __________-level directories are simple but limited.
    
-   __________-level directories allow each user a separate space.
    
-   __________-structured directories support hierarchy.
    
-   __________ graphs allow shared files between directories.
    

----------

## **5. Protection**

### 5.1 File Protection Mechanisms

-   Access types: read, write, execute, __________, delete, and __________.
    
-   ACLs define access for __________, __________, and __________ users.
    
-   Access modes are represented in __________ form.
    

### 5.2 Access Control in Unix

-   Unix uses three access classes: owner (_**), group (**_), public (___).
    
-   Permissions are modified using the __________ command.
    
-   Understanding permission levels ensures file __________.
# ANSWER
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAyODE1MjU4LC03NzEzMjQ4MzNdfQ==
-->