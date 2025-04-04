# x) Lets encrypt - How it works -kirjoituksen muistiinpanot

- Let’s Encrypt ja ACME-protokolla mahdollistavat automaattisen HTTPS-varmenteen hankinnan ilman ihmisen väliintuloa verkkopalvelimelle.
- Varmenteen hankinnan vaiheet:
  - Palvelimen on todistettava, että se hallitsee verkkotunnusta.
  - Kun hallinta on vahvistettu, palvelin voi pyytää, uusia ja perua varmenteita automaattisesti.
- Verkkotunnuksen hallinnan todistaminen:
  - Palvelimen ylläpitäjä tunnistetaan julkisella avaimella.
  - Ensimmäisellä käyttökerralla palvelinohjelmisto (agentti) luo avainparin ja todistaa verkkotunnuksen hallinnan varmentajalle (CA).
- CA antaa haasteita, joilla palvelin voi todistaa hallinnan, esim.:
  - Lisäämällä tietyn DNS-tietueen verkkotunnukseen.
  - Luomalla tietyn tiedoston palvelimen verkkosivulle.
- Palvelin suorittaa yhden haasteista ja allekirjoittaa CA:n antaman nonce-arvon yksityisellä avaimellaan.
- CA tarkistaa haasteen suorittamisen ja myöntää palvelimelle oikeuden hallita verkkotunnuksen varmenteita.
- Sertifikaatin (varmenteen) myöntäminen:
  - Kun palvelin on valtuutettu, se voi pyytää varmenteen.
  - Palvelin lähettää varmenteen allekirjoituspyynnön (CSR) CA:lle.
  - CA tarkistaa pyynnön, myöntää varmenteen ja tallentaa sen julkisiin Certificate Transparency -lokitietoihin.
- Sertifikaatin peruminen:
  - Jos varmenne täytyy perua, palvelin lähettää allekirjoitetun perumispyynnön CA:lle.
  - CA tarkistaa pyynnön ja julkaisee peruutustiedon, jolloin selain ei enää hyväksy sertifikaattia.

---
Lähteet

https://letsencrypt.org/how-it-works/

---

# x) Using an existing, running web server -kirjoituksen muistiinpanot

- Jos palvelin käyttää jo porttia 80, Let’s Encrypt -varmenteen hankkimiseksi käytettävä --http-vaihtoehto vaatii myös --http.webroot-vaihtoehdon.
- Mitä --http.webroot tekee?
    - Se ei käynnistä uutta palvelinta, vaan yksinkertaisesti luo ja tallentaa haasteen tunnustiedoston palvelimen tiedostojärjestelmään.
    - Tämä tiedosto sisältää HTTP-01-haasteen tunnuksen, joka tallennetaan hakemistoon .well-known/acme-challenge.
- Miksi tämä hakemisto on tärkeä?
    - Hakemiston täytyy olla julkisesti saatavilla verkkotunnuksen juurena (/), jotta Let’s Encrypt -palvelin voi pyytää haasteen tiedoston ja vahvistaa palvelimen hallinnan.
    - Esimerkiksi, jos haasteen tiedosto luodaan /path/to/webroot/.well-known/acme-challenge/, se tulisi olla saavutettavissa URL-osoitteesta: http://example.com/.well-known/acme-challenge/<haasteen_tiedosto>
- Mitä tehdä, jos hakemisto ei ole julkisesti saatavilla?
    - Palvelimen täytyy uudelleenohjata tai uudelleenkirjoittaa pyynnöt tähän hakemistoon.
    - Tämä voidaan tehdä esimerkiksi verkkopalvelimen asetuksissa (Apache, Nginx, jne.) lisäämällä sääntö, joka ohjaa kaikki .well-known/acme-challenge -polun pyynnöt oikeaan hakemistoon.
- Esimerkki: Lego-työkalun käyttö varmenteen hakemiseen
    - Jos käytössä on nykyinen web-palvelin portilla 80, haasteen voi suorittaa seuraavalla komennolla: lego --accept-tos --email you@example.com --http --http.webroot /path/to/webroot --domains example.com run

---

Lähteet

https://go-acme.github.io/lego/usage/cli/obtain-a-certificate/index.html#using-an-existing-running-web-server

---

# x) Basic configuration example -muistiinpanot

SSL-konfiguraatiosi tarvitsee vähintään seuraavat direktiivit:

<img width="296" alt="image" src="https://github.com/user-attachments/assets/f991846a-373b-4063-b46a-d69154e3434a" />

LoadModule ssl_module modules/mod_ssl.so = Tämä komento lataa SSL-moduulin Apacheen. SSL-moduuli on se, joka mahdollistaa salauksen, joten ilman sitä HTTPS ei toimi.

Listen 443 = Tällä määrätään, että Apache kuuntelee porttia 443. Portti 443 on se, jota käytetään HTTPS-yhteyksissä (salaus käytössä).

*<VirtualHost : 443> = Tässä määrätään, että seuraavat asetukset koskevat kaikkea liikennettä, joka menee porttiin 443 (HTTPS). Käytännössä tämä tarkoittaa, että SSL-asetukset otetaan käyttöön.
 
ServerName = Tässä määritellään verkkosivun nimi (domain), jota SSL-konfiguraatio käyttää. Tämä nimi pitäisi olla sama kuin se, joka on SSL-sertifikaatissa.

SSLEngine = Tämä komento ottaa SSL:n käyttöön, eli kertoo palvelimelle, että se alkaa käyttää salausta.

SSLCertificateFile =  Tässä määritellään SSL-sertifikaatin sijainti. 

SSLCertificateKeyFile = Tässä määritellään yksityisen avaimen sijainti. Tämä avain on tärkeä, koska sitä tarvitaan, kun palvelin purkaa salattuja tietoja. Polku pitää vaihtaa oman avaimen polkuun.

< / VirtualHost > = Tämä rivin sulkee VirtualHost-lohkon, joka määritteli kaikki yllä olevat asetukset HTTPS-yhteyksiä varten.

---

Lähteet

https://httpd.apache.org/docs/2.4/ssl/ssl_howto.html#configexample
https://stackoverflow.com/questions/46542968/how-to-install-ssl-certificate-in-apache-server-in-ubuntu

---

# a) Ilmaisen TLS-sertifikaatin hankkiminen ja asentaminen Let's Encryptilta


## Vaihe 1: Aloitin tehtävän kirjautumalla palvelimelle SHH:n kautta. 

<img width="296" alt="image" src="https://github.com/user-attachments/assets/c7372cf4-667e-4ba5-89d8-db4db11b69b3" />

## Vaihe 2: Päivitin järjestelmän ja asensin Certbotin

<img width="301" alt="image" src="https://github.com/user-attachments/assets/3a275a79-5666-4672-98f2-f4a934d91822" />

Asensin myös lisämoduulin Chatgbt:n suosituksesta.

<img width="365" alt="image" src="https://github.com/user-attachments/assets/0af435d9-5299-4000-9003-4548140037b1" />

## Vaihe 3: Asetin DNS-tietueet osoittamaan palvelimeni IP-osoitteeseen (94.237.18.62) viime viikolla, ja nyt vain varmistin, että ne ovat edelleen oikein.

<img width="273" alt="image" src="https://github.com/user-attachments/assets/81a98d9a-c14e-47b9-a8e8-86a16a10c4f4" />
<br>


<img width="365" alt="image" src="https://github.com/user-attachments/assets/3aaaae7d-a394-4045-b7f9-bdfd8908ab92" />

## Vaihe 4: TLS-sertifikaatin asentaminen

<img width="418" alt="image" src="https://github.com/user-attachments/assets/86527ef5-ee05-4ac4-836a-d991ca8dd13e" />

Painoin "y" kirjainta kaikissa kodissa, joissa pyydettiin y/no vastausta.

## Vaihe 5: Let's Encryptin sertifikaatit ovat voimassa 90 päivää, joten laitoin sertifikaatin uudistumaan automaattisesti.

Valitsin nano editorin ja laitoin sertifikaatin usiutumaan joka päivä klo 03:00.

<img width="309" alt="image" src="https://github.com/user-attachments/assets/18b372b9-410f-49cb-8d52-72c65eccbdda" />
<br>


<img width="407" alt="image" src="https://github.com/user-attachments/assets/ccb9279b-0918-4160-8272-f556bb9a36c2" />
<br>


Tallensin tiedoston painamalla Ctrl + O ja sitten Enter.

## Vaihe 6: Koitin testata, että HTTPS toimii selaimella, mutta sivu näytti, että siihen ei saada yhteyttä. Sitten koitin uudelleen Certbot-komentoa ja luin tarkemmin sen tulosteen.

<img width="497" alt="image" src="https://github.com/user-attachments/assets/dbc36250-9a30-4a43-802c-17eb79d87939" />

Tarkistin DNS-asetukset, palomuurin ja Apache-määritykset, enkä löytänyt ongelman syytä. Seuraavaksi keskityin .htaccess-tiedostoon ja tiedostojärjestelmän oikeuksiin.

.htaccess-tiedosto:Varmistin, että .htaccess-tiedosto ei estä pääsyä hakemistoon /.well-known/acme-challenge/.
Testatakseni tämän, nimesin .htaccess-tiedoston väliaikaisesti uudelleen seuraavalla komennolla:

sudo mv /home/nita/public_sites/nitaarifi.com/.htaccess /home/nita/public_sites/nitaarifi.com/.htaccess_old

Tämän jälkeen ajoin Certbotin uudelleen komennolla: sudo certbot --apache -d nitaarifi.com -d www.nitaarifi.com.

Tämän perusteella tutkin tiedoston sisältöä ja muokkasin sitä sallimaan pääsyn hakemistoon /.well-known/acme-challenge/. Aloitin varmistamalla, että .htaccess-tiedosto ei estä pääsyä hakemistoon /.well-known/acme-challenge/.Testatakseni tämän, nimesin .htaccess-tiedoston väliaikaisesti uudelleen seuraavalla komennolla: 

<img width="497" alt="image" src="https://github.com/user-attachments/assets/6fd29bdd-e024-48c8-8d33-9dada5cb76bf" />

Sitten suoritin Certbotin uudelleen, mutta ongelma jatkui. 

Mikä voisi olla ongelman syy?

## Päivitetty 9.3. 

Tutkimme opettajan ja muutaman oppilaan kanssa, miksi en saanut tätä tehtävää toimimaan tiistain 4.3. luennolla. Emme kuitenkaan löytäneet syytä yhdessä, joten opettaja suositteli aloittamaan alusta uudella etäpalvelimella.

Jotta ehtisin tehdä tämän viikon tehtävät ennen tiistain 11.3. luentoa, en pystynyt raportoimaan jokaista vaihetta yksityiskohtaisesti. Kerron siis tiivistetysti, mitä tein.

Ostin uuden palvelimen Upcloudista ja loin siihen uudet SSH-avaimet. Nyt pääsen kirjautumaan etäpalvelimelleni komennolla sudo nita@94.237.37.137.

Koska minulla on niin vähän aikaa ja paljon tehtävää, päätin tehdä seuraavat vaiheet hyödyntäen luokkalaisen raportteja tehtävistä [H4](https://github.com/juuliapurho/linux-course/blob/b7219ac8e3f8114dd74edca5f1d814a86ee3b481/h4-Maailma-kuulee.md), [H5](https://github.com/juuliapurho/linux-course/blob/main/h5-Nimek%C3%A4s.md) ja [H6](https://github.com/juuliapurho/linux-course/blob/main/h6-Salataampa.md). 

Tehtävien teko onnistui, ja testasin samalla, kuinka hyvin raportti ohjasi tehtävien suorittamista. Propsit luokkalaiselle hyvien raporttien teosta – niiden avulla sain tehtävät tehtyä onnistuneesti!

Raportoin tässä kuitenkin ainoastaan H6 a) tehtävän teosta. 

Hankin ja asensin palvelimelleni ilmaisen TLS-sertifikaatin Let's Encryptiltä. Kuten aiemmin mainitsin, hyödynsin tehtävän suorittamisessa luokkalaiseni raporttia ohjeistuksena. Tein ensin tehtävän ja aloitin vasta sen jälkeen raportoinnin. Tämän vuoksi kuvankaappauksissa näkyvät history-komennolla haetut aiemmin käyttämäni komennot.

Aloitin tehtävän käynnistämällä virtuaalikoneeni ja muodostamalla SSH-yhteyden virtuaalipalvelimelleni. Suoritin terminaalissa komennon sudo nita@94.237.37.137 ja syötin salasanani. 

<img width="406" alt="uusietäpalvelin" src="https://github.com/user-attachments/assets/40a29c0f-9b5f-4a8d-821b-e869b26c29d9" />

Käynnistin Apachen uudelleen suorittamalla komennon sudo systemctl restart apache2 ja syöttämällä salasanani.

Tämän jälkeen testasin sivustoni toimivuutta avaamalla verkkoselaimen ja kirjoittamalla osoitekenttään nitaarifi.com – sivusto toimi normaalisti.

Seuraavaksi kokeilin hakea sivustoa käyttämällä https://nitaarifi.com, mutta kuten odotettua, tämä ei toiminut, koska en ollut vielä asentanut TLS-sertifikaattia.

<img width="379" alt="restartapache" src="https://github.com/user-attachments/assets/22f504de-533d-45cb-af3f-ee80d28b4b56" />

Seuraavaksi päivitin kaikki saatavilla olevat päivitykset suorittamalla ensin komennon sudo apt-get update ja sitten sudo apt-get upgrade. Asensin tämän jälkeen lego-ohjelman komennolla sudo apt-get install lego.

<img width="316" alt="getupdate" src="https://github.com/user-attachments/assets/7721e5ee-3032-4cff-a9ee-a0308d68608a" />

<img width="286" alt="getupgrade" src="https://github.com/user-attachments/assets/99c94eef-c81e-4dca-906a-b0f38f5a1b65" />

<img width="310" alt="installlego" src="https://github.com/user-attachments/assets/7494b2dc-06f3-4dbb-95fd-cbc6d86c12f8" />

Seuraavaksi hankin sertifikaatin käyttämällä alla olevassa kuvassa näkyvää pitkää komentoa. Sertifikaatti haettiin testipalvelimelta (staging), mikä määritettiin --server-parametrin arvoksi. 

<img width="575" alt="staging" src="https://github.com/user-attachments/assets/12aab0a8-7452-4852-96a6-08dd7ef31ce6" />

Viimeisellä rivillä näkyi, että sertifikaatin haku onnistui.

<img width="404" alt="image" src="https://github.com/user-attachments/assets/4d34ec42-c8c1-4167-ad0f-4effafce21d3" />

Sitten piti poistaa --path-parametrissa määritetty kansio /home/nita/lego/certificates, johon oli tallentunut testitietoja. Poistin sen suorittamalla komennon rm -r /home/nita/lego/certificates, joka poisti kansion ja sen sisällön. Tämän jälkeen tarkistin vielä lego-kansion sisällön komennolla ls /home/nita/lego, ja kansio oli tyhjä.

<img width="233" alt="409410" src="https://github.com/user-attachments/assets/05528821-5805-4569-a289-74241f571c78" />

Sitten hain sertifikaatin oikealta palvelimelta. Poistin aiemmin testipalvelimelle suorittamastani komennosta --server-parametrin ja suoritin sitten alla olevan kuvan mukaisen komennon.

<img width="574" alt="oikeapalvelin" src="https://github.com/user-attachments/assets/4e7213fe-520b-4a54-bb85-5c2fd35dd87b" />

<img width="395" alt="onnistuicert" src="https://github.com/user-attachments/assets/4186d7ec-e847-4120-9d1f-94680d731373" />

Seuraavaksi otin sertifikaatin käyttöön name based isäntäasetuksissa eli muokkasin konfiguraatiotiedostoa. Siirryin ensin hakemistoon komennolla cd /etc/apache2/sites-available ja sen jälkeen avasin konfiguraatiotiedoston komennolla sudoedit nitaarifi.com.conf. Sen jälkeen muutin konfiguraatiotiedostoni alla olevan kuvan mukaisesti.

<img width="443" alt="123" src="https://github.com/user-attachments/assets/0dc16fa3-44df-4812-aeff-54b155f601c3" />

Konfiguraatiotiedostoni näytti alla olevan kuvan mukaiselta.

<img width="442" alt="virtualhost443" src="https://github.com/user-attachments/assets/b310d33f-54c4-4761-933d-6348cf42f7d0" />

Varmistin, että konfiguraatiotiedostoon merkitsemäni sertifikaatin hakemistopolut olivat oikein. Käytin cd, ls ja pwd komentoja tarkistaakseni, että sertifikaatit löytyvät oikeasta sijainnista. Huomasin, että lego-kansion sisällä oli certificates-kansio, jonka sisällä oli vielä toinen certificates-kansio, jossa tarvittavat tiedostot sijaitsivat.

<img width="517" alt="456" src="https://github.com/user-attachments/assets/5757bf64-567b-4f5e-b45f-3e0c933a2240" />

Muokkasin konfiguraatiotiedostoon oikeat hakemistopolut suorittamalla komennon sudoedit /etc/apache2/sites-available/nitaarifi.com.conf ja korjaamalla SSLCertificateFile- ja SSLCertificateKeyFile-kohdat.

<img width="496" alt="virtualhost4432" src="https://github.com/user-attachments/assets/ea5d7466-a60b-4b26-a0ee-eefa9bfd086b" />

Sitten otin käyttöön SSL komennolla sudo a2enmod ssl.

<img width="250" alt="a2enmod" src="https://github.com/user-attachments/assets/b2caeac3-dfb8-478b-ae4c-852e8ec4bc7e" />

Lopuksi testasin HTTPS-sivun toimivuuden, ja se onnistui vihdoin!

Kannettavalla Chromella selain näyttää seuraavan näkymän:

<img width="500" alt="image" src="https://github.com/user-attachments/assets/59149341-80cc-4818-81d8-2895844ce936" />
<br>


iPhone 13:lla Safarilla selain näyttää seuraavaa:

![IMG_8950](https://github.com/user-attachments/assets/cc342bd5-84fa-44be-9729-4f0f0cbfd556)

---

Lähteet

ChatGPT. Käytetty prompti: Ilmaisen TLS-sertifikaatin hankkiminen ja asentaminen Let's Encryptiltä Linux komentorivillä. OpenAI. Haettu 1.3.2025.

Chatgpt. Käytetty pompti: Suoritin Certbotin Let's Encryptin TLS-sertifikaatin hakemiseksi ja sain virheen: 'ei saada yhteyttä'. Olen tarkistanut DNS-tietueet ja palomuurin asetukset, mutta ongelma jatkuu. Mikä voisi olla virheen syy ja mitä seuraavaksi pitäisi tarkistaa tai kokeilla?. OpenAI. Haettu 9.3

https://github.com/juuliapurho/linux-course/blob/main/h6-Salataampa.md. Luettu 9.3.2025.

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
