## **Reverse Engineering**


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

* **crackme-py**  
We get a file named `crackme-py` with the following content.

![screenshot of file_contents](https://lh5.googleusercontent.com/OygKzH1AKCnDAUg-l5btpVtQ9OCi-kpB5tzAkhpm-g-vl_qhiNksGVBsesUIRtVcw9I=w2400)

Upon examing the code, we can see that there is a ciphertext ``bezos_cc_secret = "A:4@r%uL`M-^M0c0AbcM-MFE02fh3e4a5N"`` as well as the use of ROT47 in the program. We can use any [online ROT47 Decryption Tool](https://www.dcode.fr/rot-47-cipher) to decrypt the cipher and get the flag.

>> flag: picoCTF{1|\/|_4_p34|\|ut_a79b6c2d}

![screenshot of solution](https://lh5.googleusercontent.com/2Wn7HhMVB49715Zht6ZaqY96n2-SRKwFySiuJuEiDUC-lqc-3PJkAfbrDmRVKRca4Zc=w2400)

* **vault-door-1**  
We have got a simple Java file named `VaultDoor1.java` with the following content.

```java
import java.util.*;

class VaultDoor1 {
    public static void main(String args[]) {
        VaultDoor1 vaultDoor = new VaultDoor1();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
	String userInput = scanner.next();
	String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
	if (vaultDoor.checkPassword(input)) {
	    System.out.println("Access granted.");
	} else {
	    System.out.println("Access denied!");
	}
    }

    // I came up with a more secure way to check the password without putting
    // the password itself in the source code. I think this is going to be
    // UNHACKABLE!! I hope Dr. Evil agrees...
    //
    // -Minion #8728
    public boolean checkPassword(String password) {
        return password.length() == 32 &&
               password.charAt(0)  == 'd' &&
               password.charAt(29) == '9' &&
               password.charAt(4)  == 'r' &&
               password.charAt(2)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(3)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(1)  == '3' &&
               password.charAt(7)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(5)  == '4' &&
               password.charAt(9)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(8)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(6)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == '5' &&
               password.charAt(30) == '2' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == '0' &&
               password.charAt(26) == '7' &&
               password.charAt(31) == 'e';
    }
}
```

In the later half of the file, we can clearly deduce that the function `charAt()` is clearly used to reference the characters in the flag, albeit out of order. Hence we can simply assemble the characters of the flag in the correct order and pass the challenge.

>> flag: picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_75092e}

* **speeds and feeds**  
When we actually connect to the given address using `netcat` as `nc mercury.picoctf.net 33596`, we get the following content on the terminal.

```
G17 G21 G40 G90 G64 P0.003 F50
G0Z0.1
G0Z0.1
G0X0.8276Y3.8621
G1Z0.1
.
.
.
.
G1X199.3103Y-0.8276
G1X199.0345Y-1.3793
G1X198.7586Y-1.6552
G1X198.2069Y-1.9310
G0Z0.
```
The actual content was more than a 1000 lines long, so I tried googling the first couple lines. It turns out that my terminal was displaying CNC G Codes and the program itself is used to synchronise and plot motion at predetermined rates on multiple axes. These codes are typically utilised by CNC Machines. So I googled a [simulator](https://ncviewer.com/) to plot the G Codes and got the flag.

>> flag: picoCTF{num3r1cal_c0ntr0l_e7749028}

![screenshot of solution](https://lh3.googleusercontent.com/mr1hn_d8NpUoh1PfI7esz_9-euCaH9vAJd9ruyS_Qz69x1LjiYgJ68LDXKJ3J1Jav2M=w2400)

* **Safe Opener**  
We get a Java file named `SafeOpener.java` with the following contents.

![screenshot of file_contents](https://lh3.googleusercontent.com/n88yF0e2MPDCU0fRj5ppmEoHMOrrwCWZ6QHWDVgKFO2nxSbDzuMD77o1o2VeIDL9JZw=w2400)

Here, we can see that the programs checks the string passed with an `encodedkey = cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz`, which appears to be a `base64` encoded string. Deciphering the string using any [online Base64 deocder](https://emn178.github.io/online-tools/base64_decode.html) to get the flag.

>> flag: picoCTF{pl3as3_l3t_m3_1nt0_th3_saf3}

![screenshot of solution](https://lh3.googleusercontent.com/r751RQl3kkx9tI07nqEhB0llqhFp6tyliCpSh6_Tm5fWYeJOzxvHVL-KFWr1mrtPjE0=w2400)

* **GDB Test Drive**  
This challenge is simple enough. Just executing the `gdbme` file using the GNU Debugger and executing the commands given in the challenge gives us the required flag to pass the challenge.

>> flag: picoCTF{d3bugg3r_dr1v3_7776d758}

![screenshot of solution](https://lh4.googleusercontent.com/sRqwgvAe_fV-ExmTjmdMQd7pYUCQBh_HESa70bEDK-SFx0i57d4HcZrzQ7PouGuvggU=w2400)