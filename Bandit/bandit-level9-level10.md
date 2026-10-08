# Bandit Level 9 -> Level 10 #

## Level Goal ## 
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

## Details ##
In this level, we will primarily learn the ```strings``` command which gives us **printable** characters in files and excludes lines that are binary or non-text.

## Commands ##
```strings``` Command to print out human readable, printable text, excluding binary or non-text lines.

```|```

```grep```

## Solution ##
It's a good habit to go through each command in the OverTheWire website for the level to figure out which commands are appropriate to use. We'll notice that there is a new ```strings``` command, which shows human-readable text in a file. As such, we would ```strings``` for ```data.txt``` then pipe a ```grep``` command to look for any lines with ```=``` in it.

    strings data.txt | grep "="

You may immediately see the password there, which matches the patterns for the other passwords thus far.

However, if we were to improve on this, we could have optimized the commands to better filter the noise. The level advises us that the password is *preceded by several '=' characters*. To accomplish this, we would use the ```^``` symbol before ```=``` to signify the starting character. Afterwards, we could add an additional ```=``` because the level did mention that there is more than one in the line.

Altogether:
    strings data.txt | grep "^=="