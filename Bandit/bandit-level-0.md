# Bandit Level 0 #

## Level Goal ##

The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.

## Details ##
The start of many beginnings. In this first level, you will learn to connect to OverTheWire's machine through SSH using port 2220. The host name is **bandit.labs.overthewire.org** while the user name and password are bandit0.  To solve this level, we will need to know how to do use various Linux commands as shown below.

## Commands ##
```ssh``` to initiate the SSH process

```-p [port number]``` to connect to a specific port

```[username]@[domain name]``` to indicate the host and user we are connecting as

## Solution ##
Altogether it will look like:
    ssh -p 2220 bandit0@bandit.labs.overthewire.org

After you enter the correct command, you will receive a password prompt. In bash, the password is hidden so it would seem like nothing is being typed, but trust that it's there. Enter the password to move onto the next level.