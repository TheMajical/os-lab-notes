# Introduction to `sed` Command in Linux
---
### What is `sed`?

- `sed` (stream editor) is a powerful command-line tool used to **parse, transform, and edit text streams or files**.
- It reads input line by line, applies specified operations, and outputs the modified text.
---
### Basic Syntax

```bash
sed [options] 'command' filename
```

Or

```bash
sed 'command' filename
```

---
### Common Uses & Examples

#### 1. Print specific lines

- Print only the 2nd line of a file:
    
    ```bash
    sed -n '2p' filename
    ```
    
- Print lines from 2 to 4:
    
    ```bash
    sed -n '2,4p' filename
    ```

---

#### 2. Delete lines

- Delete the 2nd line:
    
    ```bash
    sed '2d' filename
    ```
    
- Delete lines 2 to 4:
    
    ```bash
    sed '2,4d' filename
    ```
    

---

#### 3. Substitute text (`s` command)

- Replace first occurrence of `old` with `new` on each line:
    
    ```bash
    sed 's/old/new/' filename
    ```
    
- Replace **all occurrences** on each line (global replacement):
    
    ```bash
    sed 's/old/new/g' filename
    ```

---

#### 4. Insert and append lines

- Insert a line before the 2nd line:
    
    ```bash
    sed '2i This is inserted line' filename
    ```
    
- Append a line after the 2nd line:
    
    ```bash
    sed '2a This is appended line' filename
    ```

---
#### 5. Change (replace) entire line

- Replace the 2nd line completely:
    
    ```bash
    sed '2c This is the new line' filename
    ```

---
#### 6. Using multiple commands

- Using `-e` option to execute multiple commands:
    
    ```bash
    sed -e '2d' -e '5s/old/new/' filename
    ```
    
- Or using `;` to separate commands inside quotes:
    
    ```bash
    sed '2d;5s/old/new/' filename
    ```

---

#### 7. Writing changes to a file (in-place editing)

- Use `-i` option to edit file **in-place** (modify original file):
    
    ```bash
    sed -i 's/old/new/g' filename
    ```


---

### Tips and Notes

- By default, `sed` outputs to **standard output**, so original file is not changed unless `-i` is used.
    
- Addresses can be line numbers, regex patterns, or a combination:
    
    - Example with regex:
        
        ```bash
        sed '/pattern/d' filename  # deletes lines matching 'pattern'
        ```
        
- Always back up important files before using `-i`!

---

### Educational Example

Suppose `file.txt` contains:

```
Hello world
Linux is awesome
Hello Linux users
```

- Replace “Hello” with “Hi” globally:
    
    ```bash
    sed 's/Hello/Hi/g' file.txt
    ```
    
    Output:
    
    ```
    Hi world
    Linux is awesome
    Hi Linux users
    ```
    
- Delete lines containing “Linux”:
    
    ```bash
    sed '/Linux/d' file.txt
    ```
    
    Output:
    
    ```
    Hello world
    ```
    
- Insert a line before line 2:
    
    ```bash
    sed '2i This is a new line' file.txt
    ```
    
    Output:
    
    ```
    Hello world
    This is a new line
    Linux is awesome
    Hello Linux users
    ```
    

---

### Great Source for Learning More

For more detailed explanations and examples, check out this excellent resource:  
[https://www.geeksforgeeks.org/sed-command-in-linux-unix-with-examples/](https://www.geeksforgeeks.org/sed-command-in-linux-unix-with-examples/)