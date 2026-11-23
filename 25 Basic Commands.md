# Linux Commands
- Linux commands are used to interact with the operating system through the terminal and perform tasks like file management, navigation, and system monitoring.

# 25 Basic Linux Commands
1. ls: Used to list files and directories present in the current working directory.
  - ls
2. pwd: Used to display the full path of the current directory.
  - pwd
3. mkdir: Used to create new directories or folders.
  - mkdir directory_name
4. cd: Used to change the current working directory.
  - cd directory_name
5. rmdir: Used to remove the empty directories.
  - rmdir directory_name
6. cat: Used to display file contents and combine multiple files.
  - cat file_name
7. cp: Used to copy files or directories
  - cp source destination
8. mv: Used to move or rename files and directories.
  - mv old_name new_name
9. rm: Used to delete files permanently.
  - rm file_name
10. uname: Used to display system information. Showing operating system details. Helps identify the system.
  - uname [OPTIONS]
11. locate: Used to find files using a database.
  - locate file_name
12. touch: Used to create empty files and updates file timestamps.
  - touch file_name
13. ln: Used to create links between files.
  - ln -s source link_name
  - Original and hardlink will have the same inode whereas softlink have different inode.
14. clear: Used to clear the terminal screen.
  - clear
15. ps: Used to display running processes.
  - ps
16. man: Used to display command manuals.
  - man command_name
17. grep: Used to search text patterns. Finds specific strings. Filters output.
  - grep "text" file_name
## 18. Ways for Writing to the files
- Using echo: Write a line of text.
  - echo "your content" > filename.txt
  - '>' overwrites existing content.
  - '>>' appends content without deleting existing content.
- Using cat: Write multiple lines.
  - cat > filename.txt
  - Now type the text and press Ctrl + D.
- Using nano: Edit files using a simple text editor.
  - nano sample.txt
  - Write your content.
  - Press Ctrl + O to save.
  - Press Enter to confirm the filename.
  - Press Ctrl + X to exit.
- Using vi/vim: Edit files using a terminal-based editor.
  - vi sample.txt
  - Press i to enter Insert mode.
  - Write your content.
  - Press ESC.
  - Type ':wq' and press Enter
  - Here: w means write(save) and q means quit.
19. wget: Used to download files from the internet using URL.
  - wget url
20. whoami: Used to display the current user.
  - whoami
21. sort: Used to sort file contents.
  - sort file_name
22. cal: Used to display the calendar.
  - cal
23. whereis: Used to locate the command files. Shows binary location.
  - whereis command_name
24. df: Used to display disk space usage.
  - df [options]
25. wc: Used to display number of lines, words, and bytes in the file.
  - wc [OPTION] file_name
