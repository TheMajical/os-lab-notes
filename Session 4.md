#  Introduction to Bash Scripting
---
### What is a Shell?

- A **shell** is a command-line interpreter that allows users to interact with the operating system by typing commands.
- It processes commands and runs programs.
- Different types of shells exist, including:
    
    - **Bash** (Bourne Again Shell) — the most common default shell on Linux.
    - **sh** (Bourne Shell)
    - **zsh** (Z Shell)
    - **csh** (C Shell)
    - **fish** (Friendly Interactive Shell)
        
**Bash scripts** are scripts written to be executed by the Bash shell.

---

### What is a Shebang?

- The **shebang** (`#!`) is a special line at the top of a script that tells the system which interpreter to use to run the script.
    
- For Bash scripts, the shebang is usually:
    
    ```bash
    #!/bin/bash
    ```
    
- It ensures the script runs with Bash even if executed from another shell.

---
### Variables in Bash

- Variables store data (strings, numbers, etc.).
- To **assign** a variable, do **not** put spaces around the `=` sign:
    
    ```bash
    NAME="Amir"
    ```
    
- To **use** a variable, prefix it with `$`:
    
    ```bash
    echo "Hello, $NAME"
    ```
    

---

### Escaping Variables

- Use a backslash `\` to prevent variable expansion:
    
    ```bash
    echo "\$NAME"
    ```
    
    Output: `$NAME` (literally, without expanding)
    

---

### System Variables and Command Substitution

- You can assign variables from the output of system commands using **command substitution** with `$(...)`:
    
    ```bash
    TODAY=$(date)
    echo "Today is: $TODAY"
    ```
    
- **Difference between `$date` and `$(date)`**:
    
    - `$date` means “the value of a variable named `date`” (which usually doesn’t exist).
        
    - `$(date)` runs the command `date` and substitutes its output.
        

---

### The `echo` Command

- Prints text or variables to the terminal.
- Example:
    
    ```bash
    echo "Welcome to Bash scripting"
    echo "User: $NAME"
    ```
    

---

### The `read` Command

- Reads user input from the terminal and stores it in a variable.
- Example:
    
    ```bash
    read USERNAME
    echo "Hello, $USERNAME"
    ```
    
- Using `read -p` to display a prompt before input:
    
    ```bash
    read -p "Enter your name: " USERNAME
    echo "Hello, $USERNAME"
    ```
