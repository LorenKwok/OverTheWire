# Bandit Level 8 -> Level 9 #

## Level Goal ## 
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

## Details ##
For this level, we will learn how to use ```sort``` and ```uniq``` to arrive at our answer.

## Commands ##
```sort``` Command to sort files. If there are duplicate files then they are organized together.

```[Command 1] | [Command 2]``` Command in Linux Bash that allows you to pipe. Piping basically turns the output of the first command (left side of the pipe) into the input of the second command (right side of the pipe)

```uniq``` Allows you to filter by unique lines, repeated lines, or lines based on count.

## Solution ##
For this level, the ```data.txt``` file contains a bunch of lines that are disorganized, stopping us from printing the unique line using the ```uniq``` command. In this case, we would simply use the ```sort``` command to place each duplicate lines next to each other first.

    sort data.txt

However, we want to sort ```data.txt``` *then* use uniq to extrapolate the only unique line. If we were to use ```sort``` and ```uniq``` separately then we cannot accomplish this since we need to keep the persistent output of ```sort``` and use that as input for ```uniq``` afterwards. We would accomplish by using a technique called **piping** in Bash, denoted by the command ```|```. We would then use ```uniq -u``` which specifies unique lines.

Altogether, the command would look like:
    
    sort data.txt | uniq -u

There's our password.