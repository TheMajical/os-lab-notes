# Introduction to Regular Expressions (Regex) and Usage in Bash

---
### What is Regex?

- Regular expressions (regex) are patterns used to match character combinations in text.
- Widely used for searching, validating, and text processing.

---
### Common Regex Symbols and Their Meaning

|Symbol|Meaning|Example|
|---|---|---|
|`.`|Matches **any single character** except newline|`a.c` matches `abc`, `a1c`|
|`*`|Matches **0 or more** of the preceding element|`ab*c` matches `ac`, `abc`, `abbc`|
|`^`|Matches the **start of a line**|`^Hello` matches lines starting with `Hello`|
|`$`|Matches the **end of a line**|`end$` matches lines ending with `end`|
|`[]`|Matches **any one character** inside the brackets|`[abc]` matches `a` or `b` or `c`|
|`[a-z]`|Matches **any one character in the range** (lowercase letters)|`[0-9]` matches any digit|
|`?`|Matches **0 or 1** occurrence of the preceding element|`colou?r` matches `color` or `colour`|
|`+`|Matches **1 or more** occurrences of the preceding element|`a+` matches `a`, `aa`, `aaa`|
|`{n}`|Matches **exactly n** occurrences of the preceding element|`a{3}` matches `aaa`|
|`{n,}`|Matches **n or more** occurrences|`a{2,}` matches `aa`, `aaa`|
|`{n,m}`|Matches **between n and m** occurrences|`a{2,4}` matches `aa`, `aaa`, `aaaa`|
|`\`|Escapes special characters to treat them literally|`\.` matches a literal dot|

---
### Additional Regex Shorthand Classes

- `\w`  
    Matches any **word character**: letters (a–z, A–Z), digits (0–9), and underscore (_).
    
- `\w+`  
    Matches **one or more** word characters in a row (like a “word”).
    
- `\d`  
    Matches any **digit** (0–9).
    
- `\d+`  
    Matches **one or more** digits in a row (like a number).

---
### Examples

- `\w+` matches:
    
    - `hello`
    - `user_123`
    - `Test99`
        
- `\d+` matches:
    
    - `123`
    - `007`
    - `42`
---
### Usage with `grep -P` (Perl-compatible regex)

To use these shorthand classes in grep, you often need Perl-compatible regex with the `-P` option:

```bash
grep -P "\w+" filename
grep -P "\d+" filename
```

---
### Using Regex in Bash

- Bash supports regex in conditions with `[[ ... =~ ... ]]` syntax.

Example:

```bash
read -p "Enter a string: " input
if [[ $input =~ ^[a-zA-Z]+$ ]]; then
  echo "Only letters detected"
else
  echo "Invalid input"
fi
```

---

### Using Regex with `grep`

- `grep` uses regex by default (basic regex). Use `grep -E` or `egrep` for extended regex features.

Examples:

- Search lines starting with "Error":
    
    ```bash
    grep "^Error" logfile.txt
    ```
    
- Search lines ending with ".txt":
    
    ```bash
    grep "\.txt$" files.txt
    ```
    
- Search lines with one or more digits:
    
    ```bash
    grep -E "[0-9]+"
    ```
    
- Search lines with "color" or "colour" using `?`:
    
    ```bash
    grep -E "colou?r" file.txt
    ```
    

---

### Recommended Practice Site

To practice regex interactively and see explanations and matches in real time, visit:

[**https://regex101.com/**](https://regex101.com/)

This site is great for testing regex patterns, understanding their behavior, and learning quickly.