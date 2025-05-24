# Practical Guide to `grep` Command
---
### What is `grep`?

- `grep` searches for **patterns** (strings or regular expressions) inside files or input.
    
- It prints lines that **match** the pattern.

---
### Basic Syntax

```bash
grep [options] pattern [file...]
```

---
### Common and Useful Options

| Option       | Description                                     |
| ------------ | ----------------------------------------------- |
| `-i`         | Case-insensitive search                         |
| `-r` or `-R` | Recursively search directories                  |
| `-v`         | Invert match (show lines **not** matching)      |
| `-n`         | Show line numbers where matches occur           |
| `-c`         | Count matching lines instead of printing them   |
| `-w`         | Match whole words only                          |

---

### Examples

- Search for "error" (case-insensitive) in a log file:
    
    ```bash
    grep -i "error" /var/log/syslog
    ```
    
- Search recursively for "TODO" in current directory:
    
    ```bash
    grep -r "TODO" .
    ```
    
- Show line numbers where "main" appears in code files:
    
    ```bash
    grep -n "main" *.c
    ```
    
- Count how many times "root" appears in `/etc/passwd`:
    
    ```bash
    grep -c "root" /etc/passwd
    ```
    
- Show lines that **do not** contain "test":
    
    ```bash
    grep -v "test" file.txt
    ```

---

### Combining `grep` with Other Commands

- Find processes related to ssh:
    
    ```bash
    ps aux | grep ssh
    ```
    
- Search command history for "git":
    
    ```bash
    history | grep git
    ```
