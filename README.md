# Shell-Scripting
Shell scripting is the process of writing and executing a series of instructions in a shell to automate tasks. A shell script is essentially a script or program written in a shell language, such as Bash, sh, zsh, or PowerShell?

A basic shell script that will create multiple folders and create multiple linux users at once would look like this.

```
#!/bin/bash

# Create directories
mkdir Folder1
mkdir Folder2
mkdir Folder3

# Create users
sudo useradd user1
sudo useradd user2
sudo useradd user3
```


# Task

Create a folder on an Ubuntu server and name it shell-scripting.

Using the vim editor, create a file called my_first_shell_script.sh.

Put the shell script code above into the new file.

Save the file.

Use cd command to change into the shell-scripting directory.

Use ls -latr command to confirm that the file is indeed created.

![image](https://github.com/user-attachments/assets/576bc33a-de35-4541-9598-0f360df2462f)


Notice the permissions of the newly created file is this -rw-rw--r-- which means;

    The owner of the file has read (r) and write (w) permissions.

    Members of the file’s group have read (r) and (w) permissions.

    Others also have read (r) permission.

However, no one has the execute (x) permission, hence the script cannot be executed.

To execute the script, use the following command.

```
./my_first_shell_script.sh

```
![image](https://github.com/user-attachments/assets/70a16f5a-43e7-41bd-9839-c543c934c09e)



    To grant execute permission for the owner, use the following:
    ```
    chmod u + x my_first_shell_script.sh
   ```
and run run the foolowing for confirmation

  ```
  ls -latr
  ```
![image](https://github.com/user-attachments/assets/d35a948c-59d6-476a-88ff-648353bd0f49)

  
    

    Run the shell script

    Evaluate and ensure that 3 folders are created

    Evaluate and ensure that 3 users are created on the Linux server

Hint:

    Use the chmod command to update the permission

    Use ls to test that the folders are created

    Use id command to test that the users are created. You should see something like this:

