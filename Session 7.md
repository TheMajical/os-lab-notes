# Loops in Bash Scripting — `for` and `while`
---
### `for` Loops

- Used to iterate over a list of items or a range of numbers.
- Basic syntax:
    ```bash
    for var in list
    do
      # commands using $var
    done
    ```

**Example 1: Loop through a list of words**

```bash
for fruit in apple banana cherry
do
  echo "I like $fruit"
done
```

**Example 2: Loop through numbers**

```bash
for i in {1..5}
do
  echo "Number $i"
done
```

---

### `while` Loops

- Runs as long as a condition is true.
- Basic syntax:
    
    ```bash
    while [ condition ]
    do
      # commands
    done
    ```
    

**Example 1: Simple counter**

```bash
count=1
while [ $count -le 5 ]
do
  echo "Count is $count"
  ((count++))
done
```

**Example 2: Reading lines from a file**

```bash
while IFS= read -r line
do
  echo "Line: $line"
done < filename.txt
```

---
### Notes:

- Remember to put spaces around `[ ]` in conditions.
    
- You can break out of loops early using `break`.
    
- Use `continue` to skip the rest of the current iteration.

---
### Educational Example Script

```bash
#!/bin/bash

echo "For loop example:"
for i in {1..3}
do
  echo "Iteration $i"
done

echo "While loop example:"
counter=1
while [ $counter -le 3 ]
do
  echo "Counter is $counter"
  ((counter++))
done
```
