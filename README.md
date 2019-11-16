# Trashbin-Script
Trash bin script to safeguard against permanently deleting files using rm by accident.
Instead of `rm` permanently deleting files with no chance of recovery, I created a script that sends the files safely to a trash bin. 

# Author: Kevin Filanowski

# Features
*  Safety against duplicate file names and directories.
  * Deleting a file or directory with a name that already exists in the trash bin will simply append `_copy` to the file until that filename becomes unique. This ensures we have a backup of all files we delete.

* Creates a trash bin for you if a trash bin does not exist.
  * By default, this is in the home directory as ~/.trashbin
    * You can change the location of the trashbin by changing TRASHBIN variable in the script.
    
* Tells you how many files were successfully moved to the trash bin.

* Skips over files that don't exist in the arguments.
