# Absolute Path
- An absolute path specifies the complete location of a file or directory starting from the root directory (/).
- It does not depend on your current working directory.

# Relative Path
- A relative path specifies the location of a file or directory relative to your current working directory.
- It does not start from the root directory.

# Working with directories
- pwd
- cd
- Absolute path and relative path
- ls
- mkdir
- rmdir

# Working with files
- touch
- rm
- cp
- mv

# Working with file contents
- head: Used to display the first few lines of one or more text files directly in the terminal.
  - head [options] [file(s)]
- cat
- tail: Used to display the last few lines of one or more text files.
- more: The more command displays file contents page by page. It allows you to move forward through the file.
- less: The less command also displays file contents page by page, but it provides more navigation options than more.

# Shell variables
- Used to store information that can be accessed and used by the shell and commands.
- $ dollar sign: Used to access the value stored in a variable.
- set: Displays shell variables, functions and other shell settings.
- unset: Used to remove a variable.
  - unset var_name
- $PATH variable: It is an environment variable that stores a list of directories where linux searches for executable commands.
- env: Used to display environmental variables.
- export: Used to make a shell variable available to child processes as an environment variable.

# Shell history
- history: The history command in Linux displays a list of commands that were previously entered in the terminal. By default, it shows the last 1000 commands but this can be configured.
  - history [number]
- !n: Used to execute a previously executed command using its history number.
- Ctrl + R: Keyboard shortcut used to search previously executed commands.

# File globbing
- File globbing is a technique used in Linux to match multiple filenames using special characters called wildcards.
- asterisk(*): * is used to match any number of characters(zero or more).
- question mark(?): ? is used to match exactly one character.
- Square Brackets []: Used to match the characters inside [].
- exclamation mark (!): Used to exclude characters from the list that is specified within the square brackets.

# Filters
- Filters are commands that take input from standard input (stdin), process it, and send the modified output to standard output (stdout). They are commonly used in pipelines to transform or extract specific data from a stream of text.

- cat: Displays the text of the file line by line.
- sort: Sort the lines alphabetically by default but there are many options available to modify the sorting mechanism.
- tee : The tee command reads input and sends it to two places simultaneously:
  1. Displays the output on the terminal
  2. Writes the output into a file
  - Example: ls | tee output.txt
  - Append instead of overwrite: ls | tee -a output.txt
- grep - Used to search for specific words or patterns in files or command output
  - -i : Ignore uppercase and lowercase
  - -n : Displays matching lines along with their line numbers.
- cut : Used to extract specific fields or characters from each line of a file.
  - -d : delimiter
  - -f : field
  - Example: cut -d ',' -f 2 employees.csv
- tr : Used to translate, replace or delete characters from input.
  - Example 1: echo "hello world" | tr 'a-z' 'A-Z'
  - Example 2: echo "hello world" | tr ' ' '_'
  - Example 3: echo "hello123" | tr -d '0-9'
- wc : Used to count lines, words, characters, and bytes in a file.
  - -l: Counts lines
  - -w: Counts words
  - -c: Counts bytes
  - -m: Counts characters
- sort : Used to arrange lines in alphabetical or numerical order.
  - sort -n numbers.txt : Sort based on numerical values.
  - sort -r numbers.txt : Sort in descending order.
  - sort -n numbers.txt -o sorted.txt : Sorts the numbers and saves the result in sorted.txt
  - -u : Removes duplicates lines while sorting.
  - -f : Ignores case differences
- uniq : Used to identify or remove consecutive duplicate lines.
  - Example: uniq names.txt
  - uniq -c names.txt : Count repeated lines
  - uniq -d names.txt : Display only duplicate lines
- sed : Stream Editor is used to search, replace, delete, and modify text in a stream or file.
  - sed 's/Hello/Hi/' file.txt : Replace the single occurence
  - sed 's/Hello/Hi/g' file.txt : Replace all occurences
  - sed '2d' file.txt : Delete the 2nd line
  - sed -i 's/Hello/Hi/g' file.txt : -i modifies original file directly.
- Pipe (|) : Used to send the output of one command as the input to another command

- awk : Powerful text-processing tool used to extract columns, filter records and perform calculations.
  - awk '{print $2}' employees.txt
  - awk '{print $1, $2}' employees.txt
  - awk '$3 > 35000' employees.txt
  - awk '{sum += $3} END {print sum}' employees.txt
  - awk -F ',' '{print $2}' employees.csv

- jq : Used to parse, filter, extract and transform JSON data from files or command output.
