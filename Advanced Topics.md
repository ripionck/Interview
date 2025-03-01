## ⏱️ **Real-Time Systems**  
**Characteristics**:  
- **Timeliness**: Tasks must meet strict deadlines (deterministic behavior).  
- **Predictability**: Guaranteed response times for critical operations.  
- **Concurrency**: Handle multiple inputs/sensors simultaneously.  
- **Reliability**: Fault tolerance for mission-critical applications.  

**Types**:  
- **Hard Real-Time**: Zero deadline tolerance (e.g., airbag systems, pacemakers).  
- **Soft Real-Time**: Tolerates occasional delays (e.g., video streaming, VoIP).  

**Scheduling Algorithms**:  
| **Algorithm**          | **Description**                                  | **Use Case**               |  
|-------------------------|--------------------------------------------------|----------------------------|  
| **Rate-Monotonic (RMS)** | Static priority based on task frequency (shorter period = higher priority). | Periodic tasks (e.g., flight control). |  
| **Earliest Deadline First (EDF)** | Dynamic priority: earlier deadline = higher priority. | Dynamic workloads (e.g., robotics). |  

---

## 🔧 **Embedded Systems**  
**Types**:  
1. **Standalone**: No external host (e.g., microwave, digital watch).  
2. **Real-Time**: Time-sensitive operations (e.g., ABS in cars).  
3. **Networked**: Connected to a network (e.g., smart home devices).  
4. **Mobile**: Portable with power constraints (e.g., wearables).  

**Applications**:  
- Automotive (ECUs, infotainment), IoT sensors, medical devices (MRI machines), industrial automation.  

**Challenges**:  
- **Resource Constraints**: Limited CPU, memory, and power.  
- **Harsh Environments**: Temperature, vibration, and EMI resistance.  
- **Security**: Vulnerabilities in IoT devices.  
- **Long Lifecycles**: Maintenance and updates over decades.  

---

## 💽 **RAID Technology**  
**Goals**:  
- **Redundancy**: Protect against disk failures.  
- **Performance**: Speed up read/write operations.  
- **Capacity**: Combine disks into larger volumes.  

**Common RAID Levels**:  
| **RAID Level** | **Description**                  | **Pros**                     | **Cons**                     |  
|----------------|----------------------------------|------------------------------|------------------------------|  
| **RAID 0**     | Striping (no redundancy).        | High performance.            | No fault tolerance.           |  
| **RAID 1**     | Mirroring (duplicate data).      | Full redundancy.             | 50% storage efficiency.       |  
| **RAID 5**     | Striping + distributed parity.   | Balanced speed/redundancy.   | Slow writes; 1 disk parity.   |  
| **RAID 10**    | Mirroring + striping (RAID 1+0). | High speed + redundancy.     | High cost (50% efficiency).   |  

**Example Use Cases**:  
- **RAID 0**: Video editing (speed prioritized).  
- **RAID 1**: Financial databases (data integrity).  
- **RAID 5**: Enterprise file servers.  
- **RAID 10**: High-traffic web servers.  

---

**Key Takeaways**:  
- Real-time systems prioritize **timeliness** and **predictability**.  
- Embedded systems face challenges like **resource limits** and **environmental resilience**.  
- RAID configurations balance **speed**, **capacity**, and **redundancy**.  
