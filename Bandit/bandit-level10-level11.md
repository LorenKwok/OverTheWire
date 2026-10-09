# Bandit Level 10 -> Level 11 #

## Level Goal ## 
The password for the next level is stored in the file data.txt, which contains base64 encoded data

## Details ##
In this level, we will learn how to use Base64 decoding. Base64 is a format by which binary data can be converted to text. Common usage of Base64 is embedding images in HTML/CSS or encoding files through email.

## Commands ##
```cat```

```base64```

## Solution ##
This level's quite simple since it's meant to let you test the ```base64``` command. Simply, ```cat``` the ```data.txt``` file then pipe it with ```base64 -d``` which is the command to decode the base64 text.

Altogether it would look like this:
    cat data.txt | base64-d

There's our password.