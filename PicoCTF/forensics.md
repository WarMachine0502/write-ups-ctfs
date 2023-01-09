## **Forensics**


* **Information**  
We have got a `cat.jpg` image of a cat.

![image of cat](https://lh4.googleusercontent.com/_YEr9jY6hNUZRqHvGWRkqnJUE67qAAJzdWcfHcLDHBIG3toSYWtJK28-l9sAyW9L6XY=w2400)

I first looked through the image for any hints or the actual flag to the challenge, which proved futile.  
Since the challenge hints to look at the details of the file, I first check the filetype of `cat.jpg`, then use `exiftool` to check the metadata of the file. The details of the `IPTC Digest` and `License` stand out a bit - so I run them through a [cipher identifier](https://www.dcode.fr/cipher-identifier) to check their encryption, which turns out to be base64. Hence I try decoding both the strings, with the second string yielding the flag.

>> flag: picoCTF{the_m3tadata_1s_modified}

![screenshot of solution](https://lh3.googleusercontent.com/SBJ92rF3kif3Ily2ImokccVsUw_39hQOCD3qB5MPgtPaWTIk1BjOJtUtlRodGz1j1zU=w2400)

* **Matryoshka doll**  
Since this challenge references Matryoshka Dolls, we can assume that there are nested files inside the file `dolls.jpg`. Hence, we use `binwalk` to check for hidden files, and sure enough we can see that there is a Zip archive in the file, leading to a folder `base_images` with another file `2_c.jpg` inside. Hence I unzip the files until I get to the flag, which we get after unzipping the file `4_c.jpg`

>> flag: picoCTF{bf6acf878dcbd752f4721e41b1b1b66b}

![screenshot of solution](https://lh6.googleusercontent.com/UtfF9EGbJl6nmSCqI-J0OUahLdVAdzSuQoz1tcQGgChMl6zSykJMRl7lXVAd_w0W_Xs=w2400)

* **Glory of the Garden**  
Since the hints told us to explore an hex editor, I uploaded the file to [this hex editor](https://hexed.it/) and searched for `picoCTF{`, which highlighted the hidden flag.

>> flag: picoCTF{more_than_m33ts_the_3y3eBdBd2cc}

![screenshot of solution](https://lh6.googleusercontent.com/5Zf62xS0zD4jwwuJRrqOJxFhC87cdFhIi54DBmq5_oOyK95m_Z0Zrj73JwVTJhBbWeM=w2400)

* **File types**  
dijnidvj

>> flag: 

![screenshot of solution]()

* So Meta  
dijnidvj

>> flag: 

![screenshot of solution]()

* extensions  
dijnidvj

>> flag: 

![screenshot of solution]()