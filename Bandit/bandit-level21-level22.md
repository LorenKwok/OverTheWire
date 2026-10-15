# Bandit Level 21 -> Level 22 #

## Level Goal ## 
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

## Details ##
This is a simple level to demonstrate how a cron job works.

## Commands ##
```cd```

```cat```

## Solution ##
A cron job is a file that executes tasks at predefined times like a script. We'll be looking at a cron file in this level here.

Simply ```cd``` into ```/etc/cron.d/``` then take a look at the files inside. You will find a file named ```cronjob_bandit22```. If you cat into the file, you'll see that it points towards a .sh (shell script) file: ```/usr/bin/cronjob_bandit22.sh```.

*If you're interested in the structure of the cron job, the five asterisks represent the minute, hour, day of month, month, and day of week. The asterisk is a wildcard which means that it is constantly running. The output is going into /dev/null as to dispose of all notifiers that this cron job is occuring, which can create a lot of noise. The @reboot simply means that the cron job will run once the system starts up.*

Let's ```cat``` into the file to see what it does. So it does two things:

-It does ```chmod``` to give read and write permissions for the owner, but read permissions for the groups and others.

-It also prints the password located in ```/etc/bandit_pass/bandit22``` into a temporary directory.

Simply ```cat``` the file in the temporary directory and you will get the password to the next level.