## **Transformation**  
We get a file `enc` which has these characters - `灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸彥㜰㍢㐸㙽`. Also, we have got some python code - `''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])` -  which references the use of `chr` and `ord` - commands used to convert characters to int. 

![screenshot of ciphertext](https://lh5.googleusercontent.com/b2jwDQ4TGH0YhfjtzeGIfFY9dJ1yOYe6sD1qTSzZDmF9kBReB2EpgeRwaTTa_b6AUK4=w2400)

Since this is a challenge in Reverse Engineering, we can deduce that this program has been used to encrypt the ciphertext. We can deduce that the program shifts the bits of every other letter of the flag by 8 bits and adds the the next letter of the flag to the shifted value. Based on this, we can write a python script to loop through the ciphertext to get the flag.

![screenshot of solution](https://lh4.googleusercontent.com/2BCyfx3e0BMEhtflkBNtPqWLy_PZanUMJl6rQLiU15WjvobYZ6BciWAYWCHmTSv0dNI=w2400)

```python
ciphertext = open("enc").read()
flag = ""
for i in range(0, len(ciphertext)):
    ch1 = chr((ord(ciphertext[i]) >> 8))
    ch2 = chr(ciphertext[i].encode('utf-16be')[-1])
    flag += ch1
    flag += ch2

print("The Flag is " + flag)
```
>> flag: picoCTF{16_bits_inst34d_of_8_e703b486}

![screenshot of solution](https://lh4.googleusercontent.com/8p0WjIlwCau3Pp5d6V0ztpqz8Qr-6wySuO09OqXpUOCM-3Znew-DVTyT887Iso3NGuw=w2400)
