# X) Raportin kirjoittaminen -muistiinpanot

### Hyvä pohja raportille
- Raportoidaan täsmällisesti, mitä tehtiin ja mitä tapahtui.
- Kirjoitetaan raporttia reaaliaikaisesti tehtävien aikana.
- Pidetään muistiinpanoja jatkuvasti ajatusten selkeyttämiseksi ja ajan säästämiseksi.
- Käytetään raportteja pohjana ohjeiden laatimisessa.

### Raportin oltava toistettava
- Dokumentoidaan tehtävät ja ympäristö niin, että sama tulos voidaan saavuttaa uudelleen.
- Raportoidaan ympäristö: ajankohta, paikka, käytetyt laitteet ja muut olennaiset tiedot.

### Raportin oltava täsmällinen
- Kirjataan tarkasti, mitä komentoja käytettiin ja mitä toimenpiteitä tehtiin.
- Merkitään kellonajat työvaiheille ja raportoidaan odottamattomat tulokset.
- Raportoidaan onnistumiset ja epäonnistumiset sekä miten ne todettiin.
- Käytetään mennyttä aikamuotoa, esimerkiksi “valitsin ‘tyhjennä’”.

### Raportin oltava helppolukuinen
- Käytetään väliotsikoita ja huolehditaan oikeinkirjoituksesta.
- Sovitetaan kirjoitustyyli julkaisukanavaan.
- Halutessa lisätään lyhyt tiivistelmä raportin alkuun.

### Raportissa viitattava lähteisiin
- Käytetään viittauksia akateemisten käytäntöjen mukaisesti.
- Ilmoitetaan kirjoittajat, päivämäärät ja lähteiden osoitteet.
- Vakiotekstejä

### Lisätään tarvittaessa lisenssiteksti, esimerkiksi:
- “Tätä dokumenttia saa kopioida ja muokata GNU General Public License (versio 2 tai uudempi) mukaisesti.”
- Käytetään GPL-lisenssiä, jos lisenssi valitaan.

### Pahoja mokia
- Raportoidaan vain oikeasti tehdyt testit – ei sepitetä.
- Ilmoitetaan aina lähteet – ei plagioida.
- Käytetään vain luvallisia kuvia ja ilmoitetaan niiden lähteet.

### Free Software Foundation -muistiinpanot

### Free Software tarkoitus ja määritelmä
- Ohjelmisto, joka kunnioittaa käyttäjän vapautta ja yhteisöä.
- Käyttäjillä on vapaus käyttää, kopioida, jakaa, tutkia, muuttaa ja parantaa ohjelmistoa.
- Ohjelmistosta voi maksaa tai voi saada sen ilmaiseksi, mutta sen täytyy säilyttää käyttäjien vapaudet.
- Määritelmä perustuu neljään keskeiseen vapauteen: käyttää, tutkia, jakaa ja muokata ohjelmistoa.

### Neljä olennaista vapautta
- Vapaus 0: Vapaus käyttää ohjelmistoa haluamallasi tavalla.
- Vapaus 1: Vapaus tutkia ja muokata ohjelmistoa.
- Vapaus 2: Vapaus jakaa kopioita.
- Vapaus 3: Vapaus jakaa muutettuja versioita

### Copyleft ja sen merkitys
- Copyleft suojaa vapautta varmistamalla, ettei ohjelmistoa ja sen muutoksia rajoiteta.
- Copyleft varmistaa, että ohjelmistoa ja sen muutoksia voi jakaa ja muokata vapaasti.

### Vienti ja oikeudelliset näkökohdat
- Vapaan ohjelmiston lisenssi ei saa estää ohjelmiston jakamista tai käyttöä kansainvälisesti vientirajoitusten takia.
- Vapauksien on oltava pysyviä ja peruuttamattomia ilman syytä.
- Lisenssin ei tule sallia kehittäjien peruuttaa vapauksia ilman käyttäjän virheitä.

### Sopimusperusteiset lisenssit ja käytännön näkökohdat
- Sopimusperusteiset lisenssit voivat rajoittaa enemmän kuin tekijänoikeusperusteiset.
- Sopimuksissa voidaan asettaa lisärajoituksia, jotka tekevät ohjelmistosta ei-vapaan.
- Vapaan ohjelmiston määritelmä perustuu neljään vapauteen, ja lisenssejä arvioidaan niiden perusteella.

---

Lähteet:

https://terokarvinen.com/2006/raportin-kirjoittaminen-4/

---

# a) Linuxin asennus virtuaalikoneeseen

### Ympäristötiedot:

Asensin virtuaalikoneen ASUS-kannettavalleni, jossa on Windows 11 Pro (64-bittinen, versio 23H2, koontiversio 22631.4751) ja virtuaalikoneohjelmistona Oracle VM VirtualBox. Alla kerron tarkemmin vaihe vaiheelta, miten tämän tein.

Latasin ensin ISO-tiedoston, joka löytyy [täältä](https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/) 

<img width="500" alt="image" src="https://github.com/user-attachments/assets/4c0981dd-6ab4-4145-a88f-493748d6f055" />

Seuraavaksi latasin Virtual Boxin: 

<img width="500" alt="image" src="https://github.com/user-attachments/assets/fc66ce48-ac5d-44e8-9c1c-16c77b393d54" />

Loin uuden virtuaalikoneen VirtualBoxissa, valitsin "Skip Unattended Install", asetukseksi Linux, version Debian (64-bit), varasin 4000 MB muistia ja loin virtuaalisen kiintolevyn.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/396c8ec8-c5fe-4560-9f70-0c4f3109b3b2" />

Opettajan ohjeissa kohta, "Create Virtual hard disk" aiheutti minulle hieman harmaita hiuksia, kun tehtävänannossa lukee, että tiedoston koon pitäisi olla 60GB, mutta kuvankaappauksessa näkyi 20.00GB. Valitsin virtuaalisen kovalevyn jo virtuaalikoneen luontivaiheessa, eikä siinä pitänyt erikseen määritellä mitään kokoja yms. Tarkistin, että tiedoston kokoni on 20.00GB, kuten opettajan kuvankaappauksessa, joten en muuttanut sitä enää. 

Seuraavaksi käynnistin virtuaalikoneen, ja sen jälkeen työpöytä avautui.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/f4ea4d3e-7488-4ae5-ab9b-00f4dbf4e028" />

Testasin, että verkkoyhteys, hiiri, näppäimistö ja muut laitteet toimivat oikein. Käytin Firefox-selainta ja hain terokarvinen.com-sivustoa varmistaakseni, että kaikki toimi odotetusti.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/8813d68e-b7b3-42ed-b0f7-2ce060b5ea67" />

Seuraavaksi käynnistin Debianin asennuksen virtuaalikoneessa. 

<img width="500" alt="image" src="https://github.com/user-attachments/assets/6e3bfc95-de64-4303-ab5f-3e26c95f0f08" />

Sitten kirjauduin aiemmin asennuksessa luomillani tunnuksilla sisään ja testasin Firefoxilla, että netti toimii. Sitten avasin terminaalin, päivitin saatavilla olevan ohjelmiston luettelon, suoritin järjestelmäpäivityksen, asensin palomuurin ja käynnistin koneen uudelleen.

Lopuksi tutustuin Applications -menuun ja selailin TeroKarvinen.com-.

---

Lähteet:

Chatgbt. Käytetty promptia: Voisitko auttaa minua asentamaan Linuxin virtuaalikoneeseen? Tarvitsen ohjeet siihen, ja haluaisin tehdä uuden virtuaalikoneen raporttia varten, vaikka olisin aiemmin asentanut Linuxin virtuaalikoneeseen. Miten aloitan ja mitä vaiheita minun tulisi seurata?. Haettu 15.1.2025.

---
