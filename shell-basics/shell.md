# Understanding Linux Commands, Concepts and key terminologies

## Concepts and Understanding

### What is "The Shell"
OKay ... well a quick response to what a shell is, will be a program that the terminal sends user input to. The shell generates output and passes it back to the terminal for display.

...But wait what is the "Terminal"- I guess we use a big word there.

### What is Terminal
The word "Terminal" comes from terminate, meaning it is the terminating end of a communication process. The terminal is refer to as been dump since it is just a text based input and output enivronment. It just take text input and display text output. It is the window through which we will type shell commands.It is a program that opens a window and lets us interact with shell. 

This now make more sense, the real work or the heavy lifting is done by the shell, hence the shell will be a program that takes command from the terminal inputed through the keyboard and gives them to the operating system perform.

Moreso the shell can be refers to as a linux command interpreter. Meaning that it is computer program that presents a command line interface which allows you to control your computer using commands entered via the keyboard.

It is a program which exposes an operating system services to a human user or other program.

### More on shell, various types and terminal as well as their types.
The following link will cone in handy..so check it out...
* [shell-basics](http://linuxcommand.org/lc3_lts0010.php)
* [shell-basics-1](https://datacarpentry.org/shell-genomics/01-introduction/)
* [my_favorite](https://www.hanselman.com/blog/whats-the-difference-between-a-console-a-terminal-and-a-shell)
[This_is_so_nice](https://www.geeksforgeeks.org/difference-between-terminal-console-shell-and-command-line/)


## Exploring Some Important Shortcuts via The Keyboard For Bash
Below is a good  resource:
[keyboard-shortcut](https://www.howtogeek.com/howto/ubuntu/keyboard-shortcuts-for-bash-command-shell-for-ubuntu-debian-suse-redhat-linux-etc/)

## What is Shebang in Linux Shell Scripting
...well, if you have seen a shell script before you may be wondering what is the first line is. It started with "#!" character. This character plays a major role in how the shell script is executed.

so let's understand what it meant'
...okay- here it is again : #!/bin/bash - don't fret.It will be clear soon.

The shebang is the combination of the pound key(#) and the exclamanation mark(!). This is character combination has a special meaning when it appears in the very first line of a shell script.

It is an interpreter directive- i.e it specify the interpreter with which the given script will be run by default.

There are several shells available for linux and unix system. they have some comon syntax but  they do have different syntax or different way of getting things done, hence it is important to specify the correct shell interpreter in the script inorder to get the desired result.

When you use  the shebang in the first line of a script. you are telling the shell to run the given script with the specified command. you are specifying the shell interpreter
