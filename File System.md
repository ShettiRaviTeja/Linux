# File Systems
- A filesystem is a method used by an operating system to organize, store, manage and retrieve data on storage devices.
- In simple words, a filesystem helps Linux organize files and directories on a hard disk, SSD, USB drive, etc.
- When we create a file: touch employees.txt,
  - Linux uses the filesystem to store information about that file, such as:
    - File name
    - File size
    - File permissions
    - File ownership
    - File location on the storage device
    - File timestamps

## Types of Filesystems
- A filesystem determines how data is stored and organized on a storage device.
  
### 1. ext2 (Second Extended Filesystem):
- Older Linux Filesystems.
- Does not support journaling.
- If the system crashes unexpectedly, filesystem recovery can take longer.
- Less commonly used in modern Linux systems.
- Important : Journaling means keeping a record of filesystem changes to help recover from unexpected crashes.

### 2. ext3 (Third Extended Filesystem):
- Introduced journaling.
- More reliable than ext2 during unexpected shutdowns.
- Supports backward compatibility with ext2.

### 3. ext4 (Fourth Extended Filesystem):
- An improved version of ext3.
- Supports journaling.
- Supports large files and large filesystems.
- Provides better performance and reliability.
- Commonly used in Linux distributions.

### 4. XFS
- High-performance journaling filesystem.
- Designed to handle large files and large storage volumes.
- Supports high-performance parallel operations.
- Commonly used in enterprise Linux environments.

### Btrfs (B-tree Filesystem)
- Advanced Linux filesystem
- Supports snapshots
- Supports compression
- Supports checksums for data integrity
- Supports subvolumes
- Example : Snapshots allow you to capture the state of a filesystem at a particular point in time.

### FAT32
- Commonly used in USB drives and memory cards.
- Compatible with Windows, Linux and other operating systems.
- Maximum individual file size is 4 GB (technically 4 GiB minus 1 byte).
- Does not support Linux-style file permissions natively.

### NTFS
- Primarily used by Windows
- Supports large files and file permissions
- Supports journaling.
- Linux can read and write NTFS using appropriate filesystem drivers.

### Swap
- Used as virtual memory in Linux.
- Provides additional memory space when physical RAM is insufficient.
- Can be configured using a swap partition or swap file.
- It is not a general-purpose filesystem for storing normal files.

## Filesystem Structure
- Linux organizes files and directories in a hierarchical structure, starting from a single root directory represented by /.
### 1. Root directory /
- It is the starting point of the entire Linux filesystem hierarchy.
  - All files and directories exist under /.
  - It is the top-level directory.
  - Every mounted filesystem is accessible somewhere under this hierarchy.
- / is the root directory of the entire filesystem.
- /root is the home directory of the root user.
- /home/raviteja is the home directory of the normal user Ravi Teja.

### /bin directory
- /bin stands for Binary.
- It contains essential executable commands required for basic system operations.
- Examples of commands traditionally found in /bin:
  - ls - list files and directories
  - cp - copy files
  - mv - move files
  - cat - display file contents
  - mkdir - create directories
  - rm - remove files
  - bash - shell interpreter
- ls /bin : Lists the executables available in /bin.

### /boot directory
- /boot contains the files required to start (boot) the Linux operating system.
- Important files:
  - vmlinuz : Compressed Linux kernel image
  - initrd : Temporary initial filesystem used during boot
  - grub/ : GRUB bootloader configuration and related files
  - System.map : Symbol table associated with the kernel
- Practical commands
