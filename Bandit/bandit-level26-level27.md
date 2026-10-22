# Bandit Level 26 -> Level 27 #

## Level Goal ## 
Good job getting a shell! Now hurry and grab the password for bandit27!

## Details ##
Luckily this level is very easy after completing the previous one.

## Commands ##
```ls```

## Solution ##
Take a look at the contents of the directory using ```ls``` and you'll find a bandit27-do setuid binary file.

If you remember from one of the previous levels, setuid gives you elevated permissions.

Execute this file along with opening the password folder for bandit27:
   
    ./bandit27-do cat /etc/bandit_pass/bandit27

You'll find the password to the next level.