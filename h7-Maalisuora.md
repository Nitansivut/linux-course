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
# d) Vanhan laboratorioharjoituksen ratkaiseminem

Tässä tehtävässä tuli ratkaista vanha laboratorioharjoitus. Tehtävä löytyy opettaja Teron sivuilta [Final Lab for Linux Palvelimet 2024 Spring](https://terokarvinen.com/2024/arvioitava-laboratorioharjoitus-2024-linux-palvelimet/). Tässä ei tarvitse raportoida kaikkia askelia, vain testit että asiat toimivat, tai maininta, että tätä ei ole tehty. 

Alkuun loin uuden tyhjän Linux-virtuaalikoneen samalla tavalla kuin tämän kurssin ensimmäisessä kotitehtävässä h1. Suoritin kaikki saatavilla olevat päivitykset komennoilla sudo apt-get update ja sudo apt-get dist-upgrade sekä asensin palomuurin komennolla apt-get -y install ufw ja otin sen käyttöön komennolla sudo ufw enable.

<img width="951" alt="image" src="https://github.com/user-attachments/assets/a1438b8b-aee2-4b5a-a4ee-059b3d71fe42" />

## Tehtävät a-c

Ensin loin kotihakemistooni kansion "raportti" ja tallensin siihen raporttitiedoston nimeltä index.md. Sen jälkeen määrittelin tiedostolle Linux-oikeudet niin, että vain oma käyttäjäni pystyy lukemaan raportin. Kuitenkin kirjoitin itse raportin GitHubiin, tämä tiedosto oli vain tehtävän suorittamista varten. En tehnyt muita tehtävien vaiheita.

<img width="263" alt="image" src="https://github.com/user-attachments/assets/39c0638e-0742-4b27-8de0-bdf1b2fcaf69" />
<br>

<img width="340" alt="image" src="https://github.com/user-attachments/assets/bbc1ff05-bb81-45c2-bee2-19350e58d511" />
<br>

<img width="395" alt="image" src="https://github.com/user-attachments/assets/a063a84e-d2b3-4172-b592-e20eabfbf9dd" />
<br>

<img width="329" alt="image" src="https://github.com/user-attachments/assets/210202db-4924-4467-9643-a0c3ae0e8a4e" />
<br>

<img width="295" alt="image" src="https://github.com/user-attachments/assets/e97becba-d129-4ef0-b5d4-6d956d7d85de" />

Seuraavaksi tarkistin index.md-tiedoston oikeudet komennolla ls -l /home/nitafinallab/raportti/index.md. Tämän avulla huomasin, että tiedostolla oli lukuoikeudet sekä ryhmän (group) että muiden käyttäjien (others) käyttöön, lisäksi käyttäjä nita oli ainoa, jolla oli täysi pääsy. Poistin ryhmän ja muiden käyttäjien lukuoikeudet komennolla chmod go-r /home/nita/raportti/index.md. 

<img width="349" alt="image" src="https://github.com/user-attachments/assets/4a426225-6d94-4883-846b-e89e77b8c2ac" />

## tehtävä d) 'howdy'

Tässä tehtävässä loin komennon nimeltä howdy, joka tulostaa ajankohtaista tietoa, kuten päivämäärän ja koneen osoitteen, kaikille käyttäjille riippumatta heidän työhakemistostaan.

<img width="332" alt="image" src="https://github.com/user-attachments/assets/3a21ce13-015b-4bcb-a3ac-a5fd040aa39c" />
<br>

<img width="263" alt="image" src="https://github.com/user-attachments/assets/aa4b584b-7fa9-4dae-92f7-7f0631a537c6" />
<br>

<img width="279" alt="image" src="https://github.com/user-attachments/assets/c4ffb2a1-4cf7-43bb-bc5b-0cae74350cd4" />
<br>

<img width="283" alt="image" src="https://github.com/user-attachments/assets/9adf6ba4-8f7d-408c-b79f-2b769d7919c5" />
<br>

<img width="268" alt="image" src="https://github.com/user-attachments/assets/6250a7d3-bd0c-4a7e-bbbe-67689a65d8b2" />
<br>

<img width="307" alt="image" src="https://github.com/user-attachments/assets/36d662d9-d33f-42df-b9c3-e53e4d7c07a7" />
<br>

<img width="201" alt="image" src="https://github.com/user-attachments/assets/ccbefa5f-20ea-481f-85d3-de98fa294662" />


## tehtävä e) Etusivu uusiksi

Tässä tehtävässä asensin Apache-web-palvelimen ja loin yritykselle "AI Kakone" kotisivun. Muutin tiedostojen omistajuuden ja oikeudet niin, että pystyin muokkaamaan sivua normaalilla käyttäjällä ilman sudo-oikeuksia. Kotisivu on nähtävissä Apache-palvelimen kautta koneen IP-osoitteella.

<img width="268" alt="image" src="https://github.com/user-attachments/assets/96aa98a9-a867-4b1c-8d83-ce9a3d91bf99" />
<br>

<img width="418" alt="image" src="https://github.com/user-attachments/assets/6eb0a6af-9c93-4539-a8dc-caf335b79d23" />
<br>

<img width="635" alt="image" src="https://github.com/user-attachments/assets/1960b215-e46b-4a06-ae29-2a6a9662ae8f" />
<br>

<img width="401" alt="image" src="https://github.com/user-attachments/assets/bae76eb0-3f2f-439f-b6f7-b4c28ad50d86" />
<br>

<img width="272" alt="image" src="https://github.com/user-attachments/assets/4a4617d7-dba9-4ea6-80e5-08bceb332092" />
<br>

Name based virtual host luominen ->

<img width="397" alt="image" src="https://github.com/user-attachments/assets/a26e8432-99c0-4178-a578-cd52a141d8c3" />
<br>

<img width="353" alt="image" src="https://github.com/user-attachments/assets/6f1205a3-acfc-428a-bb72-4e34862269ea" />
<br>

<img width="380" alt="image" src="https://github.com/user-attachments/assets/9fc716f8-2a72-4a64-8bb1-285280fc57e0" />
<br>

Name based virtual hostin käynnistys >

<img width="256" alt="image" src="https://github.com/user-attachments/assets/93bbb4a3-7c5f-493a-a77e-ca1c087b05a5" />
<br>

<img width="281" alt="image" src="https://github.com/user-attachments/assets/7c1cddd8-c296-4a85-96c5-3617324b6c8e" />

Verkkosivun luonti tavallisena käyttäjänä >

<img width="344" alt="image" src="https://github.com/user-attachments/assets/7b26a3b9-8136-4910-9e3a-b67f28d8b782" />
<br>

<img width="263" alt="image" src="https://github.com/user-attachments/assets/f819737e-6cbb-45d2-85da-2e74fe897738" />
<br>

<img width="466" alt="image" src="https://github.com/user-attachments/assets/5f4153d4-7f41-4315-93b6-00103e26315f" />
<br>

Korjataan Apachen käynnissä oleva sivu halutuksi > 

<img width="305" alt="image" src="https://github.com/user-attachments/assets/6ed24711-8f02-4909-b5b7-0a8712f3fcb9" />
<br>

<img width="299" alt="image" src="https://github.com/user-attachments/assets/dcf696cc-295e-4d04-8a36-ab5b0e2dab57" />

Oikeudet >

<img width="432" alt="image" src="https://github.com/user-attachments/assets/9fb6af38-9d87-49f2-bdb4-b7fdca18b554" />

## g) Salattua hallintaa 

Tässä tehtävässä tuli asentaa SSH-palvelin ja luoda uusi käyttäjä omalla nimelläni. Lisäksi minun piti automatisoida SSH-kirjautuminen julkisen avaimen menetelmällä, jotta voin kirjautua sisään ilman salasanaa. Kirjautuminen tuli testata käyttämällä localhost-osoitetta.

<img width="398" alt="image" src="https://github.com/user-attachments/assets/ee780ffc-cedb-4a36-9024-8abbf8350aff" />
<br>

<img width="397" alt="image" src="https://github.com/user-attachments/assets/a1c7b513-27f8-4fd9-ac73-42dc0db34a5a" />
<br>

<img width="322" alt="image" src="https://github.com/user-attachments/assets/aa3bd326-baed-4265-bc52-0f2dfe600024" />
<br>

<img width="230" alt="image" src="https://github.com/user-attachments/assets/21a704a7-0aa8-4c94-b60f-8e2ae37cb021" />
<br>

<img width="368" alt="image" src="https://github.com/user-attachments/assets/336aca87-a6d5-463e-81fc-9acf637de405" />
<br>

<img width="631" alt="image" src="https://github.com/user-attachments/assets/986052ad-1fde-4cd3-b7dc-8b3b7f9d749e" />
<br>

<img width="475" alt="image" src="https://github.com/user-attachments/assets/57bea028-9f2a-456b-8302-b685998e8ba6" />
<br>


Lähteet

https://github.com/Nitansivut/linux-course/blob/main/h1.md

https://github.com/Nitansivut/linux-course/blob/main/h2.md

https://github.com/Nitansivut/linux-course/blob/main/h3.md

https://github.com/Nitansivut/linux-course/blob/main/h4.md

https://github.com/Nitansivut/linux-course/blob/main/h5.md

https://github.com/Nitansivut/linux-course/blob/main/h1.md
https://github.com/juuliapurho/linux-course/blob/b7219ac8e3f8114dd74edca5f1d814a86ee3b481/h1-Oma-Linux.md
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
