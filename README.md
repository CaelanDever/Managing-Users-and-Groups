# Managing-Users-and-Groups

# Task: Secure User and Group Management for File Access

# 1. Create a New Group

Command:

sudo groupadd securegrp


<img width="301" alt="gr" src="https://github.com/user-attachments/assets/088d7d75-3cef-46d3-92b1-05c218ced010">

Explanation:

groupadd is a command used to create a new group in Linux.
securegrp is the name of the group being created.

sudo is used to run the command with superuser (root) privileges, which are typically required for creating groups.

Purpose: Creating groups allows you to manage permissions more easily by assigning multiple users to the same group, so you can control access to files and directories based on group membership.

# 2. Create a New User and Add to the Group
Command:

sudo useradd -m -G securegrp secureusr

<img width="282" alt="secure" src="https://github.com/user-attachments/assets/461da860-97ec-40e2-b81f-539027538bcb">


Explanation:

useradd is the command used to create a new user.

-m creates a home directory for the new user (/home/secureusr).

-G securegrp specifies that the new user should be added to the securegrp group.

secureusr is the name of the new user.

Purpose: Creating a user and adding them to a group allows you to manage file access and permissions specific to this user, particularly within the context of the securegrp group.

# 3. Set a Password for the User

Command:

sudo passwd secureusr

<img width="283" alt="pass" src="https://github.com/user-attachments/assets/2999bea5-55aa-4070-9e0e-4a5e6955542b">


Explanation:

passwd is used to set or change the password for a user.

secureusr is the username for which the password is being set.

Purpose: Setting a password is essential for user authentication. It ensures that only the authorized user (secureusr) can log in and access their account.

# 4. Create a Directory Named securefiles

Command:

sudo mkdir /home/secureusr/securefiles

Explanation:

mkdir is the command used to create a new directory.

/home/secureusr/securefiles specifies the path where the new directory will be created.

Purpose: Creating a directory within the user's home directory allows the user to store files securely in a designated location. This directory can be used to segregate files that should be managed with specific permissions.

# 5. Change Ownership of the Directory

Command:

sudo chown secureusr:securegrp /home/secureusr/securefiles
Explanation:

chown changes the ownership of files or directories.
secureusr:securegrp sets the ownership to the secureusr user and securegrp group.
/home/secureusr/securefiles specifies the directory whose ownership is being changed.
Purpose: Changing ownership to secureusr and securegrp ensures that the user and their group have control over the directory, while other users do not have access unless explicitly granted.

6. Set Permissions on the Directory
Command:

bash
Copy code
sudo chmod 770 /home/secureusr/securefiles
Explanation:

chmod changes the permissions on files or directories.
770 is the permission setting:
7 (read, write, execute) for the owner (secureusr).
7 (read, write, execute) for the group (securegrp).
0 (no permissions) for others.
Purpose: Setting the permissions to 770 ensures that only the owner (secureusr) and the group (securegrp) have full access to the directory. No other users can access or modify the directory.

All 3 commands together:

<img width="378" alt="sdss" src="https://github.com/user-attachments/assets/00018d61-4fbe-4f9e-9913-533727e589b0">

# Confirmation:

<img width="378" alt="com" src="https://github.com/user-attachments/assets/34a6d1ff-d3a5-4a79-91f1-4ecb84b8be90">



Summary
By following these steps, you:

Created a group (securegrp) to manage access control.
Added a user (secureusr) to this group.

Set a password for secure authentication.
Created a directory (securefiles) in the user's home directory for storing files.

Assigned ownership of the directory to the user and group.

Configured permissions to ensure that only the user and their group can access and modify the directory, while others are denied access.

This setup is useful for securing file access, ensuring that sensitive files are only accessible by the intended users and groups.

