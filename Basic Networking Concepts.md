
### **Network Definition**  
A **network** is a system of interconnected devices (called **nodes**) that communicate to share resources, exchange data, or provide services. Networks enable collaboration and resource sharing, such as accessing the internet, printing documents, or transferring files.  

- **Examples**:  
  - A home Wi-Fi network connecting phones, laptops, and smart devices.  
  - An office network linking computers, servers, and printers.  
  - The global internet, the largest network, connecting billions of devices worldwide.  

- **Purpose**:  
  - Share hardware (e.g., printers), software, and data.  
  - Enable communication (email, video calls).  
  - Centralize storage (cloud servers).  

---

### **Nodes and Links**  
1. **Nodes**:  
   - Any device connected to a network. Examples:  
     - **End devices**: Computers, smartphones, printers.  
     - **Network devices**: Routers, switches, servers.  
   - Nodes send, receive, or route data.  

2. **Links**:  
   - Physical or wireless connections between nodes.  
   - **Wired links**: Ethernet cables, fiber optics (high-speed, reliable).  
   - **Wireless links**: Wi-Fi, Bluetooth, cellular networks (flexible but prone to interference).  

- **Interaction**: Nodes use links to transmit data (e.g., a laptop sends a file to a printer via Wi-Fi).  

---

### **Network Topology**  
The **physical or logical arrangement** of nodes and links in a network. Common topologies include:  

1. **Bus**:  
   - All nodes connect to a single central cable (bus).  
   - **Pros**: Simple, low cost.  
   - **Cons**: Single point of failure; collisions slow performance.  
   - *Example*: Early Ethernet networks.  

2. **Star**:  
   - All nodes connect to a central hub/switch.  
   - **Pros**: Easy to troubleshoot; one node failure doesn’t disrupt others.  
   - **Cons**: Central hub failure collapses the network.  
   - *Example*: Modern home networks with a Wi-Fi router.  

3. **Ring**:  
   - Nodes form a closed loop, passing data in one direction.  
   - **Pros**: Predictable performance.  
   - **Cons**: A single node failure breaks the loop.  
   - *Example*: Token Ring networks (less common today).  

4. **Mesh**:  
   - Nodes are interconnected, providing multiple paths for data.  
   - **Full Mesh**: Every node connects to every other (expensive but ultra-reliable).  
   - **Partial Mesh**: Only critical nodes have redundant links.  
   - *Example*: The internet backbone (redundant paths ensure reliability).  

---

### **IP Address**  
A **unique identifier** assigned to each device on a network, enabling communication.  

1. **IPv4**:  
   - 32-bit address written as four numbers (0–255) separated by dots: `192.168.1.1`.  
   - Limited to ~4.3 billion addresses (exhausted due to internet growth).  

2. **IPv6**:  
   - 128-bit hexadecimal address, written as eight groups: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`.  
   - Solves IPv4 scarcity, offering ~340 undecillion addresses.  

- **Public vs. Private IPs**:  
  - **Public**: Assigned by ISPs, unique globally (e.g., a router’s WAN address).  
  - **Private**: Used internally (e.g., `192.168.x.x` in homes). NAT (Network Address Translation) maps private IPs to a public IP.  

---

### **DNS (Domain Name System)**  
The **"phonebook of the internet"** that translates human-friendly domain names (e.g., `google.com`) to machine-readable IP addresses (e.g., `172.217.14.206`).  

1. **How DNS Works**:  
   - **Step 1**: Type `example.com` into a browser.  
   - **Step 2**: The device queries a **DNS resolver** (usually device ISP).  
   - **Step 3**: The resolver asks **root servers**, which direct it to **Top-Level Domain (TLD) servers** (e.g., `.com`).  
   - **Step 4**: TLD servers point to the **authoritative DNS server** for `example.com`, which returns the IP.  
   - **Step 5**: The resolver caches the IP for future use.  

2. **DNS Records**:  
   - **A Record**: Maps a domain to an IPv4 address.  
   - **AAAA Record**: Maps to an IPv6 address.  
   - **CNAME**: Redirects to another domain (e.g., `www.example.com` → `example.com`).  

- **Importance**: Simplifies web navigation (no need to memorize IPs).  

---

### **Summary**  
- **Networks** connect devices to share resources.  
- **Nodes** are devices; **links** are their connections.  
- **Topology** defines the network’s layout (bus, star, ring, mesh).  
- **IP addresses** uniquely identify devices (IPv4 vs. IPv6).  
- **DNS** translates domain names to IP addresses for seamless browsing.
