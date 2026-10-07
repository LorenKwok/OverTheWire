# Bandit Level 2 -> Level 3 #

## Level Goal ##

    The password for the next level is stored in a file called --spaces in this filename-- located in the home directory

## Details ##
In this level, we'll learn how to print a file with spaces in its name.

## Commands ##
```ls```

```cat```

```./ [file name]```

```\ [Space]``` If there is a space, you may utilize backslash followed by a space to signify that there is a space. Simply typing the space would not work.

## Solution ##
Same as the previous level, you would ```ls``` to identify the files in the current directory. In this case, there is a single file called ```--spaces in this filename--```. In this case, there are spaces in the filename that you would need to resolve in order for ```cat``` to properly print the contents of the file.

We learned in the previous level to use ```./``` to specify the direct path since the file name starts with ```-```. With spaces in the file name, you will need to utilize a backslash, ```\```, followed by a space. Altogether, it will look like this:

    cat ./--spaces\ in\ this\ filename--

Afterwards, you will get the password. 