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