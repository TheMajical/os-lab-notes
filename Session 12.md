Example Question to train for the final exam:
![[Pasted image 20250526233238.png]]
### **Question:**

Write a Bash script to perform these actions

 **Read a file path and Check if the input path is a valid file.If the file is valid:


1. **Print a range lines of the file**  
2. **Extract all email addresses from it.**  
3. **Store the file's statistics into new file:**
    
	- Number of words
    - Number of characters
    - Number of lines
    
    Example output: cat info.txt
    ```
    words: 23
    letters: 240
    lines: 7
    ```

---
Provided Code:

```bash
#!/bin/bash
 
read -p "Enter file path: " fileName

if [[ -f $fileName ]]; then
  echo "1) Print range of lines"
  echo "2) Extract email addresses"
  echo "3) Storage informations of file"

  read -p "Enter your choice" menu
  
  case $menu in
  1)
    read -p "Enter start of the range: " number1
    read -p "Enter end of the range: " number2
    head -n $number2 $fileName | tail -n $(( $number2 - $number1 + 1 ))
    ;;
  2)
    grep -E "[a-zA-Z0-9._%]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,3}$" $fileName
    ;;
  3)
      echo "words=$(cat $fileName | wc -w)"
      echo "lines=$(cat $fileName | wc -l)"
      echo "letters=$(cat $fileName | wc -m)"
    ;;
  *)
    echo "menu number incorrect!"
    ;;
  esac
else
  echo "This address for file is incorrect!"
fi
