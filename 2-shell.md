# Understanding File Permission terms and Commands

__What do the Commands : chmod, sudo, su, chown, chgrp__

* Chmod : This commands give the ability to alter file permission, by either using the octal notation or the symbolic mode.

* sudo : grant superuser privileges alleast temporarily to perform so administrative task, howerver it will require password to acess the root. It gives you the power of being a root user.
The sudo command runs any command as another user account. it is use to use to elevate permission(root user)

* su : substute user- also grant administrative privildeges. when use without the -i argunmet allow you to acces the root. 

* chgrp : This change the group ownership a file

__How to represent each of the three sets of permission(owner, group, and other) as a single digit.__

The can be represented either using octal notation and symbolic mode

* using the octal representation, you use 1 to note a state and 0 means ni permission : thus rwx rwx r-- : 111 111 100 :774

 __How to change user ID or become superuser__
 * To become a superuser, : to switch to the root user: 
 sudo su
 or just do
 su
 it will ask for root password.

 * To change to another user : use the su command follow by the new-user/user.
 You can create a new user using the useradd command.

 su ted

 to login as ted and adopt the environment do : su - ted
 this time you will be place in the home directory for ted.
 [su](https://www.lifewire.com/switch-user-su-command-3887179#:~:text=To%20switch%20to%20the%20root,example%2C%20su%20%2D%20ted).)
 

 __HOw to Create a User__
 useradd test

 T0 set user passwd use : passwd test, to switch use su - test
