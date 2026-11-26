# File Links
## A. Inodes
### What is an Inode?
- Inode stands for Index Node.
- An inode is a data structure in Linux that stores the metadata (information) about a file or directory.
- An inode stores information such as:
  - File permissions
  - File owner
  - Group owner
  - File size
  - Timestamps
  - Number of hard links
  - Location of the file's data blocks
- Important: An inode does not store the filename. The filename is stored in the directory entry, which maps the filename to its inode number.
- Command to see the inode number of a file : ls -i filename

## B. Hard Links
- A hard link is an additional filename that points to the same inode as the original file.
- In simple words, two different filenames refer to the same underlying file data.
- Syntax : ln original_file.txt hardlink.txt
- After creating the hard link to the original link
