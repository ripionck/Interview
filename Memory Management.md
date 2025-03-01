## 🧠 Memory Allocation Techniques  
**1. Contiguous Allocation**  
- Memory is allocated in a **single continuous block**.  
- **Pros**: Simple to implement.  
- **Cons**: Suffers from **external fragmentation** (free memory gaps) and inflexible sizing.  
- *Example*: Early systems like MS-DOS.  

**2. Paging**  
- Divides memory into fixed-size **pages** (e.g., 4 KB).  
- Uses a **page table** to map logical addresses to physical frames.  
- **Pros**: Eliminates external fragmentation; enables virtual memory.  
- **Cons**: Internal fragmentation (unused space in pages).  
- *Example*: Modern OS like Linux/Windows.  

**3. Segmentation**  
- Divides memory into **variable-sized segments** (code, data, stack).  
- Uses a **segment table** to track base addresses and lengths.  
- **Pros**: Reflects logical program structure; easier sharing/protection.  
- **Cons**: External fragmentation; complex management.  
- *Example*: Often combined with paging (e.g., x86 architecture).  

---

## 🌐 Virtual Memory  
**Key Concepts**  
- Allows processes to use **more memory than physically available** by storing inactive pages on disk.  
- Uses **demand paging**: Pages are loaded into RAM only when needed.  

**Page Faults**  
- Occurs when a process accesses a page **not in physical memory**.  
- **Handling**:  
  1. OS traps the fault.  
  2. Loads the page from disk to RAM.  
  3. Updates the page table.  
  4. Resumes the process.  

**Thrashing**  
- Severe performance degradation due to **excessive page faults**.  
- **Causes**: Over-allocating processes, insufficient RAM.  
- **Solutions**: Adjust process priority, increase RAM, or use better page replacement algorithms (e.g., LRU).  

---

## 🔄 Paging vs. Segmentation  

| **Aspect**          | **Paging**                          | **Segmentation**                |  
|----------------------|-------------------------------------|----------------------------------|  
| **Block Size**       | Fixed (e.g., 4 KB pages)           | Variable (logical units)         |  
| **Fragmentation**    | Internal (within pages)            | External (between segments)      |  
| **Address Translation** | Uses page table + offset         | Uses segment table + offset      |  
| **Use Case**         | Efficient physical memory use      | Logical program organization     |  

**Advantages**:  
- **Paging**: Simplifies memory management, avoids external fragmentation.  
- **Segmentation**: Aligns with programmer’s view, enables modular code.  

---

### Example (Paging in x86):  
```c  
// Logical address: [Page Number][Offset]  
// Page table maps to physical frame.  
uint32_t logical_address = 0x12345678;  
uint32_t page_number = logical_address >> 12;  // Assuming 4 KB pages  
uint32_t offset = logical_address & 0xFFF;  
```  

---

This section provides a quick reference for memory management concepts. Use it to understand allocation strategies, virtual memory, and trade-offs between paging and segmentation! 🖥️
