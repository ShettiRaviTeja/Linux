# Basic Linux Tools
- These commands are commonly used by Linux administrators and Data Engineers to find files, check dates, manage execution time, and compress or extract files.

## A. Find - Search for files and directories
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

## B. locate : Search for files and directories
- Purpose: Used to search for files and directories by their names in Linux.
- Unlike find, it searches a prebuilt database instead of scanning the actual filesystem. Therefore, it is generally faster.
- Syntax : locate filename

### 1. Search for a file
- locate employees.txt
### 2. Search for a file with particular extension
- locate "*.txt"
### 3. Case-insensitive search
- locate -i employees.txt
### Flags
- -i : Case-insensitive search
- -c : Count matching results
- -n : Limit results
- -r : Search using a regular expression
- -l : Limit the number of results (same as -n)
- -S : Database statistics
- -e : Existing files only
- -b : Match only the filename
- Before using the locate command, make sure the database is updated using the command:
  - sudo updatedb

## C. date : Display the current system date and time
- Purpose : Used to display the current system date and time.
- It can also display dates in different formats, calculate future or past dates, and set the system date and time.
- Example : date
- Syntax : date [OPTION]... [+FORMAT]
  - date : Command name.
  - OPTION : Specifies what operation to perform.
  - FORMAT : Specifies how the date and time should be displayed.
### Important flags
- -d : Display a specified date/time
- -u : Display UTC time
- -s : Set system date/time
- -r : Display a file's last modification time
- -f : Read dates from a file
- -I : Display date in ISO 8601 format
- -R : Display date in RFC format

### Examples
1. -d : Display a specified date
   - date -d "yesterday"
   - date -d "tomorrow"
   - date -d "5 days ago"
   - date -d "+7 days"
   - date -d "next month"
2. -u : Display UTC time
   - date -u : India follow IST (UTC +5:30)
3. -s : Set system date and time
   - sudo date -s "2026-11-25 11:30:00"
4. -r : Display file modification time
   - date -r employees.txt
5. -f : Read dates from a file
   - date -f dates.txt
6. -I : ISO 8601 format
   - date -I : 2026-11-25
   - we also have date -Iseconds
7. -R : RFC email format
   - date -R

### Important Date Formatting Options
- %d : Day of the month
- %m : Month number
- %Y : Full year
- %y : Last two digits of year
- %H : Hour (24-hour format)
- %I : Hour (12-hour format)
- %M : Minutes
- %S : Seconds
- %p : AM/PM
- %A : Full weekday name
- %a : Short weekday name
- %B : Full month name
- %b : Short month name
- %j : Day of the year
- %Z : Timezone abbreviation
- %z : Timezone offset

### Examples 
1. Display only the date
   - date +"%d-%m-%Y"
2. Display only the time
   - date +"%H:%M:%S"
3. Display the weekday
   - date +"%A"
4. Display the month name
   - date +"%B"
5. Display date and time in a custom format
   - date +"%d-%m-%Y %H:%M:%S"
6. Display date with AM/PM
   - date +"%d-%m-%Y %H:%M:%S %p"

## D. sleep : Pause or delay the execution
- Purpose : Used to pause or delay the execution of commands for a specified amount of time.
- Syntax : sleep NUMBER[SUFFIX]
  - NUMBER : Amount of time to wait.
  - SUFFIX : Unit of time

### Available time units
- s : Seconds : sleep 5s
- m : Minutes : sleep 2m
- h : Hours : sleep 1h
- d : Days : sleep 1d
- Note : If you don't specify a suffix, Linux considers the value as seconds.

### Practical Use Cases
- The sleep command can be useful in automation and scripting.
- Suppose a script starts a service and needs to wait before checking whether it is ready.
  - echo "Starting Service..."
  - sleep 10
  - echo "Checking service status..."

- sleep 5 : Runs in the foreground
- sleep 5 & : Runs in the background
  - We will get like this : [1] [12345] which is job number and process id (PID).

## E. time : Measures the time
- Purpose : Used to measure how long a command takes to execute.
- Syntax : time command
- Example : time sleep 5
  - We will get something like this: real    0m5.002s
                                     user    0m0.000s
                                     sys     0m0.001s
### Understanding real, user, and sys
- real : Total elapsed time from start to finish.
- user : CPU time spend executing the program's instruction in user mode.
- sys : CPU time spent executing system-level operations on behalf of the program.

#### A. Real time
- Real time is the actual time that passes between starting and finishing a command.
- Think of it as the stopwatch time.

#### B. User time
- User time is the amount of CPU time spend executing the program's instructions in user mode.
- Example : time ls -l
  - Measures how much CPU time was spent executing the 1s program.

#### C. System time
- System time is the amount of CPU time spent executing kernel operations on behalf of the program.

### Important Options
- There are two commonly encountered versions of time:
  - Shell keyword : Provided by Bash.
  - External command : Usually /usr/bin/time.

## F. gzip : Compress files
- Used to compress files to reduce their storage size.
- Suppose you have a file named employees.txt and after compressing it using gzip, you get employees.txt.gz.
- The .gz extension indicates that the file is compressed using gzip.
- Syntax : gzip [OPTIONS] filename
- Example :
  - First create a sample file
  - Now compress it
  - Check the files
  - By default, gzip replaces the original file with the compressed .gz file.

### Important flags of gzip
- -k : Keep the original file
- -d : Decompress a file
- -c : Write output to standard output
- -r : Compress files recursively
- -v : Verbose mode : Displays details about the compression process, including the compression ratio.
- -1 : Fast compression : Uses less compression effort to compress files faster.
- -9 : Maximum compression : Uses more compression effort to achieve a smaller file size, usually taking more time.
- -l : List compressed file information : Displays info about a compressed file.

## G. gunzip : Decompress files
- Used to decompress files that were compressed using gzip.
- Syntax : gunzip [OPTIONS] filename.gz

### Important flags of gunzip
- -k : Keep the compressed file
- -c : Write output to standard output
- -r : Decompress files recursively
- -v : Verbose mode : Displays detailed info about the decompression process.
- -f : Force decompression even when the destination file already exists or the file has an unusual extension.
- -l : List compressed file info without extracting it.

## H. zip : Archive files
- Combines and compresses multiple files and directories into a single .zip archive.
### Important zip flags
- -r : Compress directories recursively
- -u : Update existing archive entries
- -d : Delete files from an existing archive
- -m : Move files into the archive and delete originals after successful addition.
- -v : Display detailed information
- -9 : Use maximum compression effort
- -1 : Use fastest compression

## I. unzip : Extract files
- Command used to extract files and directories from a ZIP archive (.zip)
- Syntax : unzip [OPTIONS] archive_name.zip
### Important unzip flags
- -l : List files inside the zip archive
- -d : Extract into a specific directory
- -o : Overwrite existing files automatically
- -n : Never overwrite existing files
- -j : Extract files without directory structure
- -q : Quiet mode : Extract files without displaying unnecessary messages.
- -v : Verbose mode : Displays detailedd information about the ZIP archive.
- -t : Test ZIP archive integrity : Checks whether the ZIP archive is valid and whether its contents can be decompressed successfully, without extracting the files.
