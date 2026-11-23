# Architecture
- Linux architecture is the layered structure of the Linux operating system that defines how components like the kernel, shell, system libraries, and hardware interact to manage resources and run programs efficiently.

<img width="585" height="400" alt="image" src="https://github.com/user-attachments/assets/e1d51434-f760-4ced-b128-1b42263adfa4" />

## What is Kernal in Linux?
- The kernel is the central component of an operating system that manages hardware resources and provides communication between hardware and software through system calls.

**How does a Kernal work?**
- Imagine you open a browser on your computer.
- What happens behind the scenes?
  1. You click the browser icon.
  2. The operating system requests memory (RAM) to run the browser.
  3. The kernel allocates the required memory.
  4. The kernel schedules CPU time for the browser.
  5. The browser starts running.
  So, the kernel manages the hardware resources required by the browser.

## System Libraries
- System Libraries provide functions that help applications interact with the Linux kernal.
- For example:
  - C library (glibc), math library

## Shell
- A Shell is a command-line interpreter that acts as an interface between the user and the operating system, allowing users to execute commands and manage system resources.
- Examples of Linux Shells:
  - Bash (Bourne Again Shell)
  - Zsh (Z Shell)
  - Korn Shell (Ksh)
  - Fish Shell
## Hardware Layer
- Hardware layer includes physical components like CPU, RAM, storage, and input/output devices.

## System Utilities
- System utilities are built-in tools used for system management, configuration, and maintenance.
- For example:
  - ls: Lists files and directories
  - mkdir: Creates a directory
  - cp: Copies files
  - mv: Moves or renames files
  - rm: Deletes files
  - ps: Displays running processes

## Applications
- Applications are user-level software programs that utilize system libraries and operating system services to perform specific tasks.
