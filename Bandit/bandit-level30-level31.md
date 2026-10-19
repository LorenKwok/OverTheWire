# Bandit Level 30 -> Level 31 #

## Level Goal ## 
There is a git repository at ssh://bandit30-git@bandit.labs.overthewire.org/home/bandit30-git/repo via the port 2220. The password for the user bandit30-git is the same as for the user bandit30.

From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.

## Details ##
Luckily a very easily level. We'll do the same thing as the previous level to get our answer.

## Commands ##
```git```

```cd```

```cat```

```ls```

```git show```

## Solution ##

Same process as the previous levels. ```README.md``` will obviously not have the password.

Once we're in ```.git```, we'll go back to ```packed-refs``` again. Simply ```git show``` the two hashes and one of the branches will give us the password to the next level.