# Bandit Level 27 -> Level 28 #

## Level Goal ## 
There is a git repository at ssh://bandit27-git@bandit.labs.overthewire.org/home/bandit27-git/repo via the port 2220. The password for the user bandit27-git is the same as for the user bandit27.

From your local machine (not the OverTheWire machine!), clone the repository and find the password for the next level. This needs git installed locally on your machine.

## Details ##
In this level, we'll learn to use Git to clone repository through SSH and a specified port.

## Commands ##
```git``` Command to interact with Git.

```ls```

```cat```

## Solution ##
We'll need to be in our local device (not bandit27).

Download Git first if you don't have it already. It will vary depending on the operating system you're using. For Ubuntu, which I am using, I ran the following command:

    sudo apt install git-all

Once that's done, to clone a Git through a specified port, we have to run a command that follows this structure:
    
    git clone [URL]:[port number][path]

In the level goal, they combined the entire URL and directory path to make it a bit trickier. Altogether, it will look like:

    git clone ssh://bandit7-git@bandit.labs.overthewire.org:2220/home/bandit7-git/repo

If it works, you'll find a directory named `repo` in your current directory. Go inside, and use ```cat``` for the ```README``` file inside to find the password.