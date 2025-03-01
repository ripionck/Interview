## 📁 File System Types  
**1. FAT (File Allocation Table):**  
- **Use Case**: Legacy systems, removable drives (USB, SD cards).  
- **Pros**: Simple, cross-platform compatibility (Windows, macOS, Linux).  
- **Cons**: No built-in security, limited file size (e.g., FAT32: max 4 GB/file).  

**2. NTFS (New Technology File System):**  
- **Use Case**: Modern Windows systems.  
- **Pros**: Supports large files (16 EB/file), encryption, journaling (crash recovery), and permissions.  
- **Cons**: Limited native support on non-Windows OS.  

**3. ext4 (Fourth Extended File System):**  
- **Use Case**: Default for Linux distributions.  
- **Pros**: Journaling, large file/partition support (1 EB), POSIX permissions.  
- **Cons**: Limited native Windows/macOS support.  

| **Feature**      | FAT32          | NTFS             | ext4             |  
|-------------------|----------------|------------------|------------------|  
| **Max File Size** | 4 GB           | 16 Exabytes      | 16 Terabytes     |  
| **Journaling**    | No             | Yes              | Yes              |  
| **Permissions**   | No             | ACLs             | POSIX            |  

---

## 🛠️ File System Operations  
**1. File Creation**  
- Allocates space and updates metadata (e.g., name, size, location).  
- **Example**: `touch file.txt` (Linux) or `New-Item file.txt` (PowerShell).  

**2. File Deletion**  
- Marks space as free; metadata may persist until overwritten.  
- **Example**: `rm file.txt` (Linux) or `del file.txt` (Windows CMD).  

**3. File Searching**  
- Traverses directories to locate files by name, type, or metadata.  
- **Example**: `find / -name "file.txt"` (Linux) or `dir /s file.txt` (Windows CMD).  

---

## 🔒 File System Security  
**1. Access Control Lists (ACLs):**  
- Defines permissions for users/groups (e.g., read, write, execute).  
- **Example (Linux)**:  
  ```bash  
  chmod u=rwx,g=rx,o= file.txt  # User: RWX, Group: RX, Others: No access  
  ```  

**2. POSIX Permissions (Linux/macOS):**  
- Three-level permissions: **Owner**, **Group**, **Others** (e.g., `755`).  
- **Symbolic Notation**: `r` (read), `w` (write), `x` (execute).  

**3. NTFS Permissions (Windows):**  
- Granular controls (e.g., Full Control, Modify, Read & Execute).  
- Managed via **Properties → Security tab** in Windows Explorer.  

---

## 📂 Additional Concepts  
- **Metadata**: Stores file attributes (e.g., timestamps, permissions).  
- **Directory Structure**: Hierarchical organization (e.g., root `/`, subfolders).  
- **Journaling**: Logs changes to recover from crashes (used in NTFS/ext4).  

---

### Example (Linux Permissions):  
```bash  
ls -l file.txt  
# Output: -rwxr-x--- 1 user group 1024 Jan 1 12:00 file.txt  
# Breakdown: Owner (rwx), Group (r-x), Others (---)  
```  

---

Use this guide to understand file system design, operations, and security across platforms! 💾🔐
