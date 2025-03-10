# a) Julkisen verkkotunnuksen määrittäminen omaan koneeseen

Tämän viikon tehtävänä oli ohjata valitsemani julkinen verkkotunnus suoraan palvelimelleni, jonka ostin ja konfiguroin edellisellä viikolla. Raportin palvelimen hankinnasta ja konfiguroinnista löydät [täältä kohdasta a)](https://github.com/Nitansivut/linux-course/blob/main/h4.md).

Palvelimeni isännöi verkkosivustoani ja tekee sen saataville internetiin. Verkkotunnus toimii osoitteena, jonka avulla käyttäjät voivat päästä sivustolleni ilman, että heidän tarvitsee muistaa pitkiä IP-osoitteita.

## Vaihe 1

Hankin verkkotunnuksen [Namecheap-nimisestä palvelusta](https://www.namecheap.com/). Prosessi alkoi luomalla käyttäjätilin [rekisteröitymissivun](https://www.namecheap.com/myaccount/signup/) kautta. Käytin henkilökohtaista sähköpostiosoitetta, koska koulun sähköpostilla ei onnistunut.

<img width="518" alt="image" src="https://github.com/user-attachments/assets/cf303f42-8286-4cb8-9ed8-fb0f671d7df9" />

## Vaihe 2

Rekisteröitymisen jälkeen aloin tutkimaan, että miten voin ostaa verkkotunnuksen. Klikkasin Namecheap:n logoa vasemmalta yläreunalta, jotta pääsisin takaisin etusivulle. Tämän jälkeen kirjoitin etusivulla olevaan hakukenttään verkkotunnuksen, jonka haluaisin itselleni.

<img width="562" alt="image" src="https://github.com/user-attachments/assets/c4aed13e-b2de-4deb-8d03-2f88e4dc3d3d" />

Hakutuloksissa näytettiin lista saatavilla olevista verkkotunnuksista hintoineen. Valitsin ensimmäisen, nitaarifi.com, jonka hinta on alennuskoodin kanssa 6,37 € vuodessa.

<img width="415" alt="image" src="https://github.com/user-attachments/assets/c0731772-711d-4cfb-8d69-50259479653c" />

Sitten siirryin ostoskoriini.

<img width="404" alt="image" src="https://github.com/user-attachments/assets/a64cdbad-f720-43f4-ab62-77ba3ee08352" />

Lisäsin alennuskoodin ja vahvistin tilaukseni.

<img width="261" alt="image" src="https://github.com/user-attachments/assets/49a3d9be-928b-457d-8b1e-9650be5fc60a" />

Tilauksen vahvistamisen jälkeen minut ohjattiin sivulle, jossa minun tuli täydentää tilin yhteystietoja, kuten katuosoite, postinumero, kaupunki, maakunta ja puhelinnumero. Tämän jälkeen painoin "Continue"-painiketta.

Seuraavaksi minun täytyi täyttää Whois-tiedot, jotka sisältävät verkkotunnuksen omistajan yhteystiedot. Jätin kaikki kentät oletusasetuksilla ja valitsin "User default contact" -vaihtoehdon ennen kuin painoin "Continue".

<img width="400" alt="image" src="https://github.com/user-attachments/assets/8f1cc3e4-8755-433a-9fce-51d13f0074e7" />

Lopuksi valitsin maksutavaksi korttimaksamisen, lisäsin korttitiedot ja viimeistelin maksamisen.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/f506f824-71b8-4b22-9bd1-0bd585cb4a49" />

---

**Lähteet**

https://www.cnet.com/tech/web-hosting-vs-domain/

----

# b) Name Based Virtual Host näkymään uudessa nimessäni

Tässä tehtävässä tavoitteena oli määrittää Apache-palvelimelle Name Based Virtual Host, jotta verkkosivustoni nitaarifi.com voidaan palvella palvelimellani ilman, että se vaikuttaa muihin palvelimella oleviin sivustoihin. Tämä mahdollistaa useiden verkkosivustojen isännöinnin samalla palvelimella, mutta erillisinä virtuaalisina isäntinä. Lisäksi varmistin, että kotisivuni tiedostojen muokkaaminen onnistuu ilman pääkäyttäjäoikeuksia

## Vaihe 1 

Vasemman yläreunan kautta Dashboard > Domain List > Verify Contacts > Manage.

<img width="647" alt="image" src="https://github.com/user-attachments/assets/e2969a26-09e9-4344-9f9b-63c62f4f7c30" />

Advaced DNS -välilehdeltä loin A-tietueet, joista ensimmäisessä hostina oli "@", ja toisessa "www".

<img width="409" alt="image" src="https://github.com/user-attachments/assets/3d0b6b11-9c68-4674-b408-28612ba7ea09" />
<br>


<img width="314" alt="image" src="https://github.com/user-attachments/assets/90748f04-7dcb-4b05-b94f-2c37f2a6e0b9" />

## Vaihe 2

Avasin Apache-konfiguraatiotiedoston käyttäen sudoedit-komentoa.

<img width="350" alt="image" src="https://github.com/user-attachments/assets/45f0a5a0-6989-49d1-92f2-244ca223c9cf" />

Muokkasin sen seuraavasti:

<img width="500" alt="image" src="https://github.com/user-attachments/assets/e3263cf9-3a7b-4128-9f22-6295e0b4dff8" />

Päivitin Apache-konfiguraatiotiedoston uudelleen lisätäkseni puuttuvan Require all granted -määräyksen.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/50fa283d-f921-4713-ab02-e4f372dc3c71" />

## Vaihe 3

Kun olin lisännyt VirtualHostin, otin sen käyttöön Apache-palvelimella.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/9c6642f2-055b-435a-b2a1-3307400ba5d7" />

Tämän jälkeen käynnistin Apachen uudelleen, jotta muutokset astuisivat voimaan.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/90ad829f-52e6-420f-8180-823146386f8b" />

## Vaihe 4

Seuraavaksi loin hakemiston, johon kotisivuni tallennetaan.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/7a119308-1e31-4b3a-a54d-7a5780ecee18" />

Määritin, että käyttäjä nita voi muokata verkkosivuston tietoja ilman pääkäyttäjäoikeuksa.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/af6b22e4-a463-43c4-ad07-6b8fa704d116" />

Lopuksi testasin, että kaikki toimii oikein. Kirjoitin selaimeen http://nitaarifi.com ja verkkosivustoni näkyi oikein. 

<img width="500" alt="image" src="https://github.com/user-attachments/assets/f1179617-01ce-4045-85d1-e86a982e59c0" />

---
Lähteet

https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited

---

# c) Kotisivun luominen ja palvelimelle siirtäminen

Seuraavaksi tehtävänä oli tehdä yksinkertaisen kotisivun, jossa on kolme alasivua:index.html (Etusivu), blog.html (Blogisivu) ja projects.html (Projektisivu). Kaikki sivut sisältävät perusrakenteen ja navigointilinkit, jotta käyttäjä voi siirtyä sivulta toiselle. Lisäksi ne sijoitetaan hakemistoon, johon minulla on käyttöoikeus ilman pääkäyttäjäoikeuksia.

## Vaihe 1

Koska /var/www on yleensä pääkäyttäjän hallinnoima hakemisto, luodaan alihakemisto ja annetaan se minun käyttäjälleni:

mkdir -p /var/www/nitaarifi → Luo hakemiston
chown -R nita:nita /var/www/nitaarifi → Vaihtaa hakemiston omistajaksi minut (käyttäjä nita)
chmod -R 755 /var/www/nitaarifi → Asettaa oikeudet niin, että Apache voi lukea tiedostot, mutta vain minä voit muokata niitä

<img width="500" alt="image" src="https://github.com/user-attachments/assets/94e538cf-a6ac-4540-9590-f20eb3248762" />

## 2. Vaihe: Luodaan HTML-tiedostot

Sitten loin ja kopioin tiedostot sinne ilman pääkäyttäjäoikeuksia.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/6c168d79-f9ff-4c4d-b5bf-1a1474455769" />

Sittein aloitin tekemään blog.html.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/6ea599d7-543e-4d01-b67c-c18c850a9930" />

Ja lisäsin kuvassa näkyvät tiedot nano tiedostoon.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/018ef84e-a82b-4eba-b7d8-d70888383df5" />

Lopuksi tein projects.html:

<img width="500" alt="image" src="https://github.com/user-attachments/assets/df989355-e4ec-4645-9092-a9d85bcea946" />

Ja lisäsin nämä tiedot siihen.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/9adf39c2-9ac9-410b-be3a-e652b8c8f505" />

## Vaihe 3

Hain selaimella osoitteella http://nitaarifi.com ja sivu ohjasi aiemmassa tehtävässä tehdylle sivulle. Kysyin chatgbt:ltä, että mistä tämä johtuu ja selvisi, että Apache ei käytäkään /var/www/nitaarifi-hakemistoa, vaan se hakee sivuston tiedostot hakemistosta /home/nita/public_sites/nitaarifi.com. Joten minun pitää kopioida uudet HTML-tiedostoni sinne, eikä /var/www/nitaarifi-hakemistoon.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/5e5078ea-8205-437f-b36c-315b710f2a0c" />

Siirsin tiedostot oikeaan paikkaan.

Silti ei toiminut. Tiedustelin Geminiltä, että missä ongelma voisi piiletä ja se sanoi, että minun tulisi luoda uuden määritystiedoston tätä tehtävää varten, joten tein niin ja siirsin tiedostot sinne. Ei auttanut tämäkään.

## Päivitetty 25.2. klo 18.00

Päätin aloittaa tehtävän alusta. Siskoni vilkaisi tehtävääni ja huomautti, etten ollut kirjautunut palvelimelleni SSH-yhteyden kautta lainkaan. Tällä kertaa aloitin oikein ja kirjauduin UpCloud-palvelimelleni SSH-yhteyden avulla.

Ensimmäiseksi loin palvelimelle hakemiston kotisivujen tiedostoja varten. Sen jälkeen käytin Nano-editoria luodakseni kolme HTML-tiedostoa samalla tavalla kuin aiemmissa yrityksissäni. Kun tiedostot olivat valmiit, siirsin ne palvelimen julkiseen hakemistoon, /var/www/html. Käytin sudo cp -komentoa kopiointiin ja varmistin, että tiedostojen omistajuus oli oikea muuttamalla sen käyttäjätililleni sudo chown -komennolla.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/d3c7da5c-1a31-4aea-a557-912710087004" />

Tämän jälkeen lähti toimimaan. 

<img width="500" alt="image" src="https://github.com/user-attachments/assets/53daced9-8b78-4e3b-9fff-92dfc4e0127c" />
<br>


<img width="500" alt="image" src="https://github.com/user-attachments/assets/f4a49aad-b16c-4141-9aed-ddd36c5e458c" />
<br>


<img width="500" alt="image" src="https://github.com/user-attachments/assets/57cccb17-c753-445f-847f-052ce0405650" />
<br>


---

# d) Alidomainien luominen ja konfigurointi

Luodaan kaksi alidomainia, jotka osoittavat omaan palvelimeen ja näyttävät saman sivun kuin päädomeeni.

## Vaihe 1

Ensimmäiseksi loin kaksi alidomainia linuxkurssi.nitaarifi.com ja test.nitaarifi.com Namecheapissa.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/132305c8-c502-428e-8d94-8cee06cd52a9" />

## Vaihe 2

Apache-palvelimella määritin virtuaali-isännät molemmille alidomaineille, jotta ne näyttävät samaa verkkosivua kuin päädomaini nitaarifi.com. Molemmille alidomaineille luotiin konfiguraatiotiedostot linuxkurssi.nitaarifi.com.conf ja test.nitaarifi.com.conf.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/b13cc57a-4e56-46e1-bcc0-9d42a98c729a" />
<br>


<img width="500" alt="image" src="https://github.com/user-attachments/assets/6808a106-7b32-4c2f-8b65-8d10aa7110fa" />

## Vaihe 3

Konfiguraatiotiedostot aktivoinnin jälkeen Apache-palvelin ladattiin uudelleen, jotta muutokset astuivat voimaan. Komennolla sudo systemctl reload apache2 varmistin, että molemmat alidomainit toimivat oikein.

## Vaihe 4

Lopuksi testasin selaimella.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/cc1997e9-6c0d-4810-aa0c-b18f13c04817" />
<br>


<img width="500" alt="image" src="https://github.com/user-attachments/assets/1c00b2ad-6ab9-4670-a8a3-72c0dcc563cc" />

---

Lähteet

ChatGPT, OpenAI. Käytetty promptia: Miten määritän kaksi alidomainia ja kuinka konfiguroin Apachen. Käytän Namecheap -palvelua. Haettu 23.3.3025.

---

# e) DNS-tietojen tutkiminen host- ja dig-komennoilla

## Vaihe 1

Oma domain-nimeni: nitaarifi.com

Opettajan webbisivut: tekokarvinen.com

Suuri palvelu: Nelly.com

## Vaihe 2

Aloitin ajamalla ensin komennon sudo apt update, jolla päivitin pakettitiedot. Tämän jälkeen asensin dnsutils-paketin komennolla sudo apt install dnsutils. dnsutils-paketti sisältää useita hyödyllisiä DNS-työkaluja, kuten dig ja host.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/78eccb0d-0af7-459c-a1c2-abe39472b11e" />

## Vaihe 3

**nitaarifi:**

Host -komennolla näkyy, että nitaarifi.com -verkkotunnuksella on IP-osoite 94.237.18.62 ja sähköpostipalvelinten tiedot (MX-tietueet). Kuten kuvassa näkyy, niin on useita sähköpostipalvelimia, jotka käsittelevät nitaarifi.com -verkkotunnuksen sähköpostia.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/3adf3ee2-e6b0-4480-ab8d-eaf8edbccf3b" />

ANSWER SECTION näyttää, että nitaarifi.com -verkkotunnuksella on yksi A-tietue, joka osoittaa IP-osoitteeseen 94.237.18.62. Query time kertoo kyselyn keston, SERVER kertoo käytetyn nimipalvelimen ja MSG SIZE rcvd kertoo vastaanotetun viestin koon.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/0910a26f-5120-44b8-a860-9242c519b783" />

**terokarvinen.com:**

Host-komento näyttää, että terokarvinen.com -verkkotunnuksella on IP-osoite 139.162.131.217. On vain yksi sähköpostipalvelin, joka käsittelee terokarvinen.com -verkkotunnuksen sähköpostia.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/11174d3c-9381-4ce7-81bb-b24d95aae1bd" />

dig-komento vahvistaa, että terokarvinen.com -verkkotunnuksella on A-tietue, joka osoittaa IP-osoitteeseen 139.162.131.217. ANSWER SECTION näyttää, että A-tietueen TTL (Time To Live) on 6716 sekuntia. Tämä tarkoittaa, että DNS-palvelimet voivat tallentaa tämän tiedon välimuistiinsa 6716 sekunnin ajaksi.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/270b6e03-076b-4396-84b4-dbe09a6b3f0e" />

**nelly.com:**

host-komento näyttää, että nelly.com -verkkotunnuksella on useita IP-osoitteita (sekä IPv4 että IPv6). Tämä on yleistä suurille verkkosivustoille, jotka käyttävät useita palvelimia kuormanjakoon ja redundanssiin. Sähköpostiliikenne ohjataan Microsoftin sähköpostipalvelimelle (nelly-com.mail.protection.outlook.com).

<img width="500" alt="image" src="https://github.com/user-attachments/assets/5119b246-13bf-4c7a-b2b8-532efb122791" />

dig-komento vahvistaa, että nelly.com -verkkotunnuksella on kaksi A-tietuetta, jotka osoittavat IP-osoitteisiin 104.18.22.58 ja 104.18.23.58. Tämä selittää, miksi host-komento näytti useita IP-osoitteita. ANSWER SECTION näyttää, että A-tietueiden TTL (Time To Live) on 59 sekuntia. Tämä on melko lyhyt TTL, mikä tarkoittaa, että DNS-palvelimet päivittävät näitä tietoja usein.

<img width="500" alt="image" src="https://github.com/user-attachments/assets/668083c1-371f-4299-8845-a39e9731a4ac" />

---

Lähteet

https://phoenixnap.com/kb/linux-dig-command-examples

https://phoenixnap.com/kb/linux-host

https://askubuntu.com/questions/25098/how-do-i-install-dig

---

# Tehtävissä b) - e) käytetty ympäristö

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

