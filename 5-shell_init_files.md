# SHELL INITIALIZATION FILES

A shell initilization file is a shell script which everytime the shell get to execute command. This files set up the work environment and allow the customization of the shell environment for the user.

The goal of shell initilization files are  for persistence behaviour of the shell configuration.

## Types of Shell Initialization files
- System- wide startup files

- User- specific startup files

### System- Wide Startup Files : 
The init files contain configurations that is global to the whole system.All users can share the same configuration.

#### Examples of System wide Startup Files
* /etc/profile file - contains linux system wide environment and other startup script. This file only run for login shell and not when script are executed. It stores configuration for login setup. The PATH variable, user limit are usually define in this file.

[link](https://eng.libretexts.org/Bookshelves/Computer_Science/Operating_Systems/Linux_-_The_Penguin_Marches_On_(McClanahan)/02%3A_User_Group_Administration/5.03%3A_System_Wide_User_Profiles/5.03.1%3A_System_Wide_User_Profiles%3A_etc-profile#:~:text=etc%2Fprofile%20File-,The%20%2Fetc%2Fprofile%20File,%2C%20ksh%2C%20or%20sh%20shells.)

