# Access Control List
- In Linux, normal file permissions allow us to assign permissions to three categories:
  1. User (Owner)
  2. Group
  3. Others
- But what if you want to give read permission to one specific user without changing the permissions of the existing group or others? This is where ACL comes in.

## 1. getfacl - Get File Access Control List
- It is used to display the ACL permissions of a file or directory.
- Syntax : getfacl filename

## 2. setfacl - Set File Access Control List
- It is used to add, modify, or change ACL permissions for specific users and groups.
- Syntax: setfacl -m u:username:permissions filename

## 3. Remove an ACL entry
- We use setfacl -x to remove a specific ACL entry.
- Syntax: setfacl -x u:john:rw employees.txt
- -b : Used to remove all the ACL entries : setfacl -b file.txt

## 4. ACL Mask
- The ACL mask defines the maximum effective permissions available to:
  - Named users (additional users)
  - The owning group
  - Named groups (additional groups)
- In simple words, even if you assign higher permissions to a user or group, the ACL mask can restrict their effective permissions.
- The ACL mask applies to the owning group, named users and named groups, but not to the file owner or others.
- How to set ACL mask : setfacl -m m:username:permissions
