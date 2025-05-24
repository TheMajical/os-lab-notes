# Bash Script Positional Parameters and Special Variables
---
### Positional Parameters: `$0`, `$1`, `$2`, ..., `$n`

- `$0` : The **name of the script** being executed.
- `$1`, `$2`, ..., `$n` : The **arguments passed to the script**, where `$1` is the first argument, `$2` the second, and so on.

Example:  
If you run:

```bash
./script.sh arg1 arg2
```

- `$0` = `./script.sh`
- `$1` = `arg1`
- `$2` = `arg2`
---
### Other Useful Special Variables

|Variable|Meaning|
|---|---|
|`$#`|Number of arguments passed to the script|
|`$*`|All arguments as a **single string**|
|`$@`|All arguments as **separate strings**|
|`$$`|Process ID of the current script|
|`$?`|Exit status of the last executed command|

---

### Difference Between `$*` and `$@`

- Both represent **all script arguments** but behave differently when quoted:

|Usage|Behavior|
|---|---|
|`"$*"`|All arguments as a **single string**, separated by the first character of `$IFS` (default space)|
|`"$@"`|Each argument as a **separate quoted string**, preserving argument boundaries|

---
### Example Demonstrating `$*` vs `$@`

Assume script called with:

```bash
./script.sh "arg 1" arg2 "arg 3"
```

- Looping over `"$*"` treats all arguments as one string:
    
    ```bash
    for arg in "$*"; do
      echo "$arg"
    done
    ```
    
    Output:
    
    ```
    arg 1 arg2 arg 3
    ```
    
- Looping over `"$@"` treats arguments separately:
    
    ```bash
    for arg in "$@"; do
      echo "$arg"
    done
    ```
    
    Output:
    
    ```
    arg 1
    arg2
    arg 3
    ```

---

### Educational Example Script

```bash
#!/bin/bash

echo "Script name: $0"
echo "Number of arguments: $#"

echo "All arguments using \$* :"
for arg in "$*"; do
  echo "[$arg]"
done

echo "All arguments using \$@ :"
for arg in "$@"; do
  echo "[$arg]"
done

echo "Process ID: $$"
echo "Exit status of last command: $?"

```
