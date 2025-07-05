# 🗂️ Hierarchical Virtual Memory Management System
This project implements a virtual memory management system in C++ using hierarchical page tables. It simulates the core functionality of virtual memory in modern operating systems, including virtual-to-physical address translation, efficient memory management, page swapping, and eviction.

The project was developed as part of an Operating Systems course and focuses on low-level memory management without dynamic memory allocation, requiring meticulous handling of memory structures.

## 🚀 Key Features
Hierarchical Virtual Address Translation
Multi-level page table traversal for efficient virtual-to-physical mapping.

Page Fault Handling & Swapping
Dynamically loads and evicts pages as needed when memory constraints occur.

Custom Page Replacement Algorithm
Uses a cyclical distance heuristic to select pages for eviction based on memory access patterns, minimizing the impact on frequently accessed data.

Zero Dynamic Memory Allocation
The system operates entirely within a fixed-size simulated physical memory without using new, malloc, or any dynamic allocation.

Efficient Memory Search with DFS
Implements depth-first search to quickly find available frames and locate candidates for eviction.

Comprehensive Testing
Includes a pre-written test case (SimpleTest.cpp) to verify system correctness.

## ⚙️ How It Works
Memory Initialization
The simulated physical memory is divided into fixed-size pages and frames, with frame 0 reserved for the root of the page table hierarchy.

Address Translation
Virtual addresses are resolved by traversing multiple levels of page tables, efficiently mapping virtual pages to physical frames.

Page Fault Handling
If a requested page is not present in memory, the system either allocates a free frame (if available) or evicts a page using the custom replacement strategy.

Page Swapping & Eviction
When memory is full, the system evicts the page that is "farthest" in cyclical memory distance from the most recent access, helping preserve locality.

## 🗂️ Project Structure
File	Description
VirtualMemory.h	API for virtual memory operations
VirtualMemory.cpp	Virtual memory management implementation
PhysicalMemory.h	API for simulated physical memory
PhysicalMemory.cpp	Simulated physical memory (read/write logic)
MemoryConstants.h	Constants for memory sizes and structure
SimpleTest.cpp	Provided test case for system validation

## ✅ Testing
Test Provided: SimpleTest.cpp
This test case was provided as part of the assignment and was not written by me, but it is useful to verify the correctness and expected behavior of the system.

## To Run the Test:
Tests are included in the CMake setup but are commented out by default.
👉 To enable a test, simply uncomment the relevant test file in CMakeLists.txt before building the project.
