
### Questions

### Objectives

### Outline


```python
import pandas as pd
import numpy as np

import matplotlib.pyplot as plt
```

# Tools that I use

## Terminal
* iterm
    * zsh (would not set this up without help)
    * .bash_profile
    

## IDEs
* Jupyter Notebook
* Sublime Text
* PyCharm - best for python
* VSCode - best for webapps where you're coding in both python and html/css
* IntelliJ - Java coding


## Environment
* Anaconda (conda envs)
* pipenv


## Other tools
* Postman - hit urls make get/post requests, etc
* Splunk - read log files (but this is company specific)


```python
import requests
from bs4 import BeautifulSoup
```


```python
url = "https://www.ebay.com/sch/i.html?_from=R40&_trksid=p2380057.m570.l1313.TR12.TRC2.A0.H0.Xadidas+nmd+.TRS0&_nkw=adidas+nmd+&_sacat=0"

req = requests.get(url)
req.content
```


```python
soup = BeautifulSoup(req.content, 'html.parser')
```


```python
soup.find_all("img", class_="s-item__image-img")
```




    [<img alt="Mita Adidas Consortium NMD TS1 PK 8-13 Black Blue Green BC0333 Cages Coordinates" class="s-item__image-img" loading="eager" onload='SITE_SPEED.ATF_TIMER.measure(this); if (performance &amp;&amp; performance.mark) { performance.mark("first-meaningful-paint"); }' src="https://i.ebayimg.com/thumbs/images/m/mH03r1PvK4dzJxP8tZg0YjQ/s-l225.jpg"/>,
     <img alt="[D96635] Mens Adidas Nmd_R1 - White Gum" class="s-item__image-img" loading="eager" onload="SITE_SPEED.ATF_TIMER.measure(this)" src="https://i.ebayimg.com/thumbs/images/m/mbTTepBR0dQiYE5X7N5aCQw/s-l225.jpg"/>,
     <img alt="Men's adidas NMD Runner R1 Casual Shoes Core Black/Gum B42200 BLK" class="s-item__image-img" loading="eager" onload="SITE_SPEED.ATF_TIMER.measure(this)" src="https://i.ebayimg.com/thumbs/images/m/mWzimBBDivhr_1Omf1GLKxA/s-l225.jpg"/>,
     <img alt="[B42200] Mens Adidas Originals NMD_R1 - Black Gum Running Shoe" class="s-item__image-img" loading="eager" onload="SITE_SPEED.ATF_TIMER.measure(this)" src="https://i.ebayimg.com/thumbs/images/m/mT24ja3loyxfQtndWysmWuQ/s-l225.jpg"/>,
     <img alt="[B79758] Mens Adidas Originals NMD_R1 Running Sneaker - Black Carbon White" class="s-item__image-img" loading="eager" src="https://i.ebayimg.com/thumbs/images/m/mf6oMego65MOHuKnGryNA4g/s-l225.jpg"/>,
     <img alt="adidas NMD R1 Stencil White Blue Black G27916 Men Size 9.5 W/Box" class="s-item__image-img" loading="eager" src="https://i.ebayimg.com/thumbs/images/g/ZpAAAOSw7speC8oi/s-l225.jpg"/>,
     <img alt="Men's adidas NMD R1 STLT Primeknit Casual Shoes pink" class="s-item__image-img" loading="eager" src="https://i.ebayimg.com/thumbs/images/m/mSHocZdDJkUe59cD9ZSo1Aw/s-l225.jpg"/>,
     <img alt="Adidas NMD R1 Army Green Size 9.5" class="s-item__image-img" loading="eager" src="https://i.ebayimg.com/thumbs/images/g/5eMAAOSwzfFd9-rM/s-l225.jpg"/>,
     <img alt="Adidas NMD R1 Sesame Camo Size 7" class="s-item__image-img" loading="eager" src="https://i.ebayimg.com/thumbs/images/g/9msAAOSwFFBeEMyV/s-l225.jpg"/>,
     <img alt="Adidas NMD R1 BOOST Mens SZ 10 CAMO Black Orange Mesh Trainers MSRP $130" class="s-item__image-img" loading="eager" src="https://i.ebayimg.com/thumbs/images/g/VkMAAOSws11eF7WR/s-l225.jpg"/>,
     <img alt="Adidas NMD R1 LHG 029003 White Red Mens Size 12" class="s-item__image-img" loading="eager" src="https://i.ebayimg.com/thumbs/images/g/XYEAAOSwG11eGMsL/s-l225.jpg"/>,
     <img alt="New Adidas Men's Originals NMD R1 Shoes (FV9015) Black / Black-Black" class="s-item__image-img" loading="eager" src="https://i.ebayimg.com/thumbs/images/m/mQDPBF8OQYVTWXV0AXSYq8g/s-l225.jpg"/>,
     <img alt="adidas Originals NMD R1 Men Black Metalic Silver White Yellow F99713 Size 8.5" class="s-item__image-img" loading="eager" src="https://i.ebayimg.com/thumbs/images/g/7fAAAOSwKlxeGMIg/s-l225.jpg"/>,
     <img alt="Adidas NMD Japan Triple Black Sock Size 10.5 Mens " class="s-item__image-img" loading="eager" src="https://i.ebayimg.com/thumbs/images/g/EV0AAOSwlq9eEqT2/s-l225.jpg"/>,
     <img alt="Adidas Nmd R1 Pk" class="s-item__image-img" loading="eager" src="https://i.ebayimg.com/thumbs/images/g/CDEAAOSw4cFeD4gZ/s-l225.jpg"/>,
     <img alt="Adidas Nmd R1 Champs Exclusive Size 9.5" class="s-item__image-img" loading="eager" src="https://i.ebayimg.com/thumbs/images/g/zgcAAOSw4pJeFyCz/s-l225.jpg"/>,
     <img alt="New Adidas Men's Originals NMD R1 Shoes (FV9015)  Black / Black-Black" class="s-item__image-img" loading="eager" src="https://i.ebayimg.com/thumbs/images/m/mkFE0UhXqhibBt3LsC3Fqcg/s-l225.jpg"/>,
     <img alt="Adidas NMD PK R1 BA8629 MONOCHROME Black Size 10.5 Men’s" class="s-item__image-img" loading="eager" src="https://i.ebayimg.com/thumbs/images/g/nkwAAOSw83deF22W/s-l225.jpg"/>,
     <img alt='adidas NMD CS2 "Kith X Naked Pink" Size 11' class="s-item__image-img" loading="eager" src="https://i.ebayimg.com/thumbs/images/g/JqgAAOSww~VeFCOO/s-l225.jpg"/>,
     <img alt="Men’s Adidas NMD R1 Boost S79158 Lush Red  - Size 10.5 US" class="s-item__image-img" loading="eager" src="https://i.ebayimg.com/thumbs/images/g/9esAAOSw0vdeFTl0/s-l225.jpg"/>,
     <img alt="adidas Originals NMD R1 Shoes Men's (Size 8 - 13) Black Yellow White EE4400" class="s-item__image-img" loading="eager" src="https://i.ebayimg.com/thumbs/images/m/mpdG1IgRITSyGm6_OAK1kFA/s-l225.jpg"/>,
     <img alt="Adidas NMD R1 Core Black Solar Red BRED Size 9 EE5085" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/81gAAOSw3DteC8zh/s-l225.jpg"/>,
     <img alt="Mens Adidas Nmd Size 10.5 Used " class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/eqkAAOSwuchdfwKr/s-l225.jpg"/>,
     <img alt="Adidas Micropacer R1 NMD Men’s Camo Silver Red Blue Black Boost G27934 Size 12" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/sjQAAOSwHbleA0~8/s-l225.jpg"/>,
     <img alt="Adidas Micropacer R1 NMD Mens  Camo Silver Red Blue Black Boost G27934 Size 10" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/HSUAAOSwsxFeA0~0/s-l225.jpg"/>,
     <img alt="Mens Adidas NMD White Size 11" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/RCIAAOSw6WleFnG1/s-l225.jpg"/>,
     <img alt="Adidas NMD_R1 Green Camo Mens Size 10" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/imgAAOSwM2deD~yX/s-l225.jpg"/>,
     <img alt="adidas NMD_R1 Men's Sneaker BD7750 Trace Cargo / Solar Yellow" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/m/m5LwFbPw_rb_LOHx6326egg/s-l225.jpg"/>,
     <img alt="Adidas NMD r1 Black Solar Red 8.5 Running Cross Training Shoes NWT Box Included" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/WBEAAOSw6tNeFe-U/s-l225.jpg"/>,
     <img alt="BNWT Rare Authentic Adidas NMD R1 PK Tri Colour Size 13 US OG F99712" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/~8cAAOSwwp9eGMME/s-l225.jpg"/>,
     <img alt="NEW Adidas Men's NMD_R1 STLT PK Sneakers Green/Brown/White SZ 8-12 CQ2389" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/m/mzOgXyDmNqDArWnB6A4EfVw/s-l225.jpg"/>,
     <img alt="Adidas NMD R1 Grey Glitch Camo Size 9.5 BB2886" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/iAUAAOSwmgNeFLQr/s-l225.jpg"/>,
     <img alt="Adidas NMD XR1 PK Collegiate Navy Blue (BA7215) sz 13 BEATERS!  ultra boost yzy " class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/pZUAAOSw5z1d7xdu/s-l225.jpg"/>,
     <img alt="Adidas NMD R1 Running   Boost Grey/Sesame /Chalk Pearl   (B76079) Men’s Size 8.5" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/jYkAAOSwJ4peBVrI/s-l225.jpg"/>,
     <img alt="adidas nmd" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/aN8AAOSw9J9eEot1/s-l225.jpg"/>,
     <img alt="Adidas NMD CS1 GTX PK Primeknit Goretex Core White Mens Shoes BY9404 Size 11" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/sKcAAOSwIUReF4bv/s-l225.jpg"/>,
     <img alt="mens adidas nmd size 10 R1 Primeknit" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/df0AAOSwRg9eFPnh/s-l225.jpg"/>,
     <img alt="Adidas NMD Pharell Williams Human Race Orange sz 9 BB3070 DS 100% Authentic" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/wVAAAOSwvjNeGMok/s-l225.jpg"/>,
     <img alt="Adidas NMD_ C2  - Brown - Men’s -suede Size 11 - NEW- ULTRA BOOST BY9913" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/rNYAAOSwSA5d9nuT/s-l225.jpg"/>,
     <img alt="Adidas NBHD NMD DA8835 Size 9 RARE 100% Authentic Vnds" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/iPIAAOSwsmdd-aoH/s-l225.jpg"/>,
     <img alt="Adidas NMD_R1 S31510 - Size 9.5" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/VokAAOSwn1JeE4Ba/s-l225.jpg"/>,
     <img alt="Adidas NMD_R1 Sesame/Steel/Base Green Duck Camo Men's Running Shoes D96617" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/m/mLxWmw1XIb63hOJ-ekFHnnA/s-l225.jpg"/>,
     <img alt="*NEW* MENS ADIDAS ORIGINALS NMD_R1 CAMO BLACK (D96616), Sz 4-14 ,100% AUTHENTIC!" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/m/m-CaPc-WRebPoHGEoxkEkvw/s-l225.jpg"/>,
     <img alt="NEW Adidas NMD CS2 City Sock 2 Triple Black PK Ultra Boost Mens Sz 9 New" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/vrkAAOSw9zxeF~yh/s-l225.jpg"/>,
     <img alt="NEW Adidas Originals NMD R2 Mens 9.5 Gray Future Harvest White Orange BY3014" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/n4UAAOSwfiNeEVCh/s-l225.jpg"/>,
     <img alt="ADIDAS NMD R1 Black Volt BD7751 SIZES 8.5,11,11.5,12 FREE SHIPPING" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/kmYAAOSwn1JeEM6G/s-l225.jpg"/>,
     <img alt="New adidas Men’s Shoes Size 11 NMD_R2 SUMMER Grey/White/Gum Boost  CQ3080 W/Box" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/C7EAAOSwhQpdo-oT/s-l225.jpg"/>,
     <img alt="Adidas Originals Men's Shoes NMD_R1 - S31511 Gray/White/Blue Color SZ 10.5" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/x~YAAOSwi5xeF1TX/s-l225.jpg"/>,
     <img alt="Adidas NMD Hu Pharrell Inspiration Pack Black Sz. 9.5" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/tcgAAOSw5v9eCrwE/s-l225.jpg"/>,
     <img alt="Mens Adidas NMD black/gray running shoes sz 7" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/N5EAAOSwcqFeEVuF/s-l225.jpg"/>,
     <img alt="Adidas NMD_R1 PK Purple (New)" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/m/mQGybBsUT_ZtrpfM_oyjNsw/s-l225.jpg"/>,
     <img alt="New Adidas NMD R1 PK Primeknit Boost Nomad Marble Green Mens Size 10 BB7996" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/wvYAAOSw8KxeE95f/s-l225.jpg"/>,
     <img alt="Adidas NMD CS2 PK Mens Shoes Prime knit Size 10" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/ZmoAAOSwgm5eEpkC/s-l225.jpg"/>,
     <img alt="ADIDAS NMD R1 PK BOOST BB7996 NOMAD GREEN FLASH/BLACK PRIMEKNIT MENS 8.5 W/BOX!" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/4DIAAOSwN~VeBRnu/s-l225.jpg"/>,
     <img alt="[BD7750] Mens Adidas Originals NMD_R1" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/m/m1C46KgIH4yszu17JKQJdPg/s-l225.jpg"/>,
     <img alt="Adidas NMD R1 - Size 7" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/z3YAAOSw18Nd6YPC/s-l225.jpg"/>,
     <img alt="Adidas NMD R2 Summer Boost  Orange CQ3081 Running Shoes Mens Size 8 10 11 NEW" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/m/maXhNEjGC4lpVvO61ezSZYQ/s-l225.jpg"/>,
     <img alt="Adidas NMD_R1 Duck Camo Men Size 11.5 100% Authentic" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/yA8AAOSw5B9eDpc6/s-l225.jpg"/>,
     <img alt="Adidas NMD R2 Burgundy White Gum CQ2404 Running Shoes Men's Size 13 NEW" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/vWwAAOSwVCldEPmb/s-l225.jpg"/>,
     <img alt="adidas nmd grey" class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/g/9nEAAOSwB05eDn7E/s-l225.jpg"/>,
     <img alt="Adidas NMD Racer GTX Pk White Black Gore Tex Running Shoes BD7725 New " class="s-item__image-img" loading="lazy" src="https://i.ebayimg.com/thumbs/images/m/mdxEFHpOpcy0sEMwsBwpMjQ/s-l225.jpg"/>]



### What was learned today
* solidarity in the struggle
* read error messages


### What is BeautifulSoup?
* after website information (html) has been retrieved using requests
* then BS4 is used to parse an html/xml file



### When would one use webscraping?
* trying to find data from a website that doesn't have an api
* 




```python

```
