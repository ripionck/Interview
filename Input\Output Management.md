## 💾 I/O Devices  
**Types of I/O Devices**:  
1. **Block Devices**  
   - Transfer data in fixed-size blocks (e.g., 512 bytes).  
   - *Examples*: Hard drives (HDD), SSDs, USB drives.  
   - *Use Case*: Storage with random access.  

2. **Character Devices**  
   - Transfer data as a stream of characters/bytes.  
   - *Examples*: Keyboards, mice, serial ports.  
   - *Use Case*: Real-time input/output.  

3. **Network Devices**  
   - Enable communication over networks.  
   - *Examples*: Ethernet cards, Wi-Fi adapters.  
   - *Use Case*: Data transmission (e.g., TCP/IP packets).  

---

## ⏳ I/O Scheduling (Disk Scheduling)  
Algorithms to optimize disk head movement and reduce latency:  

| **Algorithm** | **Description**                                  | **Pros**                     | **Cons**                     |  
|---------------|--------------------------------------------------|------------------------------|------------------------------|  
| **FCFS**      | Requests served in arrival order.                | Simple, fair.                | Poor performance (high seek time). |  
| **SSTF**      | Serves the nearest request first.                | Reduces seek time.           | Risk of starvation for distant requests. |  
| **C-SCAN**    | Scans requests in one direction, then resets.    | Fairer than SCAN; no starvation. | Increased latency for edge requests. |  

**Example**:  
- **C-SCAN**: Imagine a disk head moving from track 0 → 100, serving requests along the way, then jumping back to 0.  

---

## 🚨 Interrupt Handling  
**Interrupts**: Signals from hardware/software to alert the CPU (e.g., I/O completion, errors).  

**Interrupt Handling Process**:  
1. **Interrupt Occurs**: Device sends a signal to the CPU.  
2. **Save State**: CPU pauses the current task and saves its state.  
3. **Identify Interrupt**: Uses an **interrupt vector table** to locate the handler.  
4. **Execute Handler**: Runs the **Interrupt Service Routine (ISR)** to manage the event.  
5. **Restore State**: CPU resumes the paused task.  

**Types of Interrupts**:  
- **Hardware Interrupts**: Triggered by devices (e.g., keyboard press, timer).  
- **Software Interrupts**: Triggered by programs (e.g., system calls like `read()`).  

**Example**:  
- When a network packet arrives, the NIC raises an interrupt → ISR processes the packet.  

---

### Key Concepts:  
- **Direct Memory Access (DMA)**: Allows devices to transfer data directly to RAM, bypassing the CPU.  
- **Buffering**: Temporarily stores data in memory to handle speed mismatches (e.g., streaming video).  

---

Use this guide to understand I/O device types, scheduling trade-offs, and how interrupts enable efficient hardware-software interaction! 🖥️🔌
