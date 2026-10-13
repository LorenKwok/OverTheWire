# Bandit Level 18 -> Level 19 #

## Level Goal ## 
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

## Details ##
In this level, we'll need to learn how to SSH then run a command immediately afterwards as the host will boot us out.

## Commands ##
```ssh```

```cat```

## Solution ##
This level can be simple if you make it to be. We'd have to ```ssh``` into bandit18 then immediately ```cat``` into the ```readme``` file. To do so, we'd wrap the ```cat``` in quotation marks like so:
    
    ssh -p 2220 bandit18@bandit.labs.overthewire.org 'cat readme'

This will give us the password.