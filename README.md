# 🧠 Heap Management System

> **Manual memory management in C — learn how dynamic memory allocation really works under the hood.**

---

## 📘 Overview
The **Heap Management System** is a simple, educational implementation of manual heap memory management in C.  
It mimics how low-level allocators work — handling block allocation, deallocation, splitting, and coalescing — without using `malloc()` or `free()`.

This project demonstrates **how to design and manage your own heap**, and provides a hands-on understanding of:
- Memory fragmentation
- Block metadata tracking
- Dynamic memory partitioning and merging

---

## ✨ Features
- 🔹 Manual heap block allocation and deallocation  
- 🔹 Tracking of **free** and **used** blocks  
- 🔹 Splitting large blocks into smaller ones during allocation  
- 🔹 Coalescing adjacent free blocks during deallocation *(if implemented)*  
- 🔹 Simple, educational example to understand heap internals  

---

## ⚙️ How It Works
1. A contiguous memory region is reserved (via `sbrk()` or a static array).  
2. The heap is divided into **blocks**, each with metadata:  
   - `size`  
   - `status` (free or used)  
3. **Allocation:**  
   - Find the first free block large enough for the request.  
   - If it’s larger than required, split it into two: one used, one free.  
   - Mark the used block and return a pointer to its payload.  
4. **Deallocation:**  
   - Mark the block as free.  
   - Optionally, merge with adjacent free blocks (coalescing).  
5. Over time, you can observe **fragmentation** and **free list evolution**.

---

## 🧩 File Structure

HeapManagement/

├── HeapManagement.c # Core implementation and demo (main function)

└── README.md # Project documentation


---

## 🚀 Getting Started

### 🧱 Prerequisites
- C compiler: `gcc` or `clang`  
- Unix-like shell / Windows command prompt  
- Basic knowledge of pointers and dynamic memory concepts  

---

### 🛠️ Compilation
Compile using:
```bash
gcc HeapManagement.c -o heap_manager
