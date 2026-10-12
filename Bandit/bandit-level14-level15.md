# Bandit Level 14 -> Level 15 #

## Level Goal ## 
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

## Details ##
Thankfully a simpler level to make up for the last level. Here, we learn how to use telnet to remotely communicate with another host. Telnet is different from SSH in that it is an older protocol and does not encrypt the data that it sends, making it less secure. Telnet allows one to remotely log in to a host, but we will not be doing that this level.

## Commands ##
```ssh```

```telnet [host] [port number]``` Command to run telnet to connect to a host through a specified port

## Solution ##

As instructed in the previous level, we'd need to retrieve the password from /etc/bandit_pass/bandit14, bandit14 being a file.

    cat /etc/bandit_pass/bandit14

Let's take this password and submit it to ```localhost``` through ```telnet port 30000``` using the following command.

    telnet localhost 30000

Afterwards, we'd see a blinking block which specifies that it is asking for the password. Once we enter the password, we'll be met with 'Correct!' followed by the password for bandit15.

