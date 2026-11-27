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
  - ls -lh /boot : List the contents of /boot.
  - uname -r : Check the currently running kernel version.
  - ls /boot/vmlinuz* : List installed kernel images.

### /dev directory
- /dev stands for Devices.
- It contains special files that represent hardware devices and virtual devices.
- Important examples:
  - /dev/null : Discards anything written to it.
  - /dev/zero : Produces continuous zero bytes.
  - /dev/random : Provides random bytes.
  - /dev/tty : Represents the current terminal.

### /etc directory
- /etc contains system-wide configuration files.
- Important files:
  - /etc/passwd : Stores user account information
  - /etc/shadow : Stores password hashes and password aging information
  - /etc/group : Stores group information.
  - /etc/hostname : Contains the system hostname.
  - /etc/hosts : Maps hostnames to IP addresses.

### /home
- /home directory contains personal directories belonging to normal users.
- Important commands:
  - echo $HOME : Check your current home directory.
  - cd ~ : Navigate to your home directory.
  - ls /home : List all user home directories.

### /lib
- It stands for Libraries.
- It contains essential shared library files required by basic system commands and programs.
- Important contents:
  - /lib : Essential shared libraries
  - /lib/modules : Kernel modules.
  - /lib/firmware : Firmware files

## Mounting and Unmounting file systems
- Mounting : It is the process of making a filesystem accessible to the Linux operating system by attaching it to a directory.
- In simple words, mounting allows us to access the files stored on a disk, partition, USB drive, or other storage device.
### What is Mount Point
- A mount point is a directory in the Linux filesystem where another filesystem is attached.
- For example, /mnt/usb contains files which are accessed by the linux system using USB. Then it is called as Mount point.
### How to identify Disks and Partitions?
- Before mounting a filesystem, we need to identify the storage device and its partitions.
- lsblk : Displays block devices such as hard disks, SSDs and their partitions.
### How to Mount a Filesystem
- Suppose
  - Device: /dev/sdb1
  - Mount Point: /mnt/usb
1. Create a mount point
   - sudo mkdir /mnt/usb
2. Identify the filesystem
   - lsblk -f
3. Mount the filesystem
   - sudo mount /dev/sdb1 /mnt/usb
4. Verify the mount
   - df -h or lsblk
   - You should see /mnt/usb as the mount point.
5. Access the files
   - cd /mnt/usb
   - ls
### How to Unmount a Filesystem?
- Unmounting is the process of safely detaching a mounted filesystem from the Linux directory structure.
- Command: sudo umount /mnt/usb
- We can unmount using the device name or mount point name.
