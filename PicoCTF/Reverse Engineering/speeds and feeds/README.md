## **speeds and feeds**  
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
