# understanding File Permision

## What is File Permision
In linux, File permissions, attributes and ownership control the access level that the system process and users have to files. File permissions are file system attributes of files and directories that control the control the ability of file users to read, modify, navigate and execute the content of a file/file system.

## Why File Permision in Linux
..Let see some History..

Linux get out of the Unix, as the case will be Unix system are design to be mulit-user operating system which can be accessd by multiple users simultaneously. This was so due to the way computer was then. where we have a large room dedicated to computer and we have terminals in other room through which input are sent in processing to the mainframe computer. 

Linux was also design with this in mind and can bu used in mainframe and servers without any modification. We can have  more than one user operating the computer at the same time. The computer can be attached to a network or the internet, and remote users can log via ssh(secure shell).

## The Downside Of Multi-Users Accessing the Computer the same time.
Multi-users advantage raises security concerns as an malicious user can corrupt modify and delete important data and files on  the system.

Moreso since multiple users will be accessing the same computer, there will a need  to protect each user from accessing files belonging to themselves, and also devise a means of not allowing the action carried by one user put the whole system in jeopardy,

Hence, there will a need to have of a way of passing restrictions on file that the user can have acess to and this protect each user file from another. There should be a way to ensure that only authorized users and process can have access to specific files and directories.

This security concern birth the unix or Linux file permissions.

##  Unix and Linux Implementation of File Permision
Everything is file on  the linux system, and each file and directories is assigned access rights for the owner of the file, the members of a group of related users and also everybody else.

### Permision Scope(Type of User)
Permissions on linux file system are managed in three scopes or classes which are itemize below.

* Owner : This is  the user who created the file and folder and he grant the other types of users to acess the fie and folder. It is denoted by 'u'

* Group : Each users can belong to a particular group in linux. group refers to related users. They can have access  to the file. This is very is crucial when we have mulitple users working on a particular folder or file- it is denote by 'g'.

* Others/All : It indicate any user who is not  the owner of a particualar file of folder and does not belong to the file or folder owner's group.'o' is use to denote all other users and 'a' is used to denote all users.


### Permissions
It is important to note that unix-like system(linux inclusive) implement three speicfic permissions that applies to each each class or types of user.

* Read :This permissions is denoted by 'r' when define by character and it is denoted by'4' when defined by a number. The read permissions grants the ability to read a file. when set for a directory of file, this grants the ability to read the names of files in the directory,but not to find out any further information about them such as contents, file type, size, ownership, permissions.

* The Write : This permission is denoted by "w" or '2'. This grants the ability to modify and change the file.The allow the users to modify the entries and this include creating files, deleting files and renaming the files.However the write permissions require execute to set without it the write permissions is useless.

* The Execute : It is denoted by 'x' or '1'. This grants the ability to execute a file. This permissions must be set for executable programs in order to allow the operating system to  run  them.

[link](http://linuxcommand.org/lc3_lts0090.php)

## Shell Commands to Manipulate File Privileges/Permissions

* chmod : This is used to change the permission of a file  of directory. We specify the desired permission settings and the file that we wish to modify. 

Usage: chmod [Permission] [file_path or folder]

Using chmod file can be modify in two ways : octal notation method. the permission are represent in using 3 bits. The first 3-bit indicate the owner, the second 3-bit indicate the group, the last 3-bit indicate others. The permission can also be change using the symbolic mode.

### Examining the octal notation 

Considering a regualar linux file : using the ls -l file, display the longlist of the file attributes. we can have the following below display

* - rwx rw- r--
  |  |   |  |------------others
  |  |   |
  |  |   |----------------group
  |  |   
  |  |-----------------------------owner
  |
  |--------------------------file of folder or link

* - means it a regular file

#### Understanding Permission settings using the octal representation

Note : each character(r,w,x) use 1, if - is used 0.

* rwx rwx rwx = 111 111 111. In octal notation : 777 meaning no restrictions on permission.

* rw- rw- rw- = 110 110 110. In octal notation : 666 meaning all users may read and write the file.

* rw- r-- r-- = 110 100 100. In ocal notation : 644 meaning that the owner may read and write the file while other may only read the file.

* rwx --- --- = 111 000 000. In octal notation : 700 meaning the owner may read, write and execute the file. the file is kept private.

The above aswell can be represented in octal format

* rwx = 111 in octal = 7

* rw- = 110 in octal = 6

* r-x = 101 in octal = 5

* r-- = 100 in octal = 4 

... and so on.

#### Directory Permission 
chmod can also be use to control the access permissions for folder. octal notation above can be use but the meaning of r,w,x is differnt

* r : means allow the content of the folder to be listed if the execute attribute(x) is set.

* w : this allow files within the folder/directory to be created, deleted or renamed. It also requires the execute attribute to be set as well.

* x : this allows user to be able to navigate the directory and see the content.

Some directory permission:
* 777: means no restrictions. whosoever can list files and create new files in the directory aswell as delete the content.

* 755 : means the owner or the creator of the directory has full control. The others can only just list the directory content.

* 700 : means that the owner has full access. The directory is kept private.

Also recal that read can be represent by 4, execute 1 and write 2. this is will come in handy later on as we delve into symbolic mode in setting files persmissions.




### Examing the Symobolic mode
[link](https://linuxhint.com/linux_file_permissions/)

Recall that the owner is denoted by 'u', the group is denoted by 'g' and others by '0' and all by 'a'. More so, recall permission scope which are r(read), w(write) and x(execute).

Another important thing to note is some symbols

* + : to add or assign permissions for a particualar file of folder

* = : to reasign the permissions for the particular file or folder

* - : it used to remove the permissions from the particualar file or foilder.

Let's go down the rabbit hole..

- __Given a file with the following permission: 700 i.e rwx --- ---, let change the permision to group(g) to read write and execute i.e 770__

* chmod g+rwx file_name. the file change to rwx rwx --- in octal 770.

another example:
given a file a app.py with folowing permisions
rw- r-- r--, which is 110 100 100 in octal notation : 644.

- __let's give the owner of the file(u) ability to execute(x)__

* chmod u+x app.py

This becomes rwx r-- r--, which is 744

Let's see another example:

- __let's set write and execute permission for any user of a file__

consider a file cloud.py with the permission :444 i.e r-- r-- r--

* chmod a+wx cloud.py
w(write) and x(execute) has been assign to the file cloud.py.

file permission now becomes rwx rwx rwx : 777. 

Note 'a' means all users

- __Let's Reset Permissions for group of a file__

Given a file - -rw- rw- r--, let reset the group permision to execute(x)
.this will revoke the read and write priviledges.

     chmod g=x file_name

The result: - -rw- --x r--
This commands will turn off two permissions and reset it to the one passed to it.

The opposite of this is the '-' rather revoke two permisions it just revoke the one passed to it. i.e it turns it off(-).

Let's see an example:

- __Given a file : - rw- rw- r--, let turn the read permission for the others user off. i.e let revoke it__

     chmod o-r file_name
The result : - rw- rw- ---. note only the r is changed.


## Change File Ownership
File owner can be change for the different users, the command for each class of user are listed below:

* chown : this command is use to change the ownership of user and group user for any file. It has to be use with the su or sudo command to grant superuser priviledges.It will request for the root password.

Usage : 
    sudo chown [option] [owner] [:[group]] File
    sudo chown new_owner file_name

    sudo chown :new_group file_name
the above will only change the group ownership and still maintain the user owner.

    sudo chown new_owner:new_group_owner file_name
This change both the owner and the group and assign it to those specify.

    sudo chown : file_name
Both ownership remain unchange


feel free to explore more usage of chown command in the link below:
[chown](https://linuxhint.com/linux_file_permissions/)

* chgrp

usage : chgrp new_group_owner file_name
*
