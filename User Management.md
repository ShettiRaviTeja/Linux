# User Management
## a. /etc/passwd
### 1. What is /etc/passwd 
- It is a system file in Linux that stores information about user accounts.
- Whenever a user account is created, its account information is generally added to this file.
- It is a file, not a command.

### 2. How to view all users
- cat /etc/passwd
- To display only username: cut -d: -f1 /etc/passwd

### 3. Understanding the file structure
- raviteja:x:1000:1000:Ravi Teja:/home/raviteja:/bin/bash
- Each field is separated by a colon (:)
- raviteja : Username
- x : Password placeholder
- 1000 : User ID (UID)
- 1000 : Group ID (GID)
- Ravi Teja : User Info (Comment)
- /home/raviteja : Home directory
- /bin/bash : Default login shell

### Important Commands
- View a particular user's information : grep raviteja /etc/passwd
- Display only usernames : cut -d: -f1 /etc/passwd
- Count the number of local user accounts : wc -l /etc/passwd

## b. useradd
- Used to create a new user account in Linux.
- Syntax : sudo useradd username
- sudo useradd employee1 : This creates a user account named employee1 but may not create a home directory.
- To create user along with the home directory : sudo useradd -m employee1

### Important useradd flags
- -m : Create a home directory
- -M : Prevents to create a home directory
- -u : Specify a UID
- -g : Specify the primary group
- -G : Specify supplementary groups
- -s : Specify the login shell
- -c : Add a comment or description
- -d : Specify the home directory path
- -e : Set account expiration date

## c. /etc/default/useradd
- This file stores the default settings used when creating new Linux user accounts.
- 1. How to view the file : cat /etc/default/useradd
### Understanding SKEL
- The skeleton directory usually contains default configuration files that are copied into a newly created user's home directory.
- To see those files : ls -la /etc/skel

## d. userdel
- Used to delete an existing user account from a Linux system.
- Syntax : sudo userdel username
- sudo userdel employee1 : It will delete the user but generally keeps its home directory and files.
### Important flags
- -r : Removes the user's home directory and mail spool
- -f : Force deletion in certain situations
- After deleting, check the user by using the command : getent passwd employee1

## e. usermod 
- Used to modify or update an existing Linux user account.
- Syntax : sudo usermod [OPTIONS] username
### Important flags
- -l : Change username : sudo usermod -l newname oldname
- -u : Change UID
- -g : Change primary group
- -G : Change supplementary group
- -aG : Add supplementary groups without removing existing ones
- -d : Change home directory path
- -s : Change login shell
- -L : Lock user account password
- -U : Unlock user account password
- -e : Set account expiration date
