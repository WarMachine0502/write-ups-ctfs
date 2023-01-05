# Bandit
The Bandit cyber-security challenge is aimed at absolute beginners and is offered by the [OverTheWire](https://overthewire.org/wargames/) community. It introduces players to basic hacking techniques and is highly popular amongst novices and enthusiasts as an easy tool to get acquainted with cyber-security terms and syntax.

---
<br/>

> host : bandit.labs.overthewire.org  
> port : 2220  

The platform needs us to connect to the host using SSH, hence we run the following command.

```
ssh bandit<level_number>@bandit.labs.overthewire.org -p 2220
```

---

## Level 0

This level marks the beginning of the Bandit wargame.  

> username : bandit0  
> password : bandit0


We use SSH to connect to the host.

![alt](https://lh4.googleusercontent.com/uhLTb1_L6z0gPBMARl-vzKJyH7DXFQjKBpJksg7VyounmgXYSnMUXMs4l5vF4P8qOsI=w2400)

Upon connection, the host asks us for a password which has already been provided above. Entering  ``bandit0`` connects us to the machine.


First, we run ``ls`` to get a hold of the machine and its files, which only shows us a ``readme`` file on the server. We can then run ``cat readme`` to get the flag.

>> flag : NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

![alt](https://lh4.googleusercontent.com/d1-JTEIZNUAiZN7QoUNmM3QvfPMh30AWoeqdhX67LhsUZtmZu7GHmGqbHPn5reZqtZU=w2400)

---

## Level 1

> username : bandit1  
> password : NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

Using above credentials, we successfully connect to the system. Then we discover a file simply named ``-`` on the server. For files having special characters in their names, we use ``./`` to reference them in bash. Hence, we run ``cat ./-`` to see the file's contents and get the flag.

>> flag : rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

![alt](https://lh3.googleusercontent.com/wgwxlI5yIxCZ418IBXrEvpBaoNtzCcMfHKwnL9MTSBq089ktXaPMNV96mxC0KHxdHjA=w2400)

---

## Level 2

> username : bandit2  
> password : rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

This time, we discover a file named ``spaces in this filename`` on the server. For files having spaces in their names, we use ``""`` to reference the name together in bash. Hence, we run ``"spaces in this filename"`` to see the file's contents and get the flag.

>> flag : aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

![alt](https://lh4.googleusercontent.com/gVN8ZBJUxso3vjLJndC-9yorG1xdyZnkJePEhThS7zBIdo8PN_M-FhgKHra7pA-UYWI=w2400)

---

## Level 3

> username : bandit3  
> password : aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

This level's a bit tricky. We encounter a folder on the server, which doesn't seem to contain any file. However, as hinted in the [docs](https://overthewire.org/wargames/bandit/bandit4.html), the flag is stored in a hidden file. Hence, we run the command ``cat .hidden`` to view hidden contents in the folder.

>> flag : 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

![alt](https://lh6.googleusercontent.com/e6yrzm62p3qaRTfv81noQQdvIU9AJeOMC0BVwkAYZFZX2imAtYGu7fshtRgGko5ZqUo=w2400)

---

## Level 4

> username : bandit4  
> password : 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

Inside the folder ``inhere``, we encounter a number of files, some of which do not have human-readable text. To find the ASCII encoded file, we use ``find`` and ``type`` commands simultaneously as ``find . -type f | xargs file``. This yields ``-file07`` as the only file with ASCII encoding and a ``-`` in the name, hence we run ``cat ./-file07`` to get the flag.

>> flag : lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

![alt](https://lh3.googleusercontent.com/cWPkYq4rgV1rvwBUH67RKVlPOKXJhMEX5W185asE9Iqp2PpAFIzP4YtpH9lt5uurnIQ=w2400)