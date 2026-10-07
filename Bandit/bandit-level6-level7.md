# Bandit Level 6 -> Level 7 #

## Level Goal ##

The password for the next level is stored somewhere on the server and has all of the following properties:


owned by user bandit7

owned by group bandit6

33 bytes in size

## Details ##

More ```find``` command usage here.

## Commands ##
```find```
```cat```

## Solution ##
Similar to the last level, we need to use ```find``` followed by the correct commands to filter the right file by parameter.

In this case, we are searching for the entire server so we would need to lead with ```/``` after typing ```find```. If we were to look at the current directory, we would be using ```.``` instead.

To find the files owned by user ```bandit7```, we would use ```find``` followed by ```-user [username]```.

To find the files owned by the group ```bandit6```, we would use ```group [groupname]```

Finally, as per the previous level, we would find 33 byte files through ```-size [numerical value]c```.

Altogether, it would be 
    find / -user bandit7 -group bandit6 -size 33c

However, upon entering this command, you will notice there is a bunch of files with the "Permission denied" message next to them. We would need to filter these out and find the only directory where we have permission.

In this case, we would add ```2>/dev/null``` to the command, which discards all errors. ```2``` refers to the standard error. ```0``` refers to standard input, ```1``` refers to standard output, and ```2``` refers to the standard error. ```/dev/null``` command specifies to discard all files that match the parameter (2 or standard error). Altogether, this means to discard all standard errors into /dev/null.

We would input
    find / -user bandit7 -group bandit6 -size 33c 2>/dev/null

We would then find only one file which will give us the password.