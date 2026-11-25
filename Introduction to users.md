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
