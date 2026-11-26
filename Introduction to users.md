# Introduction to Users
- A user in Linux is an account that allows a person or process to access and interact with the operating system.
- Linux supports multiple users, meaning several users can use the same system while maintaining separate permissions and access.
- Types of users in Linux:
   1. Root User
       - Also called superuser.
       - Has almost complete control.
       - Can install software, modify system configurations, create users and manage permissions.
       - Root user ID (UID) is 0.
   2. Regular User
       - Created for normal system usage.
       - Has limited permissions
       - Cannot normally modify protected system files.
       - Usually UID 1000 or higher on many Linux distributions
   3. System User
       - Created to run system services and applications
       - Usually does not log in interactively
       - Examples include users created for services such as databases and web servers.
       - Often have lower UIDs, depending on the distribution.

## whoami 
- Displays the username of the user who is currently executing the command.
## who
- Displays users currently logged into the system.
- -H : Displays Headings for the output
- -b : Displays when the system was last booted
- -q : Display logged-in usernames and count
- -r : Display current run level
## id 
- Displays user ID, group ID and group memberships
- In simple words, it tells us who the user is and which groups the user belongs to.
### Important options of id
- -u : Display only UID
- -g : Display the numerical ID of the user's primary group
- -G : Displays the numerical IDs of all groups the user belongs to
- -n : The option -n is used with -u, -g, or -G to display names instead of numerical IDs.
- -r : Display real ID instead of effective ID. Also used with -u and -g.
- root : Check another user's information.

## su -Switch User
- It is used to switch from your current Linux user account to another user account.
- su username : This will switch to another user without starting a full login environment.
- su - username : This will switch to another user and loads the full login environment.

## visudo
- visudo is used to edit the /etc/sudoers file, which controls which users or groups are allowed to execute commands with administrative privileges using sudo.
- To add the user to get the permissions : username ALL=(ALL:ALL) ALL
