## Interprocess Communication (IPC) & Synchronization

## 📨 IPC Mechanisms  
Methods for processes to communicate and share data:  

| **Mechanism**   | **Description**                                  | **Use Case**                     | **Pros/Cons**                               |  
|-----------------|--------------------------------------------------|----------------------------------|---------------------------------------------|  
| **Pipes**       | Unidirectional communication (parent ↔ child).   | Shell commands (`\|` operator).  | *Pros*: Simple. *Cons*: Limited to related processes. |  
| **FIFOs (Named Pipes)** | Bidirectional; persists beyond process life.  | Unrelated processes on the same machine. | *Pros*: Cross-process. *Cons*: Slower than pipes. |  
| **Shared Memory** | Processes access a common memory region.        | High-speed data sharing (e.g., databases). | *Pros*: Fast. *Cons*: Requires synchronization (e.g., semaphores). |  
| **Sockets**     | Network-based communication (TCP/UDP).           | Distributed systems (client-server apps). | *Pros*: Cross-machine. *Cons*: Overhead. |  

**Example (Python Pipes)**:  
```python  
import os  
r, w = os.pipe()  
pid = os.fork()  
if pid == 0:  
    os.write(w, b"Hello from child!")  
else:  
    data = os.read(r, 100)  
    print(f"Parent received: {data.decode()}")  
```  

---

## 🔄 Synchronization  
Tools to coordinate access to shared resources and prevent race conditions:  

| **Mechanism** | **Description**                                  | **Use Case**                     |  
|---------------|--------------------------------------------------|----------------------------------|  
| **Semaphores** | Integer counter for signaling (via `wait()`/`signal()`). | Limiting access to a resource pool. |  
| **Mutexes**   | Locks ensuring mutual exclusion (one thread at a time). | Protecting critical sections.    |  
| **Monitors**  | High-level abstraction (locks + condition variables). | Encapsulating shared data access. |  

**Key Concepts**:  
- **Deadlock**: Occurs when processes wait indefinitely for resources (e.g., circular dependencies).  
- **Starvation**: A process is denied access to a resource indefinitely.  

**Example (Semaphore in C)**:  
```c  
#include <semaphore.h>  
sem_t sem;  
sem_init(&sem, 0, 1); // Initialize semaphore with value 1  

sem_wait(&sem); // Enter critical section  
// Access shared resource  
sem_post(&sem); // Exit critical section  
```  

---

### Comparison of IPC Mechanisms  

| **Aspect**          | Pipes/FIFOs      | Shared Memory      | Sockets          |  
|----------------------|------------------|--------------------|------------------|  
| **Speed**            | Moderate         | Very Fast          | Slower (network) |  
| **Complexity**       | Low              | High (sync needed) | Moderate         |  
| **Scope**            | Local            | Local              | Network          |  

---

### Example (Shared Memory in C):  
```c  
#include <sys/mman.h>  
int fd = shm_open("/my_region", O_CREAT \| O_RDWR, 0666);  
ftruncate(fd, SIZE);  
char *ptr = mmap(NULL, SIZE, PROT_READ \| PROT_WRITE, MAP_SHARED, fd, 0);  
sprintf(ptr, "Shared data"); // Write to shared memory  
```  

---

**Key Takeaways**:  
- Use **pipes/sockets** for simple or distributed communication.  
- Use **shared memory** for high-speed data sharing (with synchronization).  
- **Semaphores/mutexes** prevent race conditions in critical sections.  

--- 

This section provides a quick reference for IPC strategies and synchronization techniques in OS development! 🔗🖥️
