# Introduction to vi editor
## 1. What is the vi editor
- The vi editor is a text editor in Linux used to create, view, and modify files directly from the terminal.
- It is commonly used to:
  - Create shell scripts
  - Edit configuration files
  - Modify python scripts
  - Edit linux system files
  - Update log and text files

## 2. Command mode and insert mode
### A. Command mode
- It is the default mode when you open a file using vi.
- In this mode, you can:
  - Delete characters
  - Copy and paste lines
  - Undo changes
  - Search for text
  - Move the cursor
  - Save and exit using commands
- In command mode, whatever you type is interpreted as an editor command, not inserted as text.

### B. Insert Mode
- It allows you to type and modify the actual contents of a file.
- Type 'i' in command mode to enter into the insert mode.

### How to switch between modes?
- i : Enter insert mode before the cursor
- a : Enter insert mode after the cursor
- o : Create a new line below and enter insert mode
- O : Create a new line above and enter insert mode
- Esc : Return to Command mode

## 3. Replace and Delete a Character in vi
### A. Replace a character - r
- The r command replaces the character under the cursor with another character.
- Syntax : r[char]
- After replacing, vi automatically returns to Command Mode.
### B. Replace multiple characters - R
### C. Delete a character - x
- The x command deletes the character under the cursor.
### D. Delete the character before the cursor - X
- The uppercase X command deletes the character immediately before the cursor.

## 4. Undo and Repeat in vi
### A. Undo - u
- The u command reverses your most recent change.
### B. Undo all changes in the current line - U
- The uppercase U command restores the current line to the state it had when you first moved to that line (before making changes there)
### C. Repeat the last change - .
- The dot command repeats the last change you made.

## Cut, Copy and Paste a line in vi
### A. Cut a line - dd
- The dd command deletes the entire line where the cursor is positioned.
### B. Copy a line - yy
- The yy command copies the entire line where the cursor is positioned.
### C. Paste a line - p
- The p command pastes the copied or deleted line below the current cursor line.
### D. Paste above - P
- The uppercase P command pastes the copied or deleted line above the current cursor line.
### E. Cut multiple lines - Ndd
- You can delete multiple lines using a number before dd.
- Example : 3dd, means deletes three lines starting from the current cursor line.
### F. Copy multiple lines - Nyy
- Using a number before yy.
- Example : 3yy, copies three lines starting from the current cursor line.

## Start and End of a line in vi
- Helps to move the cursor to the beginning or end of a line.
### Move to the beginning of a line - 0
- Moves the cursor to the first character position of the current line.
### Move to the first non-empty character - ^
- Moves the cursor to the first non-whitespace character of the current line.
### Move to the end of a line - $
- Moves the cursor to the last character of the current line.

## Join Two or More Lines in vi
- The J command is used to join the current line with the next line.
### Join two lines - J
### Join multiple lines - NJ
### Join lines without inserting a space - gJ

## Save and Exit in vi
- Used to save modifications and exit the vi editor.
### Save a file - :w
- This command saves the changes without exiting the editor.
- Use case : When you want to save your work but continue editing the file.
### Exit the editor - :q
- This command exits the editor.
### Save and exit - :wq
### Force exit without saving - :q!
### Save without exiting - :w! : Forces a write attempt, subject to file permissions and system restrictions
### Save with a different filename - :w filename

## Searching in vi
- Used to find specific words or patterns inside a file.
### Search forward - /
- /word
### Search backward - ?
- ?word
### Find the next occurrence - n
- After finding for a word, press n to get the next occurrence.
### Find the previous occurrence - N
- The uppercase N command moves to the previous matching occurrence.
### Search without case sensitivity
- Use :set ignorecase
- To restore case sensitivity use, :set noignorecase
### Search and highlight matching words
- To highlight all matching occurrences - :set hlsearch
- To remove the highlighting - :set nohlsearch
- You can also temporarily clear the current highlights using - :nohlsearch
