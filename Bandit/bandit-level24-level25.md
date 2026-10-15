# Bandit Level 24 -> Level 25 #

## Level Goal ## 
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.
You do not need to create new connections each time

## Details ##
Challenging level that I personally learned a LOT from. In this level, we will have to create a simple script to iterate a number range of 0000-9999 to pass into the listener on port 30002.

## Commands ##
```for``` Starting a for loop

```do``` Indicating a process

```echo```

```nc```

## Solution ##
I've racked my brain trying several methods from trying to nmap to find the name of the daemon, SSHing to port 30002, running a script as well as trying all sorts of commands to try to get the brute force automation to work.

There's no need to nmap as you don't need to know the name of the daemon or anything. All you need to be concerned with is the localhost and port 30002. SSH doesn't work since the listener doesn't speak SSH. OverTheWire does not allow scripts to run here.

What we'll do is write the commands on a textfile in our desktop for ease of use then run it on the user (bandit24) itself.

So let's break down the logic to make it easier for you to understand:

We'll first need to connect to localhost on port 30002 since all OverTheWire stuff is done on the same host anyway. Since SSH doesn't work, we could use both telnet or nc. Pick your poison. For this level, I used nc:

    nc localhost 30002

Afterwards, we need to create a for loop that can pass the numbers ranging from 0000-9999 to the listener. Another challenge is entering the password for bandit24 first.

To start the for loop, we'd need to do ```for i in {0000..9999}```. This creates an iterative statement with the range denoted by the curly brackets {}. Other brackets won't work for ranges in Linux unlike () which works in Python. A range in Linux would also need to be indicated by ```..```. For each line, we'd need to separate them with a semicolon, ```;```.

Next line, we need to instruct the for loop to run a process. We will add ```do``` then make it ```echo``` the password then the number in the range.

    do echo "[password] $i"

Finally we need to create a new line to end the process with ```done```.

The loop, which includes the ```echo```, would need to start first then we would pipe the ```nc localhost 30002```. Altogether, it would look like:

    for i in {0..9999}; do echo "[bandit24 password] $i"; done | nc localhost 3002

It'll spew out each password attempt before finally reaching the correct password to bandit25.