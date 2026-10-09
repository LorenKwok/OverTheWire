# Bandit Level 11 -> Level 12 #

## Level Goal ## 
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

## Details ##
Slightly tricky level. We'll need to learn how to decipher a ROT13 cipher which moves letters in an alphabet by several places to obfuscate the original text.

## Commands ##
```cat```

```tr '[original alphabet range]' '[rotated alphabet range]'```

## Solution ##
First we need to ```cat``` the ```data.txt``` again. Afterwards, we'd pipe to use that output on the next command.

To rotate ROT13, we'd need to use the ```tr``` command to translate N-Z back to A-M and n-z back to a-m. If you count manually, N is 13 rotations away from A and so is Z from M. After entering ```tr```, you would enter ```A-Za-z``` to specify the range that we are working with which is both upper and lower case of the entire alphabet. Finally, we'd enter ```'N-ZA-Mn-za-m'``` which converts N-Z back to A-M and n-z back to a-m.

Altogether, it would look like:
    cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'

Then we will find the password from there.