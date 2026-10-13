# Bandit Level 19 -> Level 20 #

## Level Goal ## 
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

## Details ##
Setuid is a file that grants a user or group temporary permissions to run a command that they otherwise would not have access to. We'll be using this to get the password within ```/etc/bandit_pass```

## Commands ##
```cat```

## Solution ##
If we look into the main directory, there is a file called ```bandit20-do```. This is the setuid binary file which we will use to execute a ```cat``` command on ```/etc/bandit_pass/bandit20``` where the password to bandit20 is stored. To execute a file, we'd simply add the prefix ```./[file name]```. By combining the execution of ```bandit20-do``` and ```cat```, we will get the password to the next level like so:
    
    ./bandit20-do cat /etc/bandit_pass/bandit20

