### **Network Models and Protocols**  

---

#### **OSI Model (Open Systems Interconnection)**  
A **7-layer conceptual framework** that standardizes network communication functions. Each layer serves a specific purpose, ensuring interoperability between devices and systems.  

1. **Physical Layer (Layer 1)**:  
   - **Function**: Transmits raw bitstreams over physical media (cables, Wi-Fi signals).  
   - **Components**: Hubs, repeaters, cables, connectors.  
   - **Example**: Ethernet cables (Cat5/6), fiber optics.  

2. **Data Link Layer (Layer 2)**:  
   - **Function**: Ensures error-free data transfer between nodes on the same network.  
   - **Components**: Switches, MAC addresses (e.g., `00:1A:2B:3C:4D:5E`).  
   - **Protocols**: Ethernet, Wi-Fi (802.11), Frame Relay.  

3. **Network Layer (Layer 3)**:  
   - **Function**: Routes data between networks using logical addressing (IP addresses).  
   - **Components**: Routers, IP addresses.  
   - **Protocols**: IP (Internet Protocol), ICMP.  

4. **Transport Layer (Layer 4)**:  
   - **Function**: Manages end-to-end communication, error recovery, and flow control.  
   - **Protocols**:  
     - **TCP** (Transmission Control Protocol): Reliable, connection-oriented (e.g., web browsing).  
     - **UDP** (User Datagram Protocol): Fast, connectionless (e.g., video streaming).  

5. **Session Layer (Layer 5)**:  
   - **Function**: Establishes, manages, and terminates connections between applications.  
   - **Example**: NetBIOS, RPC (Remote Procedure Call).  

6. **Presentation Layer (Layer 6)**:  
   - **Function**: Translates data formats (e.g., encryption, compression).  
   - **Examples**: SSL/TLS (encryption), JPEG/MPEG (compression).  

7. **Application Layer (Layer 7)**:  
   - **Function**: Provides user-facing services (e.g., email, file transfer).  
   - **Protocols**: HTTP, FTP, SMTP, DNS.  

---

#### **TCP/IP Model**  
A **4-layer model** used for the internet and most modern networks. It simplifies the OSI model and focuses on practical implementation.  

| **TCP/IP Layer**       | **OSI Equivalent**         | **Key Protocols**                   |  
|-------------------------|----------------------------|--------------------------------------|  
| **Network Interface**   | Physical + Data Link       | Ethernet, Wi-Fi, Frame Relay         |  
| **Internet**            | Network                    | IP, ICMP, ARP                        |  
| **Transport**           | Transport                  | TCP, UDP                             |  
| **Application**         | Session + Presentation + Application | HTTP, FTP, DNS, SMTP      |  

- **Key Differences**:  
  - TCP/IP combines OSI’s top three layers (Session, Presentation, Application) into one.  
  - Focuses on end-to-end data delivery rather than strict layering.  

---

#### **Routing Protocols**  
Protocols that determine the best path for data to travel across networks.  

1. **RIP (Routing Information Protocol)**:  
   - **Type**: Distance-vector protocol.  
   - **Metric**: Hop count (max 15 hops).  
   - **Use Case**: Small networks.  
   - **Drawback**: Slow convergence, no support for VLSM.  

2. **OSPF (Open Shortest Path First)**:  
   - **Type**: Link-state protocol.  
   - **Metric**: Bandwidth, latency.  
   - **Use Case**: Large enterprise networks.  
   - **Advantage**: Fast convergence, supports complex topologies.  

3. **BGP (Border Gateway Protocol)**:  
   - **Type**: Path-vector protocol.  
   - **Metric**: Path attributes (e.g., AS path length).  
   - **Use Case**: Internet backbone (routes traffic between autonomous systems).  
   - **Example**: Your ISP uses BGP to connect to other global networks.  

---

#### **Frame Relay**  
A **Data Link layer protocol** for cost-effective Wide Area Network (WAN) connections.  

- **How It Works**:  
  - Uses **virtual circuits** (logical paths) instead of dedicated physical links.  
  - **PVC (Permanent Virtual Circuit)**: Preconfigured path (e.g., office-to-data-center).  
  - **SVC (Switched Virtual Circuit)**: Temporary path created for a session.  

- **Key Components**:  
  - **DLCI (Data Link Connection Identifier)**: Addresses virtual circuits.  
  - **Frame Relay Switch**: Routes frames between nodes.  

- **Pros**:  
  - Cheaper than leased lines (pay for bandwidth used).  
  - Supports bursty traffic (e.g., intermittent data transfers).  

- **Cons**:  
  - Lacks built-in error correction (relies on upper layers).  
  - Mostly replaced by MPLS and VPNs today.  

---

### **Summary**  
- **OSI Model**: 7-layer standard for understanding network functions.  
- **TCP/IP Model**: 4-layer practical framework for internet communication.  
- **Routing Protocols**: RIP (small networks), OSPF (large networks), BGP (internet routing).  
- **Frame Relay**: Legacy WAN protocol using virtual circuits for cost savings.
