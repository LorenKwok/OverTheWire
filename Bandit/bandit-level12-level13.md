# Bandit Level 12 -> Level 13 #

## Level Goal ## 
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Details ##

## Commands ##

```mkdir``` Command to make a new directory

```cp``` Command to copy a file to a destination

```xxd -r``` Command to reverse a ```xxd``` command which converts a file into a hex dump

```gzip -d``` Command to decompress a gzip file

```bzip2 -d``` Command to decompress a gzip file

```tar -xvf``` Command to extract a tar file. x stands for extract. v stands for verbose. f stands for file.

```file```

```mv``` Command to change file name

## Solution ##

This is a tricky level. You are recommended to create a new temporary folder inside ```/tmp/``` as you will constantly be making new files. Let's go ahead and ```cd /tmp/``` then use ```mkdir [new directory name]``` to make the new directory. We will be working off of this directory so let's run the command ```cp /home/bandit12/data.txt /tmp/[name of temporary directory]/ to copy the text file to your temporary directory.

When you run ```cat``` with the file, you will notice that it is a hex dump file, which means that you will need to run ```xxd -r data.txt``` to reverse the hex dump. Every time you reverse a compression from here on, it will create a new file for you without the extension. You must use ```file``` to determine what kind of file it has been converted into each time. In this case, it has been converted into a gzip file. As such, it would need to be renamed to a file name with the appropriate extension, which is ```.gz``` in this case.

After renaming it to [name of file].gz, you must run ```gzip -d [name of file]``` to decompress it. In this level, the file will constantly be in a compressed file type between the following: ```gzip```, ```bzip2```, and ```tar```. I won't write out the entire sequence here. But, each time you decompress the file, make sure to run the ```file``` then use the appropriate decompression method: 

-```gzip -d``` 

-```bzip2 -d```

-```tar -xvf``` 

Each time, you need to make sure to use ```mv``` to rename the file to the correct extension:

-```.gz``` for gzip files

-```.bz2``` for bzip files

-```.tar``` for tar files

Also, make sure to ```cat``` each time as you will eventually have to check if the password is there.

Once you go through enough cycles of decompressions (and there's quite a lot), the contents will eventually show 'The password is _________'
