# Text Editors and Terminal Cleanup Commands
---
### Text Editors in Linux

- Linux offers many text editors. Common ones include:
    - **nano**
    - **vim**
    - **vi**


Today, we will focus on **nano**, which is beginner-friendly and easy to use.

---
### Nano Text Editor

- `nano` is a simple command-line text editor.
    
- To open or create a file:
    
    ```bash
    nano filename.txt
    ```
    
- Inside `nano`:
    
    - Use **arrow keys** to navigate.
        
    - Type to insert text.
        
    - Common shortcuts are shown at the bottom, starting with `^` meaning Ctrl key.
        

---

### Useful Nano Commands

|Shortcut|Action|
|---|---|
|`Ctrl + O` (`^O`)|Save the current file|
|`Enter`|Confirm file name when saving|
|`Ctrl + X` (`^X`)|Exit nano (prompts to save if changes)|
|`Ctrl + K` (`^K`)|Cut current line|
|`Ctrl + U` (`^U`)|Paste the last cut line|
|`Ctrl + W` (`^W`)|Search text|

---

### Clearing the Terminal

- `clear` command:  
    Clears all previous output and moves the prompt to the top of the screen.
    
- `Ctrl + L` shortcut:  
    Also clears the screen visually, similar to `clear`.
    

---

### Difference Between `clear` and `Ctrl + L`

- Both effectively clear the terminal display.
    
- `clear` runs a command that clears the scrollback buffer in some terminals.
    
- `Ctrl + L` just refreshes the screen but might not clear scrollback in all terminals.
    
- In most cases, they behave similarly, but `clear` can be scripted while `Ctrl + L` is manual.
    
