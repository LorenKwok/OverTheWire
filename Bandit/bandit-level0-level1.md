# Bandit Level 0 -> Level 1 #

## Details ##
    The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.
As per Level 0, we are now connected to bandit.labs.overthewire.org as the user bandit0.

## Commands ##
```pwd``` Command for seeing the absolute path to the current directory.

```ls``` Command for seeing the files in the current directory.

```cat [file name]``` Command to print contents of a file.

## Solution ##
First we need to learn the current directory using ```pwd```. Once you use the command, you will notice that we are in the ```/home/bandit0``` directory.

Next, we need to look at the files inside this directory using ```ls```. You will notice that there is only one ```readme``` file.

Let's use ```cat``` to print the ```readme``` file. Once that's done, you will find the password inside to the next level.