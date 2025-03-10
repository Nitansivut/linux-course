# x) Komennot Linuxissa: Koska klikkaaminen on vain liian helppoa

## Komennot liikkumista varten

**pwd (Print working directory)**: Näyttää nykyisen työhakemiston, eli kertoo, missä hakemistossa työskennellään sillä hetkellä.

**ls (List)**: Näyttää ne tiedostot ja kansiot siinä hakemistossa, jossa ollaan sillä hetkellä. Tätä komentoa voi käyttää, jos esimerkiksi etsii tiedostoa ja saa "No such file or directory" -virheen, sillä silloin voi tarkistaa, onko sellaista tiedostoa edes olemassa. 

**cd (Change Directory)**: Auttaa siirtymään kansiosta toiseen. Jos komennon perään ei lisätä tietoa kansiosta tai tiedostosta, johon halutaan siirtyä (esim. cd kissakansio), komento vie automaattisesti käyttäjän kotikansioon.

**less**: Näyttää tiedoston sisällön ruutuun pienemmissä osissa. Tämä komento on hyödyllinen suurten tekstitiedostojen käsittelyssä, koska se ei lataa koko tiedostoa kerralla, vaan käsittelee sen sivu kerrallaan. Komento sisältää interaktiivisia ominaisuuksia, jotka mahdollistavat tiedoston selaamisen eteen- ja taaksepäin.

## Komennot tiedostojen muokkausta varten

**nano**: komentorivipohjainen tekstieditori, joka on suunniteltu konfiguraatiotiedostojen, skriptien ja muiden tekstipohjaisten asiakirjojen muokkaamiseen. 

**mkdir (Make directory)**: Luodaan uusi kansio (hakemisto).

**mv (Move)**: Siirretään tai nimetään tiedostoja ja kansioita. Ensimmäinen argumentti komennon jälkeen on tiedosto tai kansio, jota halutaan siirtää tai nimetä. Jos toisen argumentin perässä on kansio, tiedosto siirretään sinne. Jos toisen argumentin perässä on uusi tiedostonimi, tiedosto tai kansio nimetään uudelleen.

**cp (Copy)**: Kopioidaan tiedostoja ja kansioita. Jos komennon perään lisätään -r (rekursiivinen), kopioidaan myös kansion sisältö alihakemistoineen ja tiedostoineen. Esimerkiksi komento $ cp -r ORIGINAL COPY kopioi ORIGINAL-kansion (ja sen sisällön) COPY-kansioon.

**rmdir (Remove directory)**: Poistaa tyhjän hakemiston.

**rm (Remove)**: Poistaa tiedostoja, kansioita ja linkkejä tiedostojärjestelmästä, mutta ei poista kansioita ilman -r-optiota, ja poistetut tiedostot eivät ole palautettavissa.

## SHH etähallinta

**shh (Secure Shell Protocol)**: Käytetään turvalliseen etäyhteyteen toiseen tietokoneeseen tai palvelimeen. Se mahdollistaa tiedostojen siirron ja komentoja suorittamisen etänä salaamalla yhteyden. Omalle koneelle voidaan palata komennolla "exit".

**scp (Secure Copy)**: Kopioidaan tiedostoja tai kansioita turvallisesti omalta koneelta etäkoneelle tai toisinpäin SSH-yhteyden kautta.

## Komentohistorian hyödyntäminen

**Tabulaattori-näppäin**: Täydentää tiedostojen ja kansioiden nimet osan perusteella, jonka käyttäjä on kirjoittanut, ja etsii kaikki vaihtoehdot, jotka alkavat samalla tekstillä. Jos vain yksi vaihtoehto löytyy, se täyttyy automaattisesti.

**Nuoli ylös-näppäin**: Näyttää edellisen komennon.

**Vasen ja oikea nuolinäppäin**: Siirtävät kursoria vasemmalle tai oikealle kirjoitettaessa komentoa.

**Ctrl + R**: Etsii ja näyttää aiemmin suoritetut komennot kommentohistoriasta.

## Tärkeät hakemistot
**/**: Juurikansio

**/home/**: Sisältää kaikkien käyttäjien kotihakemistot. Esimerkiksi /home/tero/ on käyttäjän "tero" kotihakemisto. Ainoa paikka, johon käyttäjä "tero" voi tallentaa pysyvästi tietoja.

**/etc/**: Kaikki järjestelmän laajuiset asetukset. 

**/var/log/**: Järjestelmän laajuiset lokit.

**/media/**: Näkyvät irrotettavat laitteet, kuten USB-muistitikut ja CD-levyt, kun ne liitetään tietokoneeseen.

## Hallintakomennot

**sudo (Super user do!)**: Antaa käyttäjälle tilapäisen järjestelmänvalvojan oikeudet komentojen suorittamiseen.

**sudo apt-get update**: päivittää saatavilla olevien pakettien luettelon.

**apt-cache search**: Etsii ohjelmistoa avainsanojen perusteella ilman, että sudo-oikeuksia tarvitaan.

---

Lähteet:

Geeksforgeeks, 2025a. Luettavissa: https://www.geeksforgeeks.org/cd-command-in-linux-with-examples/. Luettu: 23.1.2025.

Geeksforgeeks. 2024b. Luettavissa: https://www.geeksforgeeks.org/rm-command-linux-examples/. Luettu: 23.1.2025. 

Jkorpela. s.a. Luettavissa: https://jkorpela.fi/unix/7.4.html. Luettu: 23.1.2025. 

Layton. 2023. Luettavissa: https://www.pluralsight.com/resources/blog/cloud/linux-commands-for-beginners-sudo. Luettu: 23.1.2025. 

Penmetsa. 2024. Luettavissa: https://medium.com/itversity/mastering-the-mv-command-6c5cb49d005d. Luettu: 23.1.2025. 

Phoenixnap, 2022a. Luettavissa: https://phoenixnap.com/kb/less-command-in-linux. Luettu 23.1.2025. 

Phoenixnap. 2024b. Luettavissa: https://phoenixnap.com/kb/use-nano-text-editor-commands-linux. Luettu: 23.1.2025.

SHH.com. s.aa. Luettavissa: https://www.ssh.com/academy/ssh/command#ssh-command-in-linux. Luettu: 23.1.2025. 

SHH.com. s.ab. Luettavissa: https://www.ssh.com/academy/ssh/scp. Luettu: 23.1.2025.

Terokarvinen, s.a. Luettavissa: https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited. Luettu: 23.1.2025.

---

# a) Micro-editorin asennus

Asensin micro-editorin virtuaalikoneessani siirtymällä terminaaliin ja suorittamalla ensin komennon sudo apt-get update, joka päivitti pakettien luettelon.

<img width="590" alt="image" src="https://github.com/user-attachments/assets/0abe080b-d8b7-4e02-b8e0-6d68eff93eb1" />

Seuraavaksi asensin micro-editorin suorittamalla komennon sudo apt-get install micro ja vahvistamalla asennuksen painamalla näppäimistöstä y-kirjainta.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/27151bdf-3edd-4313-9c3d-baf9e508ece9" />

Varmistin, että micro-editori oli asennettu oikein suorittamalla komennon micro --version.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/88954bdd-8b68-4fdb-9113-09095fc4e35a" />

# b) Kolmen uuden komentoriviohjelman asennus ja testaus

Asensin kolme valitsemaani komentoriviohjelmaa: htop, nmap sekä cowsay. Käytin niiden samanaikaiseen asentamiseen yhtä komentoa: sudo apt-get update && sudo apt-get install -y htop nmap cowsay. 

Htop on komentorivityökalu, joka tarjoaa interaktiivisen ja värillisen näkymän järjestelmän resursseista ja prosesseista reaaliajassa. Testasin sitä kirjoittamalla komentoriville htop.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/da2b6ab0-f2b1-4a6a-a314-9d4eb3efc953" />

Nmap:ia käytetään verkon tutkimiseen ja tietoturva-auditointeihin tarjoamalla reaaliaikaista tietoa verkosta, aktiivisista IP-osoitteista, avoimista porteista, live-isännistä sekä suorittamalla portti-, käyttöjärjestelmä- ja isäntäskannauksia. Tein testauksen kirjoittamalla komentoriville "nmap" ja käyttämällä yleisesti käytettyä IP-osoitetta 192.168.0.1.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/e4357b5d-6492-4f51-ad45-066543b7a583" />

Cowsay-komento luo tekstipohjaisen hahmon, joka "puhuu" syötetyn tekstin puhekuplassa. Kokeilin komentoa kirjoittamalla ensin "cowsay" komentoriville ja sen jälkeen syöttämällä tekstiksi 'Hei sinä siellä!'.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/39afed96-b98d-42f6-b9c2-4e0264c50a50" />

---

Lähteet: 

Geeksforgeeks. 2024a. Luettavissa: https://www.geeksforgeeks.org/htop-command-in-linux-with-examples/. Luettu: 23.1.2025. 

Geeksforgeeks. 2024b. Luettavissa: https://www.geeksforgeeks.org/nmap-command-in-linux-with-examples/. Luettu: 23.1.2025.

Ioflood. 2023. Luettavissa: https://ioflood.com/blog/cowsay-linux-command/. Luettu: 23.1.2025. 

---

# c) Tärkeät hakemistot Linux terminaalissa näytettynä

## Juurihakemisto

<img width="500" alt="image" src="https://github.com/user-attachments/assets/4dd23d5e-2145-44d3-a0ac-0a45b7639092" />

## Kotihakemisto

<img width="500" alt="image" src="https://github.com/user-attachments/assets/779c76fa-95b0-4590-8111-1c166981ec34" />

## Käyttäjäkohtainen hakemisto

<img width="500" alt="image" src="https://github.com/user-attachments/assets/ac643d5e-840a-4e5b-982b-f45d9ca8b9dd" />

## Järjestelmänlaajuiset asetukset

<img width="500" alt="image" src="https://github.com/user-attachments/assets/9a21ba9d-c23b-4965-a471-943ad8a8a395" />
<br>


<img width="500" alt="image" src="https://github.com/user-attachments/assets/ab31ff9a-8e3b-49f8-9e70-4a61554b65b0" />

## Irrotettavat tallennusvälineet

/media/-kansio oli tyhjä, koska järjestelmääni ei ollut liitetty irrotettavia tallennusvälineitä kyseisellä hetkellä.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/ae6d3091-2e5e-4a94-8058-d866b70a8ef2" />

## Järjestelmän lokitiedot

En löytänyt /var/log/syslog-tiedostoa komennolla ls /var/log/syslog. Osaisiko kukaan kertoa, että miksi?

<img width="500" alt="image" src="https://github.com/user-attachments/assets/f2a2bbdb-045d-4443-8aa0-0632667c8a58" />

# d) Grep-komento

Grep (Global Regular Expression Print) on komentokäsky, jonka avulla voi etsiä tiettyjä sanoja tai lauseita tiedostoista. Grepiä voidaan käyttää myös säännöllisten lausekkeiden kanssa, jotka mahdollistavat monimutkaisempien tekstien hakemisen.

Tehtävänä oli testata parisen kuvaavaa esimerkkiä grep-komennon käytöstä. Aluksi loin testitiedoston nano-editorilla ja lisäsin siihen tarinan, jonka luotin chatgpt:ltä.

<img width="554" alt="image" src="https://github.com/user-attachments/assets/4f452003-f937-490d-a070-830dcfccb22f" />

Ensimmäiseksi testasin grep-komentoa hakusanalla "Liisa", joka löytää kaikki rivit, joissa esiintyy kyseinen hakusana.

<img width="551" alt="image" src="https://github.com/user-attachments/assets/7d76d53b-e783-45a7-9101-b4c07424c522" />

Sen jälkeen kokeilin -n-optiota grep-komennossa, joka näyttää rivinumeroita, joilla hakusana esiintyy tiedostossa.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/c8e88bfb-61a5-4d21-9e82-b010a111fb93" />

---

Lähteet: 

Cyberciti. s.a. Luettavissa: https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/. Luettu: 23.1.2025. 

Digital Ocean. s.a. Luettavissa: https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix. Luettu: 24.1.2025.

---

# e) Putken (Pipe) käyttö komennoissa 

Putki (pipe) on työkalu, joka yhdistää kaksi komentoa niin, että ensimmäisen komennon tulos ohjataan suoraan toisen komennon syötteeksi. Esimerkiksi komennolla ls | less listataan kaikki tiedostot ja hakemistot, ja tämä lista ohjataan less-komennolle, joka näyttää sen sivu kerrallaan. 

<img width="500" alt="image" src="https://github.com/user-attachments/assets/aaa1acf2-26b8-4487-b42f-85874c2b3f15" />

---

Lähteet:

Geeksforgeeks. s.a. 2024. Luettavissa: https://www.geeksforgeeks.org/piping-in-unix-or-linux/. Luettu: 26.1.2025. 

---

# f) Koneen laitteiston tiedot

Aluksi asensin lshw-komennon suorittamalla komennot sudo apt update ja sudo apt install lshw. Tämän jälkeen tarkastelin koneeni laitteistotiedot komennolla sudo lshw -short -sanitize.

Tuloksista käy ilmi, että kone toimii VirtualBox-virtuaalikoneessa, jossa on AMD Ryzen 7 4700U -prosessori ja 4 GB RAM -muistia. Tallennustilana on 21 GB virtuaalikovalevy, joka on jaettu EXT4-tiedostojärjestelmään ja Linux swap -osioon. Virtuaalikoneessa on emuloitu Gigabit Ethernet -verkkokortti ja SVGA II Adapter -näytönohjain, jotka mahdollistavat verkkoyhteyden ja grafiikan toiston. Lisäksi koneessa on käytössä AC'97 Audio Controller äänentoistoon ja USB-portit erilaisten laitteiden liittämistä varten. Virtuaalikoneessa on myös CD-ROM-asema ja muita emuloituja laitteita.

---

# Tehtävissä a) - c) käytetty ympäristö

Kannettava tietokone

MalliVivoBook_ASUSLaptop X421IA_M433IA

Suoritin: AMD Ryzen 7 4700U with Radeon Graphics

RAM: 8 Gt

SSD-levyn koko: 476,07 Gt, josta vapaata tilaa: 357,07 Gt

Järjestelmätyyppi: 64-bittinen käyttöjärjestelmä, x64-suoritin

Käyttöjärjestelmä: Windows 11 Home

Virtuaalikone

Virtualisointi: Oracle Virtualbox versio 7.1.0 r164728 (Qt6.5.3)

Muisti: 4000 MB

CPU: 2

Virtuaalikovalevyn koko: 20.00 GB

Käyttöjärjestelmä: Debian GNU/Linux 12 (bookworm)
