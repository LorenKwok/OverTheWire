# Bandit Level 20 -> Level 21 #

## Level Goal ## 
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

NOTE: Try connecting to your own network daemon to see if it works as you think

## Details ##
One of the trickier levels. In this level, we learn to use ```nc``` to create a listener and we will also use a setuid binary, like the last level, to run an executable that reads a line of text and passes the password to bandit21 if the text correctly matches the password to the current level.

## Commands ##
```tmux``` Command to open multiple windows in one terminal

```nc -l``` Command to create a listener

## Solution ##
This level requires you to either have two terminals open or run ```tmux```. We'll be using ```tmux``` as an opportunity to learn the command.

```tmux``` is a command that allows you to create a new window in the same terminal. It will be useful as we will need to use one window that will be in charge of the listener while the other window will run the setuid binary file.

First, run ```tmux``` then split the windows either vertically, with ```CTRL+B and %``` or horizontally ```CTRL+B and "```. Make sure that whenever you use a tmux control, to always click CTRL+B then release afterwards before entering the next input. You can easily switch between different windows by using ```CTRL+B``` with the arrow keys on your keyboard.

We will log into bandit20 on both windows. Aftewards, let's set up the listener first on one of the windows. We'll need to use a port that isn't already in use. In this case, I used port 1333:
    nc -l localhost 1333

Once we do that, it'll be listening until it receives an input from the other side. Now on the other window, we will need to execute the setuid binary file called ```suconnect``` like in the previous level, followed by the port number we specified earlier: ```1333```.
    ./suconnect 1333

Now, both sides are connected and suconnect is waiting for an input from the listener. On the listener, we can input the password of the current level. Once that's done, suconnect will indicate that 'Password matches, sending next password', and we will receive the password for bandit21 on the listener.