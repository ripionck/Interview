## 🔒 Access Control  
**1. User Authentication**  
- Verifies user identity before granting access.  
- **Methods**: Passwords, biometrics (fingerprint), multi-factor authentication (MFA).  
- *Example*: Linux `sudo` requires password verification for admin privileges.  

**2. Access Control Lists (ACLs)**  
- Defines permissions for users/groups on files, directories, or devices.  
- **Types**:  
  - **POSIX ACLs (Linux/macOS)**: Use `chmod` and `chown` to set read/write/execute permissions.  
  - **NTFS ACLs (Windows)**: Granular permissions (e.g., "Modify," "Full Control").  

```bash  
# Linux example: Set read/write for owner, read for group  
chmod 640 secret.txt  
```  

---

## 🛡️ Memory Protection  
**1. Segmentation**  
- Divides memory into logical segments (code, data, stack) with access rights (read/write/execute).  
- **Pros**: Prevents unauthorized access to other segments.  
- *Example*: x86 architecture uses segment descriptors for protection.  

**2. Paging**  
- Uses page tables with permissions (e.g., read-only, supervisor-only) for memory pages.  
- **Pros**: Isolates processes; prevents illegal memory access.  
- *Example*: A segmentation fault occurs when a process accesses unauthorized memory.  

| **Technique** | **Approach**               | **Protection Mechanism**       |  
|---------------|----------------------------|---------------------------------|  
| Segmentation  | Variable-sized logical units| Segment-level permissions       |  
| Paging        | Fixed-size pages           | Page-table flags (R/W/X)        |  

---

## 🚨 Security Threats  
**Common Threats**:  
1. **Malware**  
   - **Viruses**: Attach to files/programs; require user action to spread.  
   - **Worms**: Self-replicating; spread via networks (e.g., WannaCry).  
   - **Ransomware**: Encrypts data for extortion (e.g., LockBit).  

2. **Phishing**: Deceptive emails/sites trick users into revealing credentials.  

3. **Denial-of-Service (DoS)**: Overwhelms systems to disrupt services.  

**Mitigation Strategies**:  
- **Antivirus Software**: Scans for and removes malware.  
- **Firewalls**: Block unauthorized network traffic.  
- **Regular Updates**: Patch vulnerabilities in OS/software.  

---

### Example (Windows ACL):  
```powershell  
# Grant "Read" access to a user  
icacls file.txt /grant Alice:R  
```  

---

Use this guide to understand how operating systems enforce security, protect memory, and combat threats! 🔐🖥️
