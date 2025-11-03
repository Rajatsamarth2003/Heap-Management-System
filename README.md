Heap Management System

HeapManagement
Implementation of basic heap (memory) management in C

Table of Contents

- Overview 			- How it Works
- Features			- File Structure
- Getting Started		- Contributing
- Prerequisites			- License
- Compiling			- Contact
- Usage
Overview
This project is a simple demonstration of manual heap memory management in C. The file `HeapManagement.c` contains functions to allocate, deallocate and manage blocks on the heap. It aims to illustrate how you might implement your own heap manager (rather than relying solely on `malloc`/`free`) and understand memory fragmentation, block splitting/merging, etc.
Features
- Manual heap block allocation and deallocation
- Tracking of free and used blocks
- Splitting larger free blocks into smaller ones on allocation
- Coalescing adjacent free blocks on deallocation (if implemented)
- Simple demonstration suitable for educational purposes

Getting Started

Prerequisites
- A C compiler (e.g., `gcc`, `clang`)
- A Unix-like shell or Windows command prompt
- Basic understanding of C and memory concepts

Compiling
 
This will compile the `HeapManagement.c` file and produce an executable named `heap_manager`.

Usage
Once compiled, run the executable:
 
Depending on how you’ve set up the demo code (e.g., example allocations/deallocations inside `main()`), it will show you output related to heap operations — for example: block allocation, free list status, block splitting, merging, etc.

You could modify `main()` (or add new functions) to test more scenarios:
- Allocate multiple blocks of different sizes
- Free blocks in different orders
- Force fragmentation and then attempt allocation of a large block
- Observe how the free list changes

How it Works
1. A contiguous chunk of memory is reserved (e.g., via `sbrk()` or a static array) to serve as the “heap”.
2. The heap is partitioned into blocks. Each block has metadata (size, status: free or used).
3. On allocation:
   - The manager searches the free list for a block that fits the requested size.
   - If a free block is larger than needed, it may be split into a used block + a remaining free block.
   - Mark the chosen block as used and return a pointer to the user‑usable region.
4. On deallocation:
   - Mark the block as free.
   - Optionally: check neighbouring blocks and if they’re free, merge (coalesce) into a larger free block.
5. Over time, fragmentation can occur.
6. This code helps you see these principles in action.
File Structure
- `HeapManagement.c` — The main source file containing the heap manager implementation and a `main()` function demonstrating its usage.
Contributing
Contributions, issues and feature requests are welcome!
1. Fork the repository.
2. Create a new branch (`git checkout -b feature-yourfeature`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature-yourfeature`).
5. Open a pull request.
License
This project is open-source. Please see the `LICENSE` file (if present) for details.
Contact
Feel free to reach out for questions, suggestions or collaborations.
