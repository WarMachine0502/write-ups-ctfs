## **Forensics**


* **Information**  
We have got a `cat.jpg` image of a cat.

![image of cat](https://lh4.googleusercontent.com/_YEr9jY6hNUZRqHvGWRkqnJUE67qAAJzdWcfHcLDHBIG3toSYWtJK28-l9sAyW9L6XY=w2400)

I first looked through the image for any hints or the actual flag to the challenge, which proved futile.  
Since the challenge hints to look at the details of the file, I first check the filetype of `cat.jpg`, then use `exiftool` to check the metadata of the file. The details of the `IPTC Digest` and `License` stand out a bit - so I run them through a [cipher identifier](https://www.dcode.fr/cipher-identifier) to check their encryption, which turns out to be base64. Hence I try decoding both the strings, with the second string yielding the flag.

>> flag: picoCTF{the_m3tadata_1s_modified}

![screenshot of solution](https://lh3.googleusercontent.com/SBJ92rF3kif3Ily2ImokccVsUw_39hQOCD3qB5MPgtPaWTIk1BjOJtUtlRodGz1j1zU=w2400)

* **Matryoshka doll**  
Since this challenge references Matryoshka Dolls, we can assume that there are nested files inside the file `dolls.jpg`. Hence, we use `binwalk` to check for hidden files, and sure enough we can see that there is a Zip archive in the file, leading to a folder `base_images` with another file `2_c.jpg` inside. Hence I unzip the files until I get to the flag, which we get after unzipping the file `4_c.jpg`

>> flag: picoCTF{bf6acf878dcbd752f4721e41b1b1b66b}

![screenshot of solution](https://lh6.googleusercontent.com/UtfF9EGbJl6nmSCqI-J0OUahLdVAdzSuQoz1tcQGgChMl6zSykJMRl7lXVAd_w0W_Xs=w2400)

* **Glory of the Garden**  
Since the hints told us to explore an hex editor, I uploaded the file to [this hex editor](https://hexed.it/) and searched for `picoCTF{`, which highlighted the hidden flag.

>> flag: picoCTF{more_than_m33ts_the_3y3eBdBd2cc}

![screenshot of solution](https://lh6.googleusercontent.com/5Zf62xS0zD4jwwuJRrqOJxFhC87cdFhIi54DBmq5_oOyK95m_Z0Zrj73JwVTJhBbWeM=w2400)

* **File types**  
We have a file named `drawing.flag.svg`.

![drawing.flag.svg](https://lh5.googleusercontent.com/9Z07F2ExzCfGyEz69fywem_Tn_5lj6vsZeBW8kPSEWxMiQewm3LzTW4pF7mhkTG8Mag=w2400)

After `exiftool` and actually zooming into the image didn't work, I googled ways to actually see the contents of the image. Since its an `svg` file, we can use `strings` to read the file's contents.

```xml
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<!-- Created with Inkscape (http://www.inkscape.org/) -->
<svg
   xmlns:dc="http://purl.org/dc/elements/1.1/"
   xmlns:cc="http://creativecommons.org/ns#"
   xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
   xmlns:svg="http://www.w3.org/2000/svg"
   xmlns="http://www.w3.org/2000/svg"
   xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd"
   xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape"
   width="210mm"
   height="297mm"
   viewBox="0 0 210 297"
   version="1.1"
   id="svg8"
   inkscape:version="0.92.5 (2060ec1f9f, 2020-04-08)"
   sodipodi:docname="drawing.svg">
  <defs
     id="defs2" />
  <sodipodi:namedview
     id="base"
     pagecolor="#ffffff"
     bordercolor="#666666"
     borderopacity="1.0"
     inkscape:pageopacity="0.0"
     inkscape:pageshadow="2"
     inkscape:zoom="0.69833333"
     inkscape:cx="400"
     inkscape:cy="538.41159"
     inkscape:document-units="mm"
     inkscape:current-layer="layer1"
     showgrid="false"
     inkscape:window-width="1872"
     inkscape:window-height="1016"
     inkscape:window-x="48"
     inkscape:window-y="27"
     inkscape:window-maximized="1" />
  <metadata
     id="metadata5">
    <rdf:RDF>
      <cc:Work
         rdf:about="">
        <dc:format>image/svg+xml</dc:format>
        <dc:type
           rdf:resource="http://purl.org/dc/dcmitype/StillImage" />
        <dc:title></dc:title>
      </cc:Work>
    </rdf:RDF>
  </metadata>
  <g
     inkscape:label="Layer 1"
     inkscape:groupmode="layer"
     id="layer1">
    <ellipse
       id="path3713"
       cx="106.2122"
       cy="134.47203"
       rx="102.05357"
       ry="99.029755"
       style="stroke-width:0.26458332" />
    <circle
       style="fill:#ffffff;stroke-width:0.26458332"
       id="path3717"
       cx="107.59055"
       cy="132.30211"
       r="3.3341289" />
    <ellipse
       style="fill:#000000;stroke-width:0.26458332"
       id="path3719"
       cx="107.45217"
       cy="132.10078"
       rx="0.027842503"
       ry="0.031820003" />
    <text
       xml:space="preserve"
       style="font-style:normal;font-weight:normal;font-size:0.00352781px;line-height:1.25;font-family:sans-serif;letter-spacing:0px;word-spacing:0px;fill:#ffffff;fill-opacity:1;stroke:none;stroke-width:0.26458332;"
       x="107.43014"
       y="132.08501"
       id="text3723"><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.08501"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3748">p </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.08942"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3754">i </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.09383"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3756">c </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.09824"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3758">o </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.10265"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3760">C </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.10706"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3762">T </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.11147"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3764">F { 3 n h 4 n </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.11588"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3752">c 3 d _ d 0 a 7 5 7 b f }</tspan></text>
  </g>
</svg>
```

The file seems to be a proper svg file, however I see that there are some spaced characters near the end of the file inside `<tspan>` tags ; `F { 3 n h 4 n ` and `c 3 d _ d 0 a 7 5 7 b f }`. Since this seems akin to the process of enhancing something, i.e., increasing the resolution, I remove the spaces and plug this to the challenge, which comes out to be the correct flag.

>> flag: picoCTF{3nh4nc3d_d0a757bf}


* **Lookey here**  
We have got a file named `anthem.flag.txt`. First I check the filetype(`unicode`) and then check the metadata.

![screenshot of failure](https://lh3.googleusercontent.com/4ZnA-hRZ47RHdHD40fnsRVSg_sWccNeFX3o4kizcam1DEhGjK8416U5wIqusiGR72x4=w2400)

I couldn't find anything, so I decided to go through the file's contents. The hint to the challenge was very useful here - I simply ran `cat anthem.flag.txt | grep picoCTF{` to get the flag.

>> flag: picoCTF{gr3p_15_@w3s0m3_2116b979}

![screenshot of solution](https://lh5.googleusercontent.com/_34tP7gVRW9BGK-B-Vfh-JGizFAZsDMf8-lYmzqXYV2Pmlzpfsp9oUW1kZ9pnpXYqBE=w2400)

* **extensions**  
We have got a file named `flag.txt`. We get unreadable text when we use `cat`, So I check the filetype, which is actually `png`. 

![screenshot of solution](https://lh3.googleusercontent.com/CBadPO_1ROaD_dLVKsibe0TnDUmiilI4wJ3pXZQI2xerNAbS4I8QtOMmoj83EZZ588Y=w2400)

Hence we rename the file with the proper extension, after which I can simply open it using any image viewer to get the flag.

>> flag: picoCTF{now_you_know_about_extensions}

![screenshot of solution](https://lh4.googleusercontent.com/Xa8HqeVdQ3YA2BrJfLyZfiPFSCbNkEZV0XIHDfR3fnu9sp7kySqCKHCZbgQS25q5wbc=w2400)

* **So Meta**  
We have a file named `pico_img.png`. Since the challenge references metadata, I use `exiftool` to see the metadata of the image. The flag is given in the `Artist` description.

>> flag: picoCTF{s0_m3ta_eb36bf44}

![screenshot of solution](https://lh4.googleusercontent.com/-dnvZjCyFwgRKhtRdz9M8Av8qQyMutaLpF15K0Iiqy1I5bbB7eNoVMdxGlGbtM7o8KQ=w2400)