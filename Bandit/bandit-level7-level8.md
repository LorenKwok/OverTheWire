# Bandit Level 7 -> Level 8 #

## Level Goal ## 
The password for the next level is stored in the file data.txt next to the word millionth.

## Details ##
For this level, we're going to learn something new, which is extrapolating specific text from a file. Remember to refer to the man files if you are stuck about certain commands by entering ```man [command]```.

## Commands ##
```ls```

```grep [text] [file namegrep ]``` Command used to search for a specific string along with its associated line

## Solution ##
The level is meant to introduce us to the ```grep``` command. As such, this will be a simple one. We are trying to find the text ```millionth``` from the file called ```data.txt```. We will only need to input the following command to arrive at our answer:

    grep millionth data.txt