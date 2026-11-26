# Group Management
- Used to manage permissions for multiple users together.

## a. groupadd
- Used to create a new group in Linux.
- When we create a group, Linux assigns it a unique Group ID (GID).
- Syntax : sudo groupadd groupname
### Important groupadd flags
- -g : Specify a custom GID
- -f : Exit successfully if the group already exists; otherwise create it
- -r : Create a system group
- -o : Allow a non-unique GID (Used with -g)

## b. groupmod
- Used to modify an existing Linux group.
- Use it to change the group name or GID.
- Syntax : sudo groupmod [OPTIONS] groupname
### Important flags
- -n : Change the group name
- -g : Change the GID
- -o : Allow a non-unique GID (used with -g)

## c. groupdel
- Used to delete an existing group from Linux.
- Syntax : sudo groupdel groupname

## d. gpasswd
- Used to manage group membership and group passwords.
- It allows administrators to:
  - Add users to group
  - Remove users from a group
  - Manage group administrators
- Syntax : sudo gpasswd [OPTIONS] groupname
### Important flags
- -a : Add a user to a group
- -d : Remove a user from a group
- -A : Set group administrators
- -M : Set the complete list of group members
