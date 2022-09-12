
question3.cpp
----------------------------
    - This is the main application source file.
    - Implemented a simple file system.


/////////////////////////////////////////////////////////////////////////////

Input 
-----------------------------

* Input is taken through Console.

* Input includes the following commands: 
	- mf file-name “filecontents”
	- df file-name
	- rf file-name1 file-name2
        - pf file-name 
        - ls


/////////////////////////////////////////////////////////////////////////////

Data structures used
------------------------------

* Two unordered maps are used to maintain the meta data and disk blocks

	=> meta_data : name of the file | inode number
	=> disk_blocks : inode number | number of blocks

* Two sets are used to check for the uniqueness of the file names and inode numbers.


/////////////////////////////////////////////////////////////////////////////

Commands
-----------------------------

* mf file-name “filecontents”
	=> first check for the uniqueness of the filename
	=> create a unique inode for file
	=> insert filename and corresponding inode into the meta data.
	=> insert the inode and filename into the sets for checking the uniqueness further.
	=> calculate the number of disk files required and create disk block files with inodeno_blockno

* df file-name
	=> check if the file with given name is present in the file system
	=> get the inode of the file to be deleted
	=> remove the file entry from the meta data
	=> retrieve the number of disk files created for the file to be deleted
	=> remove the disk block entry from the file
	=> delete all the disk files.
	=> remove the file from the list of files
	=> remove the inode from the inode list.

* rf file-name1 file-name2
	=> check whether the new filename is unique
	=> check if the file with given name is present in the file system
	=> rename the filename in the metadata
	=> remove the file from the list of files
	=> insert the new filename into the list of files

* pf file-name 
	=> check if the file with given name is present in the file system
	=> get the inode of the file to be displayed
	=> retrieve the number of disk files created for the file to be displayed
	=> display all the disk file contents

*ls
	=> list all the files from the meta_data 


/////////////////////////////////////////////////////////////////////////////
