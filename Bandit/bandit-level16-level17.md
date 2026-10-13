# Bandit Level 16 -> Level 17 #

## Level Goal ## 
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL/TLS and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.

## Details ##
In this level, we'll learn to scan a host for open ports as well as the nature of each port using ```nmap```. Afterwards, we use the same method to conduct a SSL/TLS connection but with a twist.

## Commands ##
```nmap -sV``` nmap is a command to scan for open ports. -sV is an option to conduct a service and version number search to determine the specifics of the open ports.

```openssl s_client```

```nano``` Command used to launch Bash's shell editor.

## Solution ##
First, we need to use ```nmap``` scan local host in the range of 31000 to 32000 for any open ports. We'll use the following command:
    
    nmap localhost -p 31000-32000

This way, we can first determine the open ports before conducting a longer, more rigorous scan, using ```-sV```.

We'll notice that there are five ports open, 31046, 31518, 3191, 31790, and 31960; however, we haven't ascertained which ones can communicate through SSL/TLS yet. That's where the ```-sV``` option comes in:
    
    nmap -sV localhost -p 31046,31518,31691,31790,31960

The scan might take several minutes but we'll eventually run into the full list of open ports as well as their services. It'll look like this:

![alt text](screenshots/image-3.png)

*echo* just refers to testing ports that will send any traffic back towards you, so we are not concerned with those. In this case, port 31790 has a ```ssl/unknown``` service, which is highly likely to be what we are looking for.

Just like in the previous level, we will run a SSL/TLS encrypted connection to localhost through this port we just found:
   
    openssl s_client -connect localhost:31790

However, when we enter the password, we'll run into a 'KEYUPDATE' message. Based on the openssl man page under 'CONNECTED COMMANDS', this is message occurs when any of the letters, Q, R, k, or K are at the start of the line because they are reserved for commands. To prevent this from happening, we'd need to enter an additional option, ```-option```, which bypasses the command structure:
   
    openssl s_client -connect localhost:31790 -quiet

Now, when we enter the password, it'll tell us that we have the correct password and pass us a private SSH key. If you remember from a previous OverTheWire level, we would use the private SSH key to SSH into the next level. Let's go ahead and copy the contents of this SSH key including ```-----BEGIN OPENSSH PRIVATE KEY-----``` at the start and ```-----END OPENSSH PRIVATE KEY-----``` at the end. 

Once we have that copied, we can easily create a new file using the ```nano [file name]``` command. We'd simply paste the contents of the SSH private key into the box then click exit. When prompted to save the file, we'd keep clicking enter until the file has been saved correctly with the file name of your desire.

Finally, we can SSH into bandit17 using the key. If you forgot the command, here it is:
    
    ssh -p 2220 -i bandit17.key bandit17@bandit.labs.overthewire.org