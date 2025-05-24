# STDIN, STDOUT, STDERR, Redirection, Pipes, and Command Chaining
---
### Standard Streams in Shell

- **STDIN (Standard Input)**: The default input source for commands (usually keyboard).
    
- **STDOUT (Standard Output)**: The default output destination (usually the terminal screen).
    
- **STDERR (Standard Error)**: The default output for error messages (also usually the terminal).

---
### Redirection Operators

- `>` : Redirect **STDOUT** to a file, **overwriting** the file.  
    Example:
    ```bash
    echo "Hello" > file.txt
    ```
    This writes "Hello" to `file.txt`, replacing its content.
    
- `>>` : Redirect **STDOUT** to a file, **appending** to the file.  
    Example:
    ```bash
    echo "World" >> file.txt
    ```
    This adds "World" to the end of `file.txt`.

---
### Pipe Operator `|`

- Connects the **STDOUT** of one command to the **STDIN** of another command.
- Useful for chaining commands together to process data step-by-step.
    ![[Pasted image 20250525014410.png]]

Example:

```bash
cat file.txt | wc -l
```

- `cat file.txt` outputs the content of the file.
    
- `wc -l` counts the number of lines from the input it receives via the pipe.

---
### Command Chaining with `&&`

- Runs the second command **only if the first command succeeds** (returns exit status 0).
    
- Useful for conditional execution.

Example:

```bash
mkdir new_folder && cd new_folder
```

- This creates a directory and **only changes directory if creation succeeds**.

---
### Educational Example Script

```bash
#!/bin/bash

# Overwrite file.txt with "Hello"
echo "Hello" > file.txt

# Append "World" to file.txt
echo "World" >> file.txt

# Display file contents and count lines using pipe
cat file.txt | wc -l

# Create a directory and enter it only if creation succeeds
mkdir my_folder && cd my_folder
echo "Now inside $(pwd)"
```
