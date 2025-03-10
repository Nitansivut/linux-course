# a) "Hei maailma" kolmella kielellä

Tehtävä aloitettu 9.3.2025 klo 18:00. 

Tehtävänä oli kirjoittaa ja ajaa "Hei maailma" kolmella kielellä. 

Aloitin tehtävän käynnistämällä virtuaalikoneeni ja avaamalla terminaalin. Ensimmäiseksi päivitin saatavilla olevat päivitykset komennolla sudo apt-get update. Tämän jälkeen suoritin kaikki päivitykset komennolla sudo apt-get dist-upgrade.

<img width="300" alt="updaet" src="https://github.com/user-attachments/assets/744e5710-76c2-4e0b-a6b3-429f48ec54d4" />

<img width="300" alt="upgrade" src="https://github.com/user-attachments/assets/7a1d37cf-312b-422d-aa3f-7eed81e05ce6" />

Aloitin ensin Pythonilla ja lataamalla sen komennolla sudo apt-get install python3.

<img width="300" alt="python" src="https://github.com/user-attachments/assets/a8167b02-a709-4b07-a0df-4ea74db4dc12" />

Tämän jälkeen loin tiedoston heimaailma.py komennolla micro heimaailma.py ja lisäsin tiedostoon "Hei maailma" tekstin. Tallensin tiedoston Ctrl + S ja sitten Ctrl + Q. Sitten tulostin tiedoston sisällön komennolla cat heimaailma.py, jotta voisin tarkistaa, että miltä sisältö näyttää.

<img width="300" alt="cat1" src="https://github.com/user-attachments/assets/c37ff503-5398-4d5e-b581-62335053fc13" />
<br>
<br>

<img width="329" alt="pyheimaailma" src="https://github.com/user-attachments/assets/e24ea436-64e8-4732-9def-bf74fc624173" />
<br>
<br>

<img width="223" alt="image" src="https://github.com/user-attachments/assets/dc82bbe6-d84d-4e18-8d40-f2871e9c0204" />
<br>

Lopuksi ajoin komennon python3 heimaailma.py, joka tulosti tekstin "Hei maailma".

<img width="300" alt="pythonhei" src="https://github.com/user-attachments/assets/d6aa77a6-d051-4976-82a2-153d7f2df0cc" />

Seuraavaksi kokeilin kirjoittaa ja suorittaa "Hei maailma" Javalla. Tämän aloitin asentamalla Javan komennolla sudo apt-get install openjdk-17-jdk. Asennuksen aikana täytyi kirjoittaa "y", jotta asentamisessa sai mennä eteenpäin. 

<img width="299" alt="java" src="https://github.com/user-attachments/assets/dc836d3b-98b6-439f-a211-ad5ba63617f9" />

Loin tiedoston komennolla micro heimaailma.java ja kirjoitin tiedostoon kuvassa näkyvät tiedot. Tämän jälkeen tallensin tiedoston painamalla Ctrl + S ja palasin komentoriville painamalla Ctrl + Q. Lopuksi varmistin cat heimaailma.java komennolla, että tiedostoon tekemäni muutokset ovat tallentuneet. 

<img width="235" alt="microjava" src="https://github.com/user-attachments/assets/9d41acea-2cc1-4e17-bfc8-333640adb6fb" />
<br>
<br>

<img width="220" alt="heimaailma1" src="https://github.com/user-attachments/assets/3964735e-9fd2-4db3-a20c-9a3e9e0c6bc6" />
<br>
<br>

<img width="245" alt="catcat" src="https://github.com/user-attachments/assets/fd47bddd-d3a0-4612-8504-9b6a2e6bbff7" />

Sitten suoritin komennon java heimaailma, joka tulosti tekstin "Hei maailma". 

<img width="200" alt="javaheihei" src="https://github.com/user-attachments/assets/8d67f831-8763-4320-a987-8305fb83a330" />

Viimeisimpänä kokeilin kirjoittaa ja suorittaa "Hei maailma" C:llä. Aloitin taas asentamalla kielen komennolla sudo apt-get install gcc. 

<img width="249" alt="gcc" src="https://github.com/user-attachments/assets/b9b45e35-85ea-495e-a9aa-0eafb5cb43c0" />

Loin tiedoston heimaailma.c komennolla micro heimaailma.c. 

<img width="226" alt="microheimaailma" src="https://github.com/user-attachments/assets/8884f739-6e93-4242-8875-626030ca4ffc" />

Sisällön kirjoitin alla olevan kuvan mukaisesti ja tallensin tiedoston painamalla Ctrl + S ja palasin komentoriville painamalla Ctrl + Q.

<img width="331" alt="cheimaailma" src="https://github.com/user-attachments/assets/67e67533-c752-4c71-b7f4-40ac6522f256" />

Kokeilin taas cat komennolla tarkistaa miltä näyttää.

<img width="206" alt="cathei" src="https://github.com/user-attachments/assets/e8036c5c-58f2-4d3d-a436-3286974ea0e9" />

Sitten suoritin komennon gcc heimaailma.c -o heimaailmac, jonka jälkeen ajoin komennon ./heimaailmac ja tämä tulosti tekstin "Hei maailma".

<img width="280" alt="heilmaailmac" src="https://github.com/user-attachments/assets/3d5030bf-d7e6-41f7-8276-5e6811652f06" />
<br>
<br>

Lähteet

https://terokarvinen.com/2018/hello-python3-bash-c-c-go-lua-ruby-java-programming-languages-on-ubuntu-18-04/

---

# Uuden komennon luominen ja jakaminen Linuxissa

Tehtävänä oli luoda oma komento Linuxiin, jota kaikki käyttäjät voivat ajaa. Päätin toteuttaa sen Pythonilla. Halusin tuoda positiivisuutta ihmisten päivään ja niinpä tein onnenkeksi-komennon, joka tulostaa kannustavia viestejä. Viestien luomisessa hyödynsin [Fortune Frame]([https://www.fortuneframe.com/](https://fortuneandframe.com/apps/fortunes/all?srsltid=AfmBOor-33rOrg5dCsFS6t7heg1kJF9MPlBE69P6CqhW-j9WfkR8C1Xf)) -sivustolta löytyviä inspiroivia sanomia. Tekniseen puoleen hain neuvoa 

Komento toimii niin, että se valitsee yhden viestin ennalta määritetystä listasta ja tulostaa sen näytölle, kun komentoa käytetään.


Aloitin tehtävän luomalla Python-tiedoston onnenkeksi.py micro-editorilla komennolla micro onnenkeksi.py. Kirjoitin tiedostoon kuvassa näkyvän sisällön, tallensin sen painamalla Ctrl + S ja poistuin editorista painamalla Ctrl + Q.

<img width="238" alt="microonnenkeksi" src="https://github.com/user-attachments/assets/dfe0839e-1356-4102-a4d3-010e7a5722e1" />
<br>
<br>

<img width="428" alt="pythononnen" src="https://github.com/user-attachments/assets/c5107bee-211d-4f56-8c46-398fac54cdbe" />

Sen jälkeen halusin tietää, että mihin kansioon tallensin tiedoston ja tallentuiko se varmasi ja tarkistin nykyisen sijainnin komennolla pwd.

<img width="237" alt="pwd" src="https://github.com/user-attachments/assets/49c10b82-6485-4762-b37f-c9e7378ec348" />

Ja sitten etsin tekemäni tiedoston komennolla ls.

<img width="515" alt="image" src="https://github.com/user-attachments/assets/0c5b594a-b376-4d90-b976-bc4b2589c8ef" />

Sitten suoritin luomani Python-ohjelman komennolla python3 onnenkeksi.py.

<img width="341" alt="image" src="https://github.com/user-attachments/assets/a9308fb4-f087-4a81-a049-adf082b506ff" />

🥹 

Halusin vielä varmistaa, että komentoa voi käyttää muutkin, joten halusin antaa kaikille oikeuden suorittaa sen komennolla chmod ugo+x onnenkeksi.py. 

<img width="260" alt="image" src="https://github.com/user-attachments/assets/58530b37-9803-4d25-bee6-bff7d2cc555d" />

Tarkistin vielä, että suoritusoikeuden lisääminen on onnistunut komennolla ls -l onnenkeksi.py.

<img width="280" alt="image" src="https://github.com/user-attachments/assets/dbf261aa-1ff9-4bda-a377-714b3f3a892c" />

Lopuksi suoritin ohjelmani komennolla ./onnenkeksi.py, mutta sain kuvassa näkyvän syntaksin.

<img width="328" alt="image" src="https://github.com/user-attachments/assets/4206e753-d59a-40a9-ab81-03a48fce6746" />

Googlasin, miksi chmod ugo+x -komento ei toimi, ja löysin tietoa, että tiedoston alkuun pitäisi lisätä shebang-rivi #!/usr/bin/env python3. Palasin muokkaamaan tiedostoa komennolla micro onnenkeksi.py ja lisäsin kyseisen rivin sen alkuun.

<img width="418" alt="image" src="https://github.com/user-attachments/assets/92b74778-2c4c-4d46-bf6a-e8906d752366" />

Tallensin painamalla Ctrl + S ja poistuin editorista painamalla Ctrl + Q.

Sitten lähti toimimaan.

<img width="311" alt="image" src="https://github.com/user-attachments/assets/3316ceca-bb07-47c0-bac0-56ec19e55074" />


Lähteet

https://stackoverflow.com/questions/43343180/how-to-create-our-own-linux-command-for-python-code-file

https://terokarvinen.com/2018/hello-python3-bash-c-c-go-lua-ruby-java-programming-languages-on-ubuntu-18-04/

https://stackoverflow.com/questions/7670303/purpose-of-usr-bin-python3-shebang

---
  
# Tehtävissä käytetty ympäristö 

Kannettava tietokone MalliVivoBook_ASUSLaptop X421IA_M433IA

Suoritin: AMD Ryzen 7 4700U with Radeon Graphics

RAM: 8 Gt

SSD-levyn koko: 476,07 Gt, josta vapaata tilaa: 357,07 Gt

Järjestelmätyyppi: 64-bittinen käyttöjärjestelmä, x64-suoritin

Käyttöjärjestelmä: Windows 11 Home

Virtuaalikone Virtualisointi: Oracle Virtualbox versio 7.1.0 r164728 (Qt6.5.3)

Muisti: 4000 MB

CPU: 2

Virtuaalikovalevyn koko: 20.00 GB

Käyttöjärjestelmä: Debian GNU/Linux 12 (bookworm)
