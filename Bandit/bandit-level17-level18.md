# Bandit Level 17 -> Level 18 #

## Level Goal ## 
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19

## Details ##
Very simple level, but that's because it's a precursor for the next level.

## Commands ##
```diff``` Command to compare lines between two files.

## Solution ##
Simply use the ```diff [file 1] [file2]``` command and it will print the differences between the two files. The output will also have arrows that point to each file along with each difference.

Simply use the new password to access bandit18. The host will kick us out with a 'Byebye!' message but that's supposed to happen. We'll have to refer to this for bandit18 -> 19.