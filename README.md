# RecycleBin
Problem:
UNIX has no recycle bin at the command line.  When we remove a file or directory, it is gone and cannot be restored.
This project is to write a recycle script and a restore script. This will provide users with a recycle bin which can be used to safely delete and restore files.

# Recycle Script
---------------
The recycle bin will be created at $HOME/recyclebi by the script.

The script should be executed as follows to delete a file: 	bash recycle fileName 

When any of the following are encountered, the script displays the same kind of error messages as the rm command.
a)	No filename provided 
b)	File does not exist 
c)	Directory name provided instead of a filename
d)	Filename provided is recycle. In this case, display the error message “Attempting to delete recycle – operation aborted” and the script will be terminated with a non-zero exit status.

The filenames in the recyclebin, will be in the following format:
fileName_inode
For example, if a file named f1 with inode 1234 is recycled, the file in the recyclebin will be named f1_1234. 
This gets around the potential problem of deleting two files with the same name. 
The recyclebin only contain files, not directories. 

# Restore Script
----------------
"restore" restores individual files back to their original location.
The user will determine which file is to be restored and use the file name with inode number in order to restore the file.  
For example:  bash restore f1_1234
