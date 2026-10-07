# Bandit Level 4 -> Level 5 #

## Level Goal ##

The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

## Details ##
In this level, the directory contains several files which are not human-readable. We will learn to determine which files are human-readable using the ```file``` command.

## Commands ##
```ls```

```cd```

```file``` Command used to determine the type of file

```cat```

## Solution
There's several ways to solve this level. Certainly, you can use ```cat``` on each file and eventually get to your answer. However, the purpose of this level is to teach you how to look at different types of files. If you ```-ls``` the ```inhere``` directory, you will find 10 files inside. 

One way to determine if the file is human-readable is to see the type of file it is. We can use the following command to extrapolate each file type:
    file ./-file0*
We use ```*``` as a wildcard so the command would affect the files between 0 and 9 for the last digit. You will notice that there is a single ASCII text file amongst several data files. ASCII is a human-readable format whereas data files contain incomprehensible content. If we ```cat``` the only ASCII text file then we will arrive at our answer.