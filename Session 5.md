# Conditionals, Mathematical Operations, and Switch Case in Bash
---
### If-Else Conditions

- Bash if syntax requires spaces around brackets and `then` keyword:
    
    ```bash
    if [ condition ]; then
      # commands
    elif [ condition ]; then
      # commands
    else
      # commands
    fi
    ```
    
- Important notes:
    - Use spaces after `[` and before `]`.
    - Conditions are often comparisons or command exit statuses.
    - `[[ ... ]]` is an advanced test command, safer and more flexible.

Example:

```bash
if [ $num -gt 10 ]; then
  echo "Number is greater than 10"
else
  echo "Number is 10 or less"
fi
```

---

### Mathematical Operations and Comparisons

- For arithmetic, use `(( ... ))` or the `expr` command.
- Basic arithmetic with `(( ))`:
    
    ```bash
    a=5
    b=3
    (( sum = a + b ))
    echo $sum  # outputs 8
    ```
    
- Common comparison operators inside `[ ]`:
    
    - `-eq` : equal
        
    - `-ne` : not equal
        
    - `-lt` : less than
        
    - `-le` : less or equal
        
    - `-gt` : greater than
        
    - `-ge` : greater or equal
        

Example:
```bash
if [ $a -eq $b ]; then
  echo "Equal"
else
  echo "Not equal"
fi
```

---
### Switch Case Statement

- Syntax:
    ```bash
    case $variable in
      pattern1)
        # commands
        ;;
      pattern2)
        # commands
        ;;
      *)
        # default commands
        ;;
    esac
    ```
    
- Useful for multiple-choice branching.

Example:
```bash
read -p "Enter a fruit: " fruit
case $fruit in
  apple)
    echo "You chose apple";;
  banana)
    echo "You chose banana";;
  *)
    echo "Unknown fruit";;
esac
```

---

### Educational Example Script

```bash
#!/bin/bash

read -p "Enter a number: " num

if (( num > 0 )); then
  echo "Positive number"
elif (( num == 0 )); then
  echo "Zero"
else
  echo "Negative number"
fi

read -p "Choose a day (mon/tue/wed): " day

case $day in
  mon)
    echo "Monday selected";;
  tue)
    echo "Tuesday selected";;
  wed)
    echo "Wednesday selected";;
  *)
    echo "Invalid day";;
esac
```
