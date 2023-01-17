## **Static ain't always noise**  
We get an ``ltdis.sh`` script file and a ``static`` 64-bit executable file. Instead of parsing the script file manually, we can directly `grep` for the flag from the executable file using the keyword ``pico`` as ``strings static | grep pico``.

>> flag:picoCTF{d15a5m_t34s3r_ae0b3ef2}

![screenshot of solution](https://lh3.googleusercontent.com/QFDYXQvYhF9yYMLzgrUPtOR1n2G4cXwn431KDjeID5Mzdngwi5F9yG9yKoNt16dsHrU=w2400)