## **Matryoshka doll**  
Since this challenge references Matryoshka Dolls, we can assume that there are nested files inside the file `dolls.jpg`. Hence, we use `binwalk` to check for hidden files, and sure enough we can see that there is a Zip archive in the file, leading to a folder `base_images` with another file `2_c.jpg` inside. Hence I unzip the files until I get to the flag, which we get after unzipping the file `4_c.jpg`

![screenshot of solution](https://lh6.googleusercontent.com/UtfF9EGbJl6nmSCqI-J0OUahLdVAdzSuQoz1tcQGgChMl6zSykJMRl7lXVAd_w0W_Xs=w2400)

>> flag: picoCTF{bf6acf878dcbd752f4721e41b1b1b66b}
