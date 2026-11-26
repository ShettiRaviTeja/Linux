# Linux File Permissions
- Linux file permissions control who can access files and directories and what operations they can perform.

## chown - Change file ownership
### What is file ownership
- Every file and directory in Linux has an owner and an associated group.
### What is chown?
- It stands for Change Ownership.
- It is used to change the owner of a file or directory, and optionally its group ownership.
- Syntax : chown [OPTIONS] USER[:GROUP] FILE

### Practical Examples
1. Change the file owner
   - Suppose employees.txt currently belongs to ravi, and you want to assign ownership to employee1.
   - sudo chown employee1 employees.txt
   - Now employee1 becomes the owner of the file.
2. Change the group ownership
   - sudo chown :developers employees.txt
   - This changes the group ownership to developers without changing the current owner.
3. Change both owner and group
   - sudo chown employee1:developers employees.txt
   - Now owner is employee1 and group is developers
4. Change ownership of a directory recursively
   - sudo chown -R employee1:developers project/
   - The -R flag means recursive.
  
## chmod - Permissions
- chmod stands for Change Mode.
- It is used to change the permissions of files and directories in Linux.
- Linux provides three basic permission types:
  - Read : r : Read file contents or list directory contents
  - Write : w : Modify a file or create/delete directory entries
  - Execute : x : Execute a file or access/traverse a directory
### Who can receive permissions?
- Linux permissions are divided into three categories:
  - User : u : File owner
  - Group : g : Group associated with the file
  - Others : o : Everyone else
  - All : a : User, group and others
- Syntax : chmod [OPTIONS] PERMISSIONS filename

- There are two ways to assign permissions:
  1. Symbolic method
  2. Numeric method

1. Symbolic Method
  - It uses letters and operators to modify permissions.
  - + : Add permissions
  - - : Remove permissions
  - = : Set exact permissions
### Examples:
  1. Add execute permission to the owner: chmod u+x employees.txt
  2. Remove write permission from the group: chmod g-w employees.txt
  3. Give read permission only to others: chmod o=r employees.txt
  4. Give read, write and execute permissions to everyone: chmod a+rwx employees.txt

2. Numeric Method
   - Each permission has a numerical value:
   - Read (r) : 4
   - Write (w) : 2
   - Execute (x) : 1
   - Permission 755 : First number to user, second to group and third to others.

## Sticky Bit on Directories
### What is a sticky bit?
- A sticky bit is a special permission used mainly on shared directories.
- It ensures that users cannot delete or rename files belonging to other users, even when they have write permission on the directory.
### How to set the sticky bit?
- Two methods:
  1. Symbolic method:
     - chmod +t shared/ : Here +t enables the sticky bit.
     - chmod -t shared/ : It removes the sticky bit.
  2. Numeric method:
     - The sticky bit has a special numeric value of 1.
     - chmod 1777 shared/
- t : Sticky bit enabled, and others have execute permission.
- T : Sticky bit enabled, but others do not have execute permission.
