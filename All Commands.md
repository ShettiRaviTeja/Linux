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
