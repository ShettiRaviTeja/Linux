# ls - List files and Directories
1. -l : Displays files in long-listing format(permissions, owner, size, date) : ls -l
2. -a : Displays all files, including hidden files : ls -a
3. -h : Displays file sizes in human-readable format(KB, MB, GB) : ls -lh
4. -i : Displays the inode number of each file : ls -i
5. -r : Reverses the sorting order : ls -r
6. -d : Displays the directory itself rather than its contents : ls -d */
7. -1 : Displays one entry per line : ls -1
8. -R : Lists files inside directories and their subdirectories recursively : ls -R
9. -S : Sorts files by size, largest first : ls -S
10. -t : Sorts files by modification time, newest first : ls -t

# pwd - Print Working Directory
1. -L : Displays the logical path, preserving symbolic links in the path : pwd -L
2. -P : Displays the physical path, resolving symbolic links : pwd -P

# cd - Change Directory
1. -L : Follows the logical path, preserving symbolic links : cd -L /tmp/link
2. -P : Follows the physical path, resolving symbolic links : cd -P /tmp/link
3. cd .. : Moves to the parent directory
4. cd ~ : Moves to the home directory
5. cd - : Moves to the previous working directory

# mkdir - Make Directory
1. -p : Creates parent directories if they don't exist : mkdir -p projects/data/files
2. -v : Displays a message for each directory created : mkdir -v projects
3. -m : Sets the directory permissions at creation time : mkdir -m 755 projects

# touch - Create or Update Files
1. -a : Updates only the access time : touch -a file.txt
2. -m : Updates only the modification time : touch -m file.txt
3. -c : Does not create the file if it doesn't exist : touch -c file.txt
4. -t : Sets the timestamp to a specified time : touch -t 202611241200 file.txt

# cat - Display File Contents
1. -n : Numbers all output lines : cat -n file.txt
2. -b : Numbers only non-empty lines : cat -b file.txt
3. -s : Suppresses consecutive blank lines : cat -s file.txt

# echo - Display Text
1. -n : Prevents a newline at the end of the output : echo -n "Hello"
2. -e : Enables interpretation of certain escape sequences : echo -e "Hello\nWorld"
3. -E : Disables interpretation of escape sequences : echo -E "Hello\nWorld"

# cp - Copy Files and Directories
1. -r : Copies directories recursively : cp -r dir1 dir2
2. -v : Displays copying information : cp -v file.txt backup.txt
3. -i : Prompts before overwriting : cp -i file.txt backup.txt
4. -f : Forces copying without prompting : cp -f file.txt backup.txt
5. -p : Preserves file attributes : cp -p file.txt backup.txt
6. -u : Copies only if the source is newer or destination is missing : cp -u file.txt backup.txt

# mv - Move or Rename Files
1. -i : Prompts before overwriting : mv -i file.txt backup.txt
2. -f : Does not prompt before overwriting : mv -f file.txt backup.txt
3. -v : Displays moving information : mv -v file.txt backup.txt
4. -n : Prevents overwriting an existing destination : mv -n file.txt backup.txt

# ln - Create Links
1. -s : Creates a symbolic (soft) link : ln -s file.txt link.txt
2. -f : Removes an existing destination before creating the link, when permitted : ln -f file.txt link.txt
3. -v : Displays link creation information : ln -v file.txt hardlink.txt

# grep - Search Text
1. -i : Ignores case sensitivity : grep -i "error" file.txt
2. -c : Count matching lines : grep -c "error" file.txt
3. -n : Displays matching line numbers : grep -n "error" file.txt
4. -v : Displays lines that don't match : grep -v "error" file.txt

# head - Display Beginning of File
1. -n : Displays the specified number of lines from the beginning : head -n 5 file.txt
2. -c : Displays the specified number of bytes from the beginning : head -c 20 file.txt

# tail - Display End of file
1. -n : Displays the specified number of lines from the end : tail -n 5 file.txt
2. -c : Displays the specified number of bytes from the end : tail -c 20 file.txt
3. -f : Continuously displays newly added content : tail -f log.txt

# history - Display Command History
1. -c : Clears the current shell's history list : history -c
2. -d : Deletes a specific history entry : history -d 5
3. -a : Appends new commands to the history file : history -a
4. -w : Writes the current history list to the history file : history -w

# less - View File Contents
1. -N : Displays line numbers : less -N file.txt
2. -S : Prevents long lines from wrapping : less -S file.txt
3. -F : Exits automatically if content fits on one screen : less -F file.txt

# more - View File Contents
1. -d : Displays helpful navigation prompts : more -d file.txt
2. -s : Suppresses consecutive blank lines : more -s file.txt
3. -n : Sets the number of lines displayed per screen : more -n 10 file.txt

# set - Shell Settings
1. -e : Exits a script when a command fails, subject to shell rules : set -e
2. -x : Displays commands as they execute : set -x
3. -f : Disables filename globbing : set -f

# env - Environment Variables
1. -i : Starts a command with an empty environment : env -i bash
2. -u : Removes a specified environment variable for the command : env -u HOME bash

# export - Export Variables
1. -p : Displays exported variables : export -p
2. -n : Removes the export attribute from a variable : export -n name

# unset - Remove variables
1. -v : Removes a variable : unset -v name
2. -f : Removes a function : unset -f f_name

# bash - Start Bash Shell
1. -c : Executes a command string : bash -c 'echo hello'
2. -i : Starts an interactive shell : bash -i
3. -l : Starts a login shell : bash -l
4. -n : Checks script syntax without executing it : bash -n script.sh
5. -x : Displays commands while executing a script : bash -x script.sh

# vi - Text Editor
1. -R : Opens a file in read-only mode : vi -R file.txt
2. -r : Attempts to recover an editing session : vi -r file.txt
3. -c : Executes an editor command after opening : vi -c 'set number' file.txt
