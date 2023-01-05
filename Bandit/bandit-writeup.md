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

![screenshot_of_solution](https://lh4.googleusercontent.com/uhLTb1_L6z0gPBMARl-vzKJyH7DXFQjKBpJksg7VyounmgXYSnMUXMs4l5vF4P8qOsI=w2400)

Upon connection, the host asks us for a password which has already been provided above. Entering  ``bandit0`` connects us to the machine.


First, we run ``ls`` to get a hold of the machine and its files, which only shows us a ``readme`` file on the server. We can then run ``cat readme`` to get the flag.

>> flag : NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

![screenshot_of_solution](https://lh4.googleusercontent.com/d1-JTEIZNUAiZN7QoUNmM3QvfPMh30AWoeqdhX67LhsUZtmZu7GHmGqbHPn5reZqtZU=w2400)

---

## Level 1

> username : bandit1  
> password : NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

Using above credentials, we successfully connect to the system. Then we discover a file simply named ``-`` on the server. For files having special characters in their names, we use ``./`` to reference them in bash. Hence, we run ``cat ./-`` to see the file's contents and get the flag.

>> flag : rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

![screenshot_of_solution](https://lh3.googleusercontent.com/wgwxlI5yIxCZ418IBXrEvpBaoNtzCcMfHKwnL9MTSBq089ktXaPMNV96mxC0KHxdHjA=w2400)

---

## Level 2

> username : bandit2  
> password : rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

This time, we discover a file named ``spaces in this filename`` on the server. For files having spaces in their names, we use ``""`` to reference the name together in bash. Hence, we run ``"spaces in this filename"`` to see the file's contents and get the flag.

>> flag : aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

![screenshot_of_solution](https://lh4.googleusercontent.com/gVN8ZBJUxso3vjLJndC-9yorG1xdyZnkJePEhThS7zBIdo8PN_M-FhgKHra7pA-UYWI=w2400)

---

## Level 3

> username : bandit3  
> password : aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

This level's a bit tricky. We encounter a folder on the server, which doesn't seem to contain any file. However, as hinted in the [docs](https://overthewire.org/wargames/bandit/bandit4.html), the flag is stored in a hidden file. Hence, we run the command ``cat .hidden`` to view hidden contents in the folder.

>> flag : 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

![screenshot_of_solution](https://lh6.googleusercontent.com/e6yrzm62p3qaRTfv81noQQdvIU9AJeOMC0BVwkAYZFZX2imAtYGu7fshtRgGko5ZqUo=w2400)

---

## Level 4

> username : bandit4  
> password : 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

Inside the folder ``inhere``, we encounter a number of files, some of which do not have human-readable text. To find the ASCII encoded file, we use ``find`` and ``type`` commands simultaneously as ``find . -type f | xargs file``. This yields ``-file07`` as the only file with ASCII encoding and a ``-`` in the name, hence we run ``cat ./-file07`` to get the flag.

>> flag : lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

![screenshot_of_solution](https://lh3.googleusercontent.com/cWPkYq4rgV1rvwBUH67RKVlPOKXJhMEX5W185asE9Iqp2PpAFIzP4YtpH9lt5uurnIQ=w2400)

---

## Level 5

> username : bandit5  
> password : lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

As hinted by the [docs](https://overthewire.org/wargames/bandit/bandit6.html), the flag is stored in a file which is human-readable(ASCII), 1033 bytes in size and non-executable. Hence we use ``find`` and ``type`` commands simultaneously as ``find . -type f -size 1033c ! -executable`` to find the file in the ``inhere`` directory, following which we get the file's address instantly.

>> flag : P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

![screenshot_of_solution](https://lh6.googleusercontent.com/ZzxmmyFjUuglVAkU52VrdWLAX5aIOA5ENy82byGTdS_tjCV3mmRwhq097MnaFZH1XzM=w2400)

---

## Level 6

> username : bandit6  
> password : P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

Running the `ls` command does not return anything, hence we will need to run a custom `find` command to iterate through all files on the server to get the file we need.
<br />

According to the [docs](https://overthewire.org/wargames/bandit/bandit7.html), we have a file owned by the user bandit7, group bandit6 and is 33 bytes in size. Hence, we run the command ``find / -type f -user bandit7 -group bandit6 -size 33c``, which gives us a list of files and their access statuses. Out of all the files, we are only allowed to access the file at ``/var/lib/dpkg/info/bandit7.password``, where the flag is located.

>> flag : z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

![screenshot_of_solution](https://lh5.googleusercontent.com/cydKvtCMvUAcZYMFFIgI3eNitvPoVN4liWGRaNpET493k2Q5jC_cjIcB_dBcz5RNnQQ=w2400)

![screenshot_of_solution](https://lh5.googleusercontent.com/hWLpo7n7o8zVK_-2YI-OOMfVMlw4EdT0YrUWoZGhzfkloGoQ3IKVvvX5BGkPzO_bCM8=w2400)

---

## Level 7

> username : bandit7  
> password : z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

We know that the flag is situated in the file ``data.txt``, next to the word ``millionth``. Hence we use the ``strings`` and ``grep`` command together as ``strings data.txt | grep "millionth"
`` to find the flag.

>> flag : TESKZC0XvTetK0S9xNwm25STk5iWrBvP

![screenshot_of_solution](https://lh6.googleusercontent.com/F3-hckkexTmoGf6KPPABlfuNbsmh9vNv-83SKQs_ymm7CIowAwsWWbqDZME2ZEtOxik=w2400)

---

## Level 8

> username : bandit8  
> password : TESKZC0XvTetK0S9xNwm25STk5iWrBvP

As hinted by the [docs](https://overthewire.org/wargames/bandit/bandit9.html), we have to look for the line of text which only occurs once. Hence we will have to sort the file using the ``sort`` command and the use the ``uniq`` command to get the number of instances of each line of text, as ``sort data.txt | uniq -c``.

![screenshot_of_solution](https://lh6.googleusercontent.com/suehSyLp5Al1N88Y2vxih-h62NgD6klG8SFMDf8N1W4rBsXYg76eY17rlFqCyABc7Wk=w2400)

The line of text occuring only once is the flag.

![screenshot_of_solution](https://lh3.googleusercontent.com/qvqssFfjRYceBQI9WE2ASL7z6JplJZ0bhfaVlutCgDaW3W0No5rFqxXWIi-Txs1ojrc=w2400)

>> flag : EN632PlfYiZbn3PhVK3XOGSlNInNE00t

![screenshot_of_solution](https://lh4.googleusercontent.com/0pyCT2BA5QTYPy3CAirmqG3AKjq9vQf1g0beBMF9s4DZ5x-q__XubFRLsbr520ZxxwU=w2400)

---

## Level 9

> username : bandit9  
> password : EN632PlfYiZbn3PhVK3XOGSlNInNE00t

The flag is stored in the ``data.txt`` file next to several ``=`` characters. Hence, we can use the ``strings`` command again as ``strings data.txt | grep "="`` to find the flag.

>> flag : G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

![screenshot_of_solution](https://lh3.googleusercontent.com/SEn5UJ2Qxh4djNY-NwToXA-pQVe295WXDrsvmg8igpzDZym5D0a--IfaYUlAGvZOaWA=w2400)

---

## Level 10

> username : bandit10  
> password : G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

The flag is stored in the file ``data.txt``, which contains base64 encoded data. We will decrypt the file using ``base64`` command as ``base64 -d data.txt`` to get the flag.

>> flag : 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

![screenshot_of_solution](https://lh5.googleusercontent.com/L4kt7ymmOpv6C7CyjzHLJrJvPjDA3JybAaSMfK9BKkoO5sPftA4iggdAeTXD9s6e8Gs=w2400)

---

## Level 11

> username : bandit11  
> password : 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

The flag in the file ``data.txt`` has been rotated by 13 positions(ROT13). Hence we can use the ``tr`` command and transliterate the arguments of the uppercase and lowercase letters in the command by 13 positions, as ``cat data.txt | tr '[A-Za-z]' '[N-ZA-Mn-za-m]'``, giving us the flag.

>> flag : JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

![screenshot_of_solution](https://lh5.googleusercontent.com/7szMCtUX8Zxv3HZJHR29eRwQTu1UEjGiXyGL2Yr0Fvl9DkDpUfh-Fvg8Qxs3EnOj-Uw=w2400)

---

## Level 12

> username : bandit12  
> password : JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

As explained in the [docs](https://overthewire.org/wargames/bandit/bandit13.html), `data.txt` is a hexdump of a file that has been repeatedly compressed. Hence we first create a temporary directory ``alpha`` where we copy the ``data.txt`` file to work upon.

![screenshot_of_solution](https://lh4.googleusercontent.com/Ea5WCvqy8aQccsmJpd5txCylGpoCVfB_yov3zWLTGR4z5jP-JQ_GjHUgrZd2-elmt3Q=w2400)

Following this, we remove the extension from the file and check its format.

![screenshot_of_solution](https://lh4.googleusercontent.com/5ms8rtp87UkzaIHiB4D_Eko-Qgc0BojJxc0amAl-UUhy8T-1WH-eu-s5TPq2WLjNjSo=w2400)

The file comes out to be a ``gzip`` file, hence we use the ``mv`` command to rename and change its extension, and then decompress it. We then check the format of the file ``data1`` obtained.

![screenshot_of_solution](https://lh6.googleusercontent.com/Ezp7vCQU04lkwTV_WQxtgYNWEO0mrXSy-rM_gpCnWCuPKL8xc8ROQNGiUW7YwiN_jHQ=w2400)

``data1`` turns out to be a ``bzip2`` file, hence we again use the ``mv`` command to rename and change its extension, and then decompress it. We then check the format of the file ``data2`` obtained, which turns out to be another ``gzip`` file.

![screenshot_of_solution](https://lh4.googleusercontent.com/yvWM1OHoAaTopNowmOWYZkxWEpQP0-FiVmTW5TTG5KfMiXloJsqe0C3Ssywxzk0RG5M=w2400)

This process continues for a while, till we start encountering ``.tar`` files too.

![screenshot_of_solution](https://lh4.googleusercontent.com/1hd2Wj8P4DR7RVxhN1Q49ky26CRAMV4xpvtjw96CG24e09zM48Zi0HbrVMDZEi65Kgc=w2400)

After much decompressing and renaming, we finally discover ``data9``, which is an ``ASCII`` encoded file. Hence, we run ``cat data9`` to finally get the flag.

>> flag : wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

![screenshot_of_solution](https://lh3.googleusercontent.com/AdjkIkmnVQxeUeCjTNtPEYHJv-DaaX0JyTCY5otIzyn1fhBFnYqxKChDx4qxxbN1vlE=w2400)

---