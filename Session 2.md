#  Linux Users, Permissions, and Important Directories
---

### Linux Users and Groups

- Linux is a **multi-user system**, where each user has a unique user ID (UID).
    
- Users are organized into **groups** to manage permissions collectively.
    
- Common user types:
    
    - **Root**: The superuser with full system privileges.
        
    - **Regular users**: Normal accounts with limited permissions.
        
- You can check your current user by running:
    
    ```bash
    whoami
    ```
    

---

### Linux File Permissions

Every file and directory has three types of permissions for three classes of users:

|Permission|Meaning|
|---|---|
|**r**|Read permission|
|**w**|Write permission|
|**x**|Execute permission|

|User Class|Description|
|---|---|
|**u**|Owner (user)|
|**g**|Group|
|**o**|Others (everyone else)|

Permissions control who can read, modify, or execute files.

---

### `chmod` Command

- Changes file or directory permissions.
    
- Syntax example:
    
    ```bash
    chmod [options] mode file
    ```
    
- Special case:
    
    ```bash
    chmod u+x filename
    ```
    
    This **adds execute permission** (`+x`) **for the file owner** (`u`).
    
- Use case: Making a script executable by its owner.
    

Example:

```bash
chmod u+x script.sh
```

---

### Important Directories in `/` and Their Permissions

|Directory|Purpose|Typical Permissions & Notes|
|---|---|---|
|`/bin`|Essential user binaries (commands)|Executable by all users (e.g., `ls`, `cp`)|
|`/etc`|Configuration files|Usually writable only by root|
|`/home`|User home directories|Each user's own directory writable by user|
|`/root`|Root user's home directory|Writable only by root|
|`/var`|Variable data (logs, mail, spool)|Writable by system processes|
|`/tmp`|Temporary files|Writable by all users, usually cleared on reboot|
|`/usr`|User programs and libraries|Readable by all users|
|`/dev`|Device files|Managed by system, special permissions|

---

### Permissions and Security

- Many system directories require **root privileges** to modify.
    
- Regular users typically have **read and execute** access but **no write** access outside their home directory.
    
- Correct permissions are crucial to keep the system secure and stable.
    
