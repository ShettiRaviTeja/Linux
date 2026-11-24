# Basic Linux Tools
- These commands are commonly used by Linux administrators and Data Engineers to find files, check dates, manage execution time, and compress or extract files.

## 1. Find - Search for files and directories
- Purpose: Used to search for files and directories based on their names, types, sizes, permissions, modification times, etc.
- Syntax: find (path) (condition)

### Find a file by name
- find /home -name "employees.txt" : Case-sensitive
- find . -iname "Employees.txt" : Case-insensitive

### Search using wildcards
- find . -name '*.txt' : Ending with txt.
- '*' represents multiple characters and '?' represents single character.

### Searching based on file type
- find . -type d : Directories
- find . -type f : Regular Files
- l : Symbolic link
- b : Block device
- c : Character device

### Searching based on file size
- find . -size (size_condition)
  - c : Bytes
  - k : Kilobytes
  - M : Megabytes
  - G : Gigabytes

### Searching based on modification time
- -mtime : Modification time in days
  - find . -mtime -1 (Find files modified within the last 24 hours)
  - find . -mtime +7 (Modified more than 7 days ago)
  - find . -mtime 2 (Modified exactly 2 days ago)
- -mmin : Modification time in minutes
  - find . -mmin -10 (modified within the last 10 minutes)
  - find . -mmin +30 (modified more than 30 minutes ago)
 
### Searching empty files and directories
- The -empty option identifies empty files and directories.
- find . type f -empty (Displays empty files)
- find . type d -empty (Display empty directories)
- find . -empty (All empty files and directories)

### Searching based on permissions
- Linux files have permissions such as read, write and execute.
- The -perm option searches based on permissions.
   - Find regular files with exactly permission 644?
      - find . -type f -perm 644
   - Find regular files for which all three execute bits are set (owner, group and others)?
      - find . -type f -perm -111
   - Find regular files where at least one execute permission is set?
      - find . -type f -perm /111

### Searching based on ownership
- You can search for files owned by a particular user.
   - -user : find /home -user ravi (Find files and directories owned by the user ravi)
   - -group : find /home -group developers (Find files and directories belonging to the developers group)

### Performing actions on the search results
- You can not only search for files but also perform actions on them.
  - -print : Displaying the matching files.
    - find . -name "*.txt" -print
    - It is the default action when no other action is specified.
  - -delete : Deletes matching files.
    - find . -type f -name "*.tmp" -delete
    - Files will be permanently deleted.
  - -exec : Executes another command on each matching result.
    - Syntax: (find) (path) (condition) -exec (command) {} \;
    - {} represents the currently matched file.
    - \; represents the end of the command.
  - -exec with + : Instead of executing the command separately for each file, + passes multiple matching files together when possible.
    - find . -name "*.txt" -exec ls -l {} +
