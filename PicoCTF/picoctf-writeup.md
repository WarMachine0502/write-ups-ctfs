# **PicoCTF**

[PicoCTF](https://picoctf.org/) is a free cyber-security program presented  by security and privacy experts at Carnegie Mellon University, in the format of CTF-based challenges.

---

## **Tools Used**

* [https://www.dcode.fr/caesar-cipher](https://www.dcode.fr/caesar-cipher)
* [https://www.dcode.fr/vigenere-cipher](https://www.dcode.fr/vigenere-cipher)
* [https://hexed.it/](https://hexed.it/)
* [https://www.boxentriq.com/code-breaking/cipher-identifier#base64](https://www.boxentriq.com/code-breaking/cipher-identifier#base64)
* [https://onlineasciitools.com/convert-decimal-to-ascii](https://onlineasciitools.com/convert-decimal-to-ascii)
* [https://morsecode.world/international/decoder/audio-decoder-adaptive.html](https://morsecode.world/international/decoder/audio-decoder-adaptive.html)
* [https://www.dcode.fr/rot-47-cipher](https://www.dcode.fr/rot-47-cipher)
---

### **General Skills**


* **Obedient Cat**  
This challenge has a single file named `flag` to be downloaded. Simply running `cat flag` gives us the flag.

>> flag: picoCTF{s4n1ty_v3r1f13d_4a2b35fd}

![screenshot_of_solution](https://lh4.googleusercontent.com/O8VLq-2gH3pLd-ZIrFN45d6dV3hb0TYw9anAZNGc6lA4Gn9UU5LKlNSLs1JbwcjtboQ=w2400)

* **Python Wrangling**  
We have a python file named `ende.py`. Executing the file simply through python3 returns a response that the file has to be decoded. Hence we decode the python file using the flag as `python3 ende.py -d flag.txt.en`, which successfully decodes the file and gives out the flag after getting the password from the ``pw.txt`` file.

>> flag: picoCTF{4p0110_1n_7h3_h0us3_68f88f93}

![screenshot_of_solution](https://lh4.googleusercontent.com/2POlX5BY2Cnzm3PuzIm9Cp_tqJhXKORjhpdv5E_GiQtHWSicTO3i716BGSsO3Re_c0U=w2400)

* **Wave a flag**  
We have a file named `warm`, which does not give out human-readable values when we browse its contents through ``cat``. Hence we check the filetype of ``warm``, which reveals that it is a 64-bit executable file. Hence we give it executable privileges using the ``chmod +x warm`` command and then try and run it using ``./warm``. This gives us further instructions on what arguments is required by the file, and we finally get the flag after running ``./warm -h``.

>> flag: picoCTF{b1scu1ts_4nd_gr4vy_6635aa47}

![screenshot_of_solution](https://lh5.googleusercontent.com/qv3WcK9DU7D_BGVp8nKrwBcIhKQ2fQ-kKJTytRzMhRFL8fLvPsvXcYWCBgIdooptSac=w2400)

* **Nice netcat...**  
We have got a simple address to connect to using netcat, hence we run ``nc mercury.picoctf.net 49039`` to connect. This gives us a series of decimal values with no apparent meaning. However, using a simple tool such as this [Decimal to ASCII Converter](https://onlineasciitools.com/convert-decimal-to-ascii), we can convert these decimal values to our flag.

>> flag: picoCTF{g00d_k1tty!_n1c3_k1tty!_3d84edc8}

![screenshot_of_solution](https://lh5.googleusercontent.com/9qMIGNSV_6kflKKMCKADw8GhVes6EE5yKHSQLO_a_rk0IhLZD0zi6EXLbzFC5pmyFr0=w2400)
![screenshot_of_solution](https://lh3.googleusercontent.com/NXWgKOIhSSqVyLpPvDGiS9zo68gezavPTT53B2-qhH_f_OgfZA2jBnoii_VFifuILis=w2400)

* **Static ain't always noise**  
We get an ``ltdis.sh`` script file and a ``static`` 64-bit executable file. Instead of parsing the script file manually, we can directly `grep` for the flag from the executable file using the keyword ``pico`` as ``strings static | grep pico``.

>> flag:picoCTF{d15a5m_t34s3r_ae0b3ef2}

![screenshot of solution](https://lh3.googleusercontent.com/QFDYXQvYhF9yYMLzgrUPtOR1n2G4cXwn431KDjeID5Mzdngwi5F9yG9yKoNt16dsHrU=w2400)

* **Magikarp Ground Mission**  
We connected to the given address using SSH as outlined in the challenge after starting an instance. Then we used ``ls`` to check the active directory, where we got part of the flag and instructions on how to obtain the rest of the flag. Correctly following all of the instructions gives us the complete flag.


>> flag: picoCTF{xxsh_0ut_0f_\/\/4t3r_540e4e79}

![screenshot of solution](https://lh6.googleusercontent.com/sLKgNqY3Y4XGeBunXOfQg9SytDj-btuLATxnQ-4ktCYb1qoqJaWQAxQA3CWZIvX1j0I=w2400)

* **Lets Warm Up**  
This challenge only involves converting ``0x70``, an hexadecimal radix, to ASCII. Converting it by creating a hexdump using the ``xxd`` command in the terminal gives us the primitve of the flag.

>> flag: picoCTF{p}

![screenshot of solution](https://lh4.googleusercontent.com/5AWkrr1e0nt06Iu4IGlmVF6LudGwusJLGlI_Pz_yhBJPlIqimEF04zWLDJhv0bZ1Dss=w2400)

* **Warmed Up**  
This challenge requires us to convert the hexadecimal value ``0x3D`` to decimal.

>> flag: picoCTF{61}

![screenshot of solution](https://lh5.googleusercontent.com/x-eG2ipKZW_WbgGsvq6ARyVxGlf5gX0cTl97A0qu9pPlubuxH-BJzLjDNIpfRk2S8Pk=w2400)

* Tab, Tab, Attack

* 2Warm

* what's a net cat?

* strings it

* Bases

* First Grep

* Codebook

* convertme.py

* fixme1.py

* fixme2.py

* Glitch Cat

* HashingJobApp

* PW Crack 1

* PW Crack 2

---

### **Cryptography**


* **Mod 26**  
This challenge presents us a simple plaintext to be decrypted using ROT13.

>> flag: picoCTF{next_time_I'll_try_2_rounds_of_rot13_hWqFsgzu}


![screenshot of solution](https://lh3.googleusercontent.com/ze4-XrUJKD3f7uUD47gQs3pdatopY_tiWb6ZAIYENbgdL0-Om5v09qR-OiR4_QJyWDM=w2400)

* **The Numbers**  
We get an image with the following ciphertext:

![screenshot of ciphertext](https://lh3.googleusercontent.com/RCUhXTEmmSuSrBiaWj9apuiCDS6rDfpbbQjWWHcsh5W-sVXVFoHxfESQgz77ZowVsGQ=w2400)

This is a simple substitution cipher, where each letter is substituted by a number - A is 1, B is 2, C
is 3 and so on. Deciphering this gives the flag.

>> flag: picoCTF{THENUMBERSMASON}

* **Easy1**  
We have got an encrypted ciphertext ``UFJKXQZQUNB``, a key ``SOLVECRYPTO`` along with a table, which is just a classic example of a Vigenère Cipher.

![screenshot of table](https://lh3.googleusercontent.com/spMQS464g6e_qBNOPrTUgcoQCCnOqYT-r5WdOCYxi3CiN9KRTJW-N_n4GUIpIveHxXA=w2400)

We can use any [online Vigenère Cipher](https://www.dcode.fr/vigenere-cipher) to decrypt and obtain the flag.


>> flag: picoCTF{CRYPTOISFUN}

![screenshot of solution](https://lh4.googleusercontent.com/Q59dS9aCbYswA5rxhT45-Mx3fB-Fh3LTE27C5ox58ZTYYl5Ii6YvGDZwSVY57LVtYcc=w2400)

* **13**  
This challenge is also a classic example of ROT13.

>> flag: picoCTF{not_too_bad_of_a_problem}

![screenshot of solution](https://lh3.googleusercontent.com/R5uFhtshsrVTCaSwY0h7R0Se3bLLTNm994KvfJLG5lfDbLkG8uF305Ag2745hq0rrpc=w2400)

* **caesar**  
We have got a file name ``ciphertext`` which has the text `picoCTF{ynkooejcpdanqxeykjrbdofgkq}` inside. 

![screesnhot of ciphertext](https://lh3.googleusercontent.com/Dw0mhEVEMYFMJGdXYqRqeheGt7Nb7Rn0nWtBpVf6pu5o1R9lEJhS_yKQ-kFTqI8-XJo=w2400)

Since the challenge clearly references the use of a Caesar Cipher, we can use any [online Caesar Cipher Tool](https://www.dcode.fr/caesar-cipher) to decrypt the message

>> flag: picoCTF{crossingtherubiconvfhsjkou}

![screenshot of solution](https://lh3.googleusercontent.com/U_EtSNDcpuLbnLqot8fY3eP23p0jCvdkbVk0lcyGX-h0YGpRaJ_kxSYOR3t9JX2EKTg=w2400)

* **morse-code**  
As directed by the challenge, we open the file `morse_chal.wav` in Audacity to get the following waveform.

![screenshot of waveform](https://lh5.googleusercontent.com/pUPiMw2kkvrphfAtuXQRLiq9fF-sJHMYNix_7EEu9lcMgjRA8YWExV6aDgKT21SDNaA=w2400)

To convert the waveform to text we can use any [online tool](https://morsecode.world/international/decoder/audio-decoder-adaptive.html) for converting morse code audio to text to get the flag.

>> flag: picoCTF{wh47_h47h_90d_w20u9h7}

![screenshot of solution](https://lh5.googleusercontent.com/cjdwxDY_t8CYK7jnYzXCNdYi3nBavvjxUppdos4IVUmNx5xCOFcMm0rzOXxLgk6dkn4=w2400)

* **Vigenere**  
We have got another example of the Vigenère Cipher with the ciphertext in the file `cipher.txt` and the key `CYLAB`.

![screenshot of ciphertext](https://lh6.googleusercontent.com/9RtGrmZWveYF14D_tmgi9ld8LvCVPHa9UBd56-qRj38Mym_p5L5MTNQGsuXj_eVQTFg=w2400)

We can use any [online Vigenère Cipher](https://www.dcode.fr/vigenere-cipher) to decrypt and obtain the flag.

>> flag: picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_2951a89h}

![screenshot of solution](https://lh6.googleusercontent.com/9BxrnHzkyvv8ECDn8wtSO1IWh9Ynko98lR1wJUypm5b5vDSkJKJRAqbCC4pcReoFje0=w2400)

---

### **Reverse Engineering**


* **Transformation**  
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

* **vault-door-training**  
We get a file named `VaultDoorTraining.java`, where upon examining its contentc we find a probable string with underscores in a return password function - `w4rm1ng_Up_w1tH_jAv4_be8d9806f18`. Affixing `picoCTF{}` to the string turns out to be the flag for the challenge. 

>> flag: picoCTF{w4rm1ng_Up_w1tH_jAv4_be8d9806f18}

![screenshot of solution](https://lh5.googleusercontent.com/aLLu8kp9yfP6q0U3Ns3-Ruu5gOXQIgc8mJq-6VmXs5yIHs-iNq2irZ2bCb7q0hkBcXg=w2400)

* keygenme-py

* **crackme-py**  
We get a file named `crackme-py` with the following content.

![screenshot of file_contents](https://lh5.googleusercontent.com/OygKzH1AKCnDAUg-l5btpVtQ9OCi-kpB5tzAkhpm-g-vl_qhiNksGVBsesUIRtVcw9I=w2400)

Upon examing the code, we can see that there is a ciphertext ``bezos_cc_secret = "A:4@r%uL`M-^M0c0AbcM-MFE02fh3e4a5N"`` as well as the use of ROT47 in the program. We can use any [online ROT47 Decryption Tool](https://www.dcode.fr/rot-47-cipher) to decrypt the cipher and get the flag.

>> flag: picoCTF{1|\/|_4_p34|\|ut_a79b6c2d}

![screenshot of solution](https://lh5.googleusercontent.com/2Wn7HhMVB49715Zht6ZaqY96n2-SRKwFySiuJuEiDUC-lqc-3PJkAfbrDmRVKRca4Zc=w2400)
---

### Web Exploitation


* GET aHEAD  

* Cookies  
The challenge description leads us to a website 

* Insp3ct0r

* Scavenger Hunt

* where are the robots

* logon

* dont-use-client-side

* It is my Birthday

* login

* Includes

* Inspect HTML

* Local Authority

* Search Source

* caas

* Client-side-again

* Web Gauntlet

* Power Cookie

* Roboto Sans

* notepad

* Irish-Name-Repo 1

* SQLiLite

* Irish-Name-Repo 2

* Irish-Name-Repo 3

---

### Forensics


* Information

* Matryoshka doll

* tunn3l v1s10n

* Glory of the Garden

* Wireshark doo dooo do doo...

* So Meta

* extensions

---



### Binary Exploitation


* nothing

---