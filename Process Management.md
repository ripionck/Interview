## 🔄 Process States  
A process transitions through the following states during its lifecycle:  
- **New**: Process is being created.  
- **Ready**: Process is waiting to be assigned to the CPU.  
- **Running**: Instructions are being executed.  
- **Waiting**: Process is idle (e.g., waiting for I/O or an event).  
- **Terminated**: Process has finished execution.  

```
Example State Diagram:  
New → Ready → Running → (Waiting ↔ Ready) → Terminated  
```

---

## ⏳ Process Scheduling Algorithms  
Algorithms to determine which process gets CPU time next:  
1. **First-Come, First-Served (FCFS)**:  
   - Non-preemptive; processes are executed in arrival order.  
   - *Issue*: Convoy effect (long processes block short ones).  

2. **Shortest Job First (SJF)**:  
   - Prioritizes processes with the smallest burst time.  
   - Optimal for minimizing waiting time but requires prior knowledge of burst times.  

3. **Priority Scheduling**:  
   - Processes are assigned priorities (static or dynamic).  
   - *Risk*: Starvation of low-priority processes.  

4. **Round Robin (RR)**:  
   - Preemptive; allocates CPU time in fixed intervals (time slices/quantum).  
   - Fair but high context-switching overhead.  

---

## 🚫 Deadlocks  
**Conditions for Deadlock** (Coffman conditions):  
1. **Mutual Exclusion**: A resource is held by one process at a time.  
2. **Hold and Wait**: A process holds resources while waiting for others.  
3. **No Preemption**: Resources cannot be forcibly taken.  
4. **Circular Wait**: Processes form a cycle waiting for resources.  

**Handling Deadlocks**:  
- **Prevention**: Break one of the four conditions (e.g., enforce resource ordering).  
- **Avoidance**: Use algorithms like the **Banker’s Algorithm** to ensure safe resource allocation.  
- **Detection & Recovery**: Terminate processes or preempt resources.  

---

## 🧵 Threads  
Threads are lightweight units of execution within a process.  

### Types of Threads:  
1. **User-Level Threads (ULTs)**:  
   - Managed by user-space libraries (e.g., POSIX threads).  
   - *Pros*: Fast creation, no kernel involvement.  
   - *Cons*: Blocking one thread blocks all threads in the process.  

2. **Kernel-Level Threads (KLTs)**:  
   - Managed by the OS kernel.  
   - *Pros*: OS handles blocking and scheduling.  
   - *Cons*: Slower creation and context-switching.  

**Benefits of Multithreading**:  
- Improved responsiveness (e.g., UI remains active while a thread handles I/O).  
- Resource sharing (threads share memory and files).  
- Scalability across multicore systems.  

---

### Example Code (Multithreading in C):  
```c  
#include <pthread.h>  
#include <stdio.h>  

void* task(void* arg) {  
  printf("Thread ID: %ld\n", pthread_self());  
  return NULL;  
}  

int main() {  
  pthread_t t1, t2;  
  pthread_create(&t1, NULL, task, NULL);  
  pthread_create(&t2, NULL, task, NULL);  
  pthread_join(t1, NULL);  
  pthread_join(t2, NULL);  
  return 0;  
}  
```  

---

This section provides a quick reference for key concepts in process management. Use it alongside code examples or OS-specific implementations! 🖥️
