
---
Example question to train for the final exam:

Write a Bash script to read data.txt file and perform these options

 1. Change @example.com to @usc.com in all email addresses!
 2. Return people who are older than a specific year
 3. Delete nth line of the file (e.g: 3)

Here is the sample of the `data.txt` file
```
nima | nima@example.com | 1383
reza | reza@another.com | 1381
sara | sara@gmail.com | 1382
aref | aref@yahoo.com | 1384
alireza | alireza@usc.com | 1386
```


---

Answer:

```bash
#!/bin/bash

read -p "Enter your file path: " fileName

if [[ -f $fileName ]]; then
  echo "Enter your option:"
  echo "1) Change @example to @usc"
  echo "2) Show people older than a year"
  echo "3) Delete a line"

  read -p "Enter your choice: " menu
  case $menu in
    1)
      sed -i "s/@example/@usc/g" $fileName
      echo "File updated successfully"
      ;;
    2)
      read -p "Enter a birth year: " year
      while read -r line; do
        var=$(echo "$line" | grep -Eo "[0-9]{4}")
        if [[ $var -lt $year ]]; then
          echo "$line"
        fi
      done < "$fileName"
      ;;
    3)
      read -p "Enter a line number to delete: " lineNumber
      sed -i "${lineNumber}d" $fileName
      ;;
  esac
else
  echo "File is not valid"
fi

```

