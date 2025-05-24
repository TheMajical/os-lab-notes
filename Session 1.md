# Introduction to Basic Linux Commands

Hello and welcome!

Below are the basic Linux commands we learned and practiced in the previous session.  
I’m also sharing a useful link where you can review these commands or see visual examples if needed.

---
### Basic Linux Commands

- **ls** — Lists directories and files (most frequently used command)
    
- **pwd** — Prints the current working directory
    
- **cd** — Changes directory, used to navigate through folders
    
- **mkdir** — Creates new directories
    
- **mv** — Moves or renames files and directories
    
- **cp** — Copies files or directories (similar to `mv` but for copying)
    
- **rm** — Deletes files or directories
    
- **touch** — Creates an empty file
    
- **clear** — Clears the terminal screen
    
- **cat** — Displays the contents of a file
    
- **man** — Opens the manual pages for Linux commands
    
- **chmod** — Changes file or directory permissions
    
- **sudo** — Executes commands with elevated (superuser) privileges
    

---
# Additional Notes on Linux Commands

### `ls` Command Options

- `-a` : Show **all** files, including hidden files (those starting with a dot `.`).
    
- `-h` : Show file sizes in **human-readable** format (e.g., KB, MB) when used with `-l`.
    
- `-l` : Display files in a **long listing format**, showing permissions, owner, size, and modification date.
    

Example:

```bash
ls -lah
```

Lists all files including hidden ones, with detailed info and human-readable sizes.

---

### How `cd ..` Works

- `cd` stands for **change directory**.
    
- `..` refers to the **parent directory** of the current directory.
    
- So, `cd ..` moves you **one level up** in the directory hierarchy.
    

Example:  
If you are in `/home/user/documents`, running `cd ..` moves you to `/home/user`.

---

### Relative Path vs Absolute Path

- **Absolute Path**: The full path starting from the root directory `/`.  
    Example: `/home/user/documents/file.txt`
    
- **Relative Path**: Path relative to your current directory.  
    Example: If you are in `/home/user`, `documents/file.txt` is a relative path.
    

Relative paths do not start with `/`. Commands like `cd`, `ls`, and others accept both types.

---

### `rm` Command Options

- `-f` (force): Remove files **without prompting** for confirmation, even if files are write-protected.
    
- `-r` (recursive): Remove directories and their contents **recursively**.
    

Example:

```bash
rm -rf myfolder
```

Forcefully and recursively deletes the folder named `myfolder` and all its contents.

---
### Useful Resource

[DigitalOcean Linux Command Tutorials](https://www.digitalocean.com/community/tutorials/linux-commands)  
A comprehensive guide for reviewing and learning Linux commands with examples.
