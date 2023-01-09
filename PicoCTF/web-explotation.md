## **Web Exploitation**


* **GET aHEAD**  
We have an [HTML page](http://mercury.picoctf.net:28916/) with the following code.

```HTML
<!doctype html>
<html>
<head>
    <title>Red</title>
    <link rel="stylesheet" type="text/css" href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css">
	<style>body {background-color: red;}</style>
</head>
	<body>
		<div class="container">
			<div class="row">
				<div class="col-md-6">
					<div class="panel panel-primary" style="margin-top:50px">
						<div class="panel-heading">
							<h3 class="panel-title" style="color:red">Red</h3>
						</div>
						<div class="panel-body">
							<form action="index.php" method="GET">
								<input type="submit" value="Choose Red"/>
							</form>
						</div>
					</div>
				</div>
				<div class="col-md-6">
					<div class="panel panel-primary" style="margin-top:50px">
						<div class="panel-heading">
							<h3 class="panel-title" style="color:blue">Blue</h3>
						</div>
						<div class="panel-body">
							<form action="index.php" method="POST">
								<input type="submit" value="Choose Blue"/>
							</form>
						</div>
					</div>
				</div>
			</div>
		</div>
	</body>
</html>
```

Inspecting the buttons, we can clearly see that they are part of seperate forms with the methods `GET` and `POST`, which are types of `https` requests.
As `HEAD` was prominently highlighted in the challenge title, we can try sending out a `HEAD` request using `curl`, which supports `https` requests. This gives us the flag.

![screenshot of solution](https://lh4.googleusercontent.com/4CZk5Kwbd_Lzf89IvXNqa4Ij5BDxVMrchDo0MigcYyAViwYtAiGSD3PEn46QdzkLY8Y=w2400)

>> flag: picoCTF{r3j3ct_th3_du4l1ty_70bc61c4}

* **Cookies**  
The challenge description leads us to a [website](http://mercury.picoctf.net:64944/) with content about actual cookies. So I go over to the DevTools on my browser and check the cookies for the websites, where I see the value `-1` to the cookie `Name`. Hence I change its value to `0` and refresh the page, and the page starts displaying names of cookies.

![screenshot of sample page](https://lh3.googleusercontent.com/XqNFrgIQvfaspmVMHThvzJC8JMdznFibGwMTiLYyPX7l0I2_PrXAGIWSfTJcdyWO5xA=w2400)

This continues till the value `17` of the cookie. The website displays the flag at `18`.

![screenshot of solution](https://lh3.googleusercontent.com/Wx9IEPot9Jd6wxTsEkn7ZggdoVwNF0wUGiC-jm0yMVrRVYH_RIuKa-EzZNL1QbkeUzo=w2400)

>> flag: picoCTF{3v3ry1_l0v3s_c00k135_cc9110ba}

* **Insp3ct0r**  
We have a [basic website](https://jupiter.challenges.picoctf.org/problem/44924/) in the challenge, with instructions to inspect its code. Hence I opened up DevTools and looked at the HTML, which had a third of the flag as shown.

![1/3 of the solution](https://lh4.googleusercontent.com/GHg5KAhr9PtYiDcg_rhDCzURRLhe_bvKSVJQuY_MTerz5xAT79JU7LeQOQnGKqdDW0Q=w2400)

Since we are on the right track, I further look up the site's sources to see that the website also employs a `myjs.js` file and `mycss.css` file, which have the remaining two parts of the flag.

![2/3 of the solution](https://lh4.googleusercontent.com/Q8XBu4zDaewPrOZC9z-lZviKorU4Nlh_x8bxgZBYVEm_QQtpA_PfkBlRwGa9nxKcl30=w2400)

![3/3 of the solution](https://lh4.googleusercontent.com/qMz31N0UoyVVtHxzqygK77fs46E8rz7KjxJIEDdPq4FsqlavIusrMPpNKSmZdBFZHhg=w2400)

>> flag: picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?f10be399}

* **Scavenger Hunt**  
This challenge is similar to **Insp3ct0r**; we find the first and second part of the flag easily in the HTML and CSS part of the website respectively.  

![part1 of solution](https://lh5.googleusercontent.com/3hEmvG1l4KWhv5M8bj4NGJq3UI-p6bD-pGAv1S8mG4QIBt-r0-w4Eb-DKtnrhumS49Y=w2400)

![part2 of solution](https://lh3.googleusercontent.com/fQGbRvnumjhOqGnangF38HUiW3URjWN_CyMxE6vMN_MCVUipBjLfh-G4u4w8vK_N0uw=w2400)

As soon as we get to the JavaScript file, we get the folloiwng hint - `How can I keep Google from indexing my website?`

![part3 of solution](https://lh3.googleusercontent.com/YQ40S_H5BripTE6er9rGYW-NPXyrfIpo6HY1zmbxfzaQxC-eTqof8VKt7mcCJRIIwtc=w2400)

We seem to have encountered the same issue in **where are the robots**; we need to access the `robots.txt` file where we append files for non-indexing. Accessing the [robots.txt](http://mercury.picoctf.net:55079/robots.txt) file of the server gives us the third part of the flag, as well as the next hint - `I think this is an apache server... can you Access the next flag?`

![part4 of solution](https://lh6.googleusercontent.com/9695pHxhF3mYO49cWvL2OMEIRALt3WkRja6nWvuZKjxuVyVOt-ye7Jo7itWFclEH5Ps=w2400)

Since the word `Access` was emphasized, I did a bit of googling with the hey words `https`,`Apache`, and `Access`, which led me to the discovery of controlof main configuration files on an Apache server by `.htaccess`, hence I visited the [.htaccess](http://mercury.picoctf.net:55079/.htaccess) file to get the fourth part of the flag and the next clue - `I love making websites on my Mac, I can Store a lot of information there.`

![part5 of solution](https://lh6.googleusercontent.com/XqWMgCcV2Oa8mHppo6PjzXQ1IqeTL0Q4cmhtXQF2C48p3EFJmNALYTRjGFzsZEJhm4o=w2400)

Again, after much googling the keywords `Apple`, `Mac`, `Store`, and `folder`, I came to discover `.DS_Store`, a proprietary file system present on Apple Macintoshes to store custom attributes. Hence, visiting the [.DS_Store](http://mercury.picoctf.net:55079/.DS_Store) page brought me to the final part of the flag.

![final part of solution](https://lh5.googleusercontent.com/Ve229hPSoEzBKqYLZ8wQcJZ4jlYt7bHinf4FaYObJ2HFG7S_5A2GUPyRt0FtOTo3Vm4=w2400)

>>flag: picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_74cceb07}

* **where are the robots**  
We are provided with a basic [website](https://jupiter.challenges.picoctf.org/problem/60915/) with the following content.

![screenshot of website](https://lh3.googleusercontent.com/wmeWzLEJ_Axrdhc9kDA2EzLJXWCzKure-tWSHRdq4gi2v8X1StxthFHBNxFLqX7ztP8=w2400)

Since the challenge and the website prominently mentioned `robots`, I visited the [robots.txt](https://jupiter.challenges.picoctf.org/problem/60915/robots.txt) page to get the non-indexed pages, which sure enough had [/8028f.html](https://jupiter.challenges.picoctf.org/problem/60915/8028f.html) disallowed.

![screenshot of robots.txt](https://lh5.googleusercontent.com/LqDVbDLu2Npdvp2URIf97vQ-d8a7TzJjSNnmou1-ISq8wl4zZpkGHmLfGS-VIFs9p7c=w2400)

The [/8028f.html](https://jupiter.challenges.picoctf.org/problem/60915/8028f.html) page had the flag.

![screenshot of solution](https://lh3.googleusercontent.com/orLUTJIaaYua4s0aEse3eP0lzhPLuZBlBiCbGkFyN8L0CX_dkNnKfNQZbbL6heY07gY=w2400)

>> flag: picoCTF{ca1cu1at1ng_Mach1n3s_8028f}

* **logon**  
We are presented with a basic [login page](https://jupiter.challenges.picoctf.org/problem/15796/) as shown.

![screenshot of website](https://lh4.googleusercontent.com/DLgWpQeR0uW6phFHdsF_u4OaK3lYK94urHnIw2vG8kl55b8O8mPzpL8guVLxwIVsIbA=w2400)

As hinted by the description, the site only checks crdentials if the Username is `Joe`; all other Users are let through without any verification. Hence, the user `Joe` must have been assigned `admin` privileges, which led me to the cookie `admin` on the website that was `False` for all unverified users.

![screenshot of cookie](https://lh6.googleusercontent.com/DARqRar5UkRVyJBA4THIm-NrEw2FbDAyRrox-yj4s2I2ikud-9KG-0jUu9zxUyn7j7M=w2400)

Changing the cookie's value from `False` to `True` gives us the flag.

![screenshot of solution](https://lh3.googleusercontent.com/CCfKM9_Y4tvlOVjkSY8sFzib_ayZLaDfukIwuOcJOgS8TA-KG32s4psJlt8S-1iGwp4=w2400)

>> flag: picoCTF{th3_c0nsp1r4cy_l1v3s_6edb3f5f}

* **dont-use-client-side**  
We have got a plain website with a form, with the following HTML Code.

```HTML
<html>
<head>
<title>Secure Login Portal</title>
</head>
<body bgcolor=blue>
<!-- standard MD5 implementation -->
<script type="text/javascript" src="md5.js"></script>

<script type="text/javascript">
  function verify() {
    checkpass = document.getElementById("pass").value;
    split = 4;
    if (checkpass.substring(0, split) == 'pico') {
      if (checkpass.substring(split*6, split*7) == '723c') {
        if (checkpass.substring(split, split*2) == 'CTF{') {
         if (checkpass.substring(split*4, split*5) == 'ts_p') {
          if (checkpass.substring(split*3, split*4) == 'lien') {
            if (checkpass.substring(split*5, split*6) == 'lz_7') {
              if (checkpass.substring(split*2, split*3) == 'no_c') {
                if (checkpass.substring(split*7, split*8) == 'e}') {
                  alert("Password Verified")
                  }
                }
              }
      
            }
          }
        }
      }
    }
    else {
      alert("Incorrect password");
    }
    
  }
</script>
<div style="position:relative; padding:5px;top:50px; left:38%; width:350px; height:140px; background-color:yellow">
<div style="text-align:center">
<p>This is the secure login portal</p>
<p>Enter valid credentials to proceed</p>
<form action="index.html" method="post">
<input type="password" id="pass" size="8" />
<br/>
<input type="submit" value="verify" onclick="verify(); return false;" />
</form>
</div>
</div>
</body>
</html>
```

The form is clearly checking any string entered with the characters in the `substring()` functions.

```HTML
<script type="text/javascript">
  function verify() {
    checkpass = document.getElementById("pass").value;
    split = 4;
    if (checkpass.substring(0, split) == 'pico') {
      if (checkpass.substring(split*6, split*7) == '723c') {
        if (checkpass.substring(split, split*2) == 'CTF{') {
         if (checkpass.substring(split*4, split*5) == 'ts_p') {
          if (checkpass.substring(split*3, split*4) == 'lien') {
            if (checkpass.substring(split*5, split*6) == 'lz_7') {
              if (checkpass.substring(split*2, split*3) == 'no_c') {
                if (checkpass.substring(split*7, split*8) == 'e}') {
                  alert("Password Verified")
                  }
                }
              }
      
            }
          }
        }
      }
    }
    else {
      alert("Incorrect password");
    }
    
  }
</script>
```
Piecing together the flag from the functions gives us the flag, which displays `Password Verified` on the website.

>> flag: picoCTF{no_clients_plz_7723ce}


* **Roboto Sans**  
The challenge presents us a [promotional page](http://saturn.picoctf.net:64710/) with no apparent anomalies. However, since the title of the challenge references robots, we navigate to the [robots.txt](http://saturn.picoctf.net:64710//robots.txt) page of the website to see some interesting text.

![screenshot of robots.txt](https://lh3.googleusercontent.com/g6rP7ttu4UGDNA0HxgPCX5LIBEBzc195fvgvX2q5w6wTmI9OgoNxWlyZfmI5sBoEieQ=w2400)

I tried visiting the disallowed pages but those didn't pan out, neither could I brute-force the addresses as it is an `nginx` server; however I did recognise the 3 lines of gibberish as `base64` encoded text. The middle line, `anMvbXlmaWxlLnR4dA==`, was decrypted to an address, `js/myfile.txt`. Visiting the [address](http://saturn.picoctf.net:64710/js/myfile.txt) gives us the flag.

![screenshot of solution](https://lh3.googleusercontent.com/gcHt8Uxw8D2CA6T_swqQB4IDrcV3N54D41KbtgYMjEIepFwC9vOlHpykxQGLdh-QZCc=w2400)

>> flag: picoCTF{Who_D03sN7_L1k5_90B0T5_032f1c2b}

* **login**  


* Includes

* Inspect HTML

* Local Authority

* Search Source

* caas

* Client-side-again

* Web Gauntlet

* Power Cookie

* It is my Birthday

* notepad

* Irish-Name-Repo 1

* SQLiLite

* Irish-Name-Repo 2

* Irish-Name-Repo 3