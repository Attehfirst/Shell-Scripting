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

![shell06](https://github.com/user-attachments/assets/ed506e96-1387-4413-9f82-c3e51cc7506f)
