# Trashbin-Script
I created this trash bin script to safeguard against permanently deleting files using `rm` on my university server.
I currently use this script, and thought to share it with any other students who may want to use it as well. 

# Author: Kevin Filanowski

# Table of Contents
* [Features](#features)
* [How to Use](#how-to-use)
* [Installing](#installing)
* [Troubleshooting](#troubleshooting)

# Features
* Safety against duplicate file names and directories.
  * Deleting a file or directory with a name that already exists in the trash bin will simply append `_copy` to the file until that filename becomes unique. This ensures we have a backup of all files we delete.

* Creates a trash bin for you if a trash bin does not exist.
  * By default, this is in the home directory as ~/.trashbin
    * You can change the location of the trashbin by changing TRASHBIN variable in the script.
    
* Tells you how many files were successfully moved to the trash bin.

* Skips over files that don't exist in the arguments.

# How To Use
Simply type `rm <files>*` where `<files>` are as many files as you would like to delete.

# Installing
In order for the system to use this rm script instead of the default one, we need to edit our path variable to be in front of the default path variables. 

First, we need to pick a location to have the rm be in.
Let's say we have a folder in our home directory called `linux_tools`.
Then, for the following system:

### MacOS
Typing this command in your terminal will do the trick:
```
echo 'export PATH="~/linux_tools:$PATH"' >> ~/.bash_profile
source ~/.bash_profile
```

### Linux
Typing this command in your terminal will do the trick:
```
echo 'export PATH="~/linux_tools:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

# Troubleshooting
It is possible the permissions on the file are incorrect, we need to be sure that the script is executable.
You can fix this by typing:
`chmod 755 rm`
to add sufficient permissions to the script.
