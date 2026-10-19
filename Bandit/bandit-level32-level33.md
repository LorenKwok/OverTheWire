# Bandit Level 32 -> Level 33 #

## Level Goal ## 
After all this git stuff, it’s time for another escape. Good luck!

## Details ##
Our final level at the time of me writing this. Have fun with it.

## Commands ##

## Solution ##
As our final level, it isn't an easy one to immediately understand.

When we enter bandit32, we'll notice that we're greeted by a message stating that we are in the UPPERCASE SHELL. Every command will be entered in upper case, which means we cannot use our standard commands here.

However, symbols and numbers will still function as normal, so we'll find a way to use that.

OverTheWire points towards the commands ```sh``` and ```man```. So if you were to solve the level yourself, you'd start looking into ```sh``` to find any commands that would fit this situation. The answer, however, is very simple. The command we are looking here is ```$0```, which is a shortcut that points towards the current shell process. Think of this command as initializing your shell again.

After we input ```$0```, the terminal will launch the ```sh``` shell, which would then allow us to enter commands as normal. If you ```ls``` the current directory, you'll notice that there is an ```uppershell``` file. If we use ```file```, we can see that it is a setuid file. If we use ```ls -la```, it takes the permissions from the owner, bandit33. If we activate this file, it'll take us right back to the UPPERCASE SHELL, which means that the setuid file is the one that is putting us there on startup. This also means that from the get-go, we have bandit33 permissions. If you use ```$0``` to go back to the ```sh``` shell again then enter the ```whoami``` command, you'll see that we're already bandit33.

Go ahead and ```cat /etc/bandit_pass/bandit33``` to get the password.

As of the time of this writing, this is the final level in this series. If you may go ahead and enter bandit33 to find a ```README.md``` that will congratulate you for completing this series.

Thank you for following me throughout this entire series.

-LK