## **Information**  
We have got a `cat.jpg` image of a cat.

![image of cat](https://lh4.googleusercontent.com/_YEr9jY6hNUZRqHvGWRkqnJUE67qAAJzdWcfHcLDHBIG3toSYWtJK28-l9sAyW9L6XY=w2400)

I first looked through the image for any hints or the actual flag to the challenge, which proved futile.  
Since the challenge hints to look at the details of the file, I first check the filetype of `cat.jpg`, then use `exiftool` to check the metadata of the file. The details of the `IPTC Digest` and `License` stand out a bit - so I run them through a [cipher identifier](https://www.dcode.fr/cipher-identifier) to check their encryption, which turns out to be base64. Hence I try decoding both the strings, with the second string yielding the flag.

![screenshot of solution](https://lh3.googleusercontent.com/SBJ92rF3kif3Ily2ImokccVsUw_39hQOCD3qB5MPgtPaWTIk1BjOJtUtlRodGz1j1zU=w2400)

>> flag: picoCTF{the_m3tadata_1s_modified}