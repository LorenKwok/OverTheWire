# Bandit Level 5 -> Level 6 #

## Level Goal ##
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

human-readable

1033 bytes in size

not executable

## Details ##
In this level, we will learn to use the ```find``` command to filter files to find the one we want.

## Commands ##
```ls```

```cd```

```find``` Command used to filter files

```cat```

## Solution ##
In the ```inhere``` directory, we will find many subsequent directories. As we would absolutely not look through each file manually here, we need to use the ```find``` command to filter to the file that we are looking for. To repeat we are looking for the file with these parameters: *human-readable, 1033 bytes in size, not executable*

Let's use ```find```. 

As per the previous level, human-readable files are ASCII text files. We'll figure out which files are ASCII text later.

To find files with a specific file size, we need to add ```-size``` followed by ```[size of file]c```. ```c``` stands for bytes. 

Finally, to filter by executable, we would simply type ```-executable```. However, in this case we are trying to find a file that is *not executable*. As such, we would use ```! -executable```

Altogether we would use the following command:
    -find -size 1033c ! -executable

Luckily, there is only one file that showed up with these parameters. 

*For learning sake, let's say it wasn't just one file, and it was two. You would have to use ```file``` followed by the directories for each file (you can enter multiple directories in the same command). You would then determine which ones are ASCII text*

Once you ```cat``` the only directory, you will get your password to the next level.