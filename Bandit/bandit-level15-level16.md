# Bandit Level 15 -> Level 16 #

## Level Goal ## 
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.

Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.

## Details ##
This one is also a simple level which teaches you how to conduct a SSL/TLS connection.

## Commands ##
```openssl s_client -connect [hostname]:[port number]``` Command for connecting to a remote host via SSL/TLS by specifying a host name and port number

## Solution ##
OpenSSL is an open-source library that allows the user to conduct a Secure Sockets Layer (SSL) and Transport Layer Security (TLS) encrypted connection to a remote host. Using SSL/TLS adds a layer of security with its cryptographic PKI system.

For this level, we need to connect to local host from 30001 port using SSL TLS. As such, we would need to use the following command:
    
    openssl s_client -connect localhost:30001

Once the connection has been made, like the last level, we'd simply have to enter the password for bandit15 and it will return the password for bandit16 to us.