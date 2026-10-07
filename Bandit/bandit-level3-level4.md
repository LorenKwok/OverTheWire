# Bandit Level 3 -> Level 4 #

## Details ##
    The password for the next level is stored in a hidden file in the inhere directory.
Using commands learned in the previous levels, we can access the directory known as ```inhere```.

## Commands ##
```ls -a`` To see all files in the directory including hidden ones
```cd [Directory Name]```
```cat```

## Solution ##
This level is quite simple. If you use ```ls``` in the starting directory, you'll find the directory known as ```inhere```. Let's change to this directory with the ```cd``` command.
    cd inhere
Afterwards, if you just use ```ls```, you'll notice that there aren't any files. That's because the file we're trying to look for is hidden. Instead, we will use ```ls -a```. You will find a hidden file known as ...Hiding-From-You. Files in Bash are signified by a ```.``` before the file name. 

Now, let's use the ```cat``` command to open up this hidden file.
    cat ./...Hiding-From-You
You will find the password inside.