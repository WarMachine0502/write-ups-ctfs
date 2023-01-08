## **General Skills**


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