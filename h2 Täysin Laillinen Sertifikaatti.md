# Tehtävänannon löytää osoitteesta: https://terokarvinen.com/tunkeutumistestaus/#h2-taysin-laillinen-sertifikaatti

<br>

Tämä on Tunkeutumistestaus - ICI005AS3A-3002 - 2025p4 -kurssin toisen viikon vastausdokumentti. Tässä dokumentissa dokumentoidaan opiskelijan tekemistä sekä tekemisen vaiheita tekstin ja kuvin. 

Tehtävät on tehty käyttäen Asus Vivobook 15 läppäriä. Muita työkaluja on muun muassa:

- Oracle VirtualBox (Version 7.1.6 r167084 (Qt6.5.3)) ohjelma
- Kali linux virtuaalikone
- Metasploitable2 virtuaalikone

<br>

# HUOM! Mikäli yrität replikoida tehtävädokumentissa esiintyviä tehtäviä ja niiden ratkaisuja, perehdy ensin tunkeutumistestaukseen liittyviin lakiasetuksiin ja säännöksiin.

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

# x) Lue/katso ja tiivistä.

<br>
<br>

## OWASP 2021: OWASP Top 10:2021. 
  - https://owasp.org/Top10/A01_2021-Broken_Access_Control/
  -  https://owasp.org/Top10/A10_2021-Server-Side_Request_Forgery_%28SSRF%29/

<br>

### OWASP 2021 listan top 10 listan numero 1. Broken access control
- Broken access controllissa käyttäjillä on enemmän oikeuksia järjestelmissä kuin mitä heillä pitäisi olla.
- Johtuu yleensä inhimillisestä virheestä.
- Pomppasi sijalta 5. sijalle 1.
- Pystyy ehkäisemään mm. deny-by-default periaatteella sekä sillä, että verkkopalvelin ei lähetä raakaa dataa kuten salasanatietoja käyttäjälle (Eli esim verkkosivun url:ssa ei lue "UserID = 1111" jne)

<br>

### OWASP 2021 listan numero 10. Server-Side Request Forgery (SSRF)
- Eli väärien pyyntöjen lähetys palvelimille.
- Tämän mahdollistaa se, että palvelinta ei ole konfiguroitu varmentamaan onko käyttäjän lähettämä pyyntö aito vai väärennös.
- Pystyy ehkäisemään deny-by-default periaatteella, HTTP jälleenlähetyksen pois päälle laittamisella sekä käyttäjän lähettämän tiedon validoimisella.

<br>
<br>

## PortSwigget Academy: 

  - https://portswigger.net/web-security/access-control/idor
  - https://portswigger.net/web-security/file-path-traversal
  - https://portswigger.net/web-security/ssrf
  - https://portswigger.net/web-security/cross-site-scripting

<br>

- IDOR, eli Insecure direct object references on hyökkäys jossa hyökkääjä pääsee käsiksi tai muokkaa käyttäjille tarkoitettuja resursseja.
- Path travelsar on hyökkäystapa jossa hyökkääjä pyrkii liikkumaan verkkosivun hakemistossa syöttämällä /, cd .. tai cd. komentoja. Eli hän siis pyrkii liikkumaan esimerkiksi verkkosivun hakemistossa samalla tavalla kuin tietokoneen hakemistossa.
- Server-Side Request Forgery (SSRF) on hyökkäystapa jossa hyökkääjä lähettää vääriäpyyntöjä verkkopalvelimille. Hyökkääjä pyrkii saamaan palvelimen palauttamaan vahingossa hänelle kuulumattomia tietoja.
- Cross-site scripting, eli xss on hyökkäystapa jossa hyökkääjä pyrkii lähettämään haitallista javascriptiä verkkosivulle. Tällä hän pyrkii saamaan verkkosivulta jotakin tieto itselleen tai vaikkapa muokkaamaan verkkosivun ulkonäköä.
- Portswiggerissä on todella paljon näihin hyökkäystekniikoihin liittyvää dokumentointia sekä esimerkkejä ja labroja.

<br>
<br>
<br>
<br>

# a) Totally Legit Sertificate. Asenna OWASP ZAP, generoi CA-sertifikaatti ja asenna se selaimeesi.

<br>
<br>


Asensin zaproxyn kali viertuaalikoneelle komennolla "'sudo apt-get install zaproxy". Asennuksen jälkeen avasin sen komennolla "zaproxy".

<br>

Asennus onnistui:

<br>

![image](https://github.com/user-attachments/assets/d96867d0-0668-4cf2-879c-de3a1fec197a)

<br>

Sitten loin uuden sertifikaatin zaproxyssä:

<br>

![image](https://github.com/user-attachments/assets/f2d3cf62-c230-4995-95e3-d6f187afc957)

<br>

Ja tallensin sen:

<br>

![image](https://github.com/user-attachments/assets/0f36125f-0031-4bff-bc35-44603fba6b13)

<br>

Sitten avasin firefoxyn ja menin sertifikaatit asetuksiin:

<br>

![image](https://github.com/user-attachments/assets/48a8d3c0-0e6c-4b4f-9002-7947adb2b12d)

<br>

Tallensin sertifikaatin ja annoin sille oikeudet tarkastella vain verkkosivuja (Kuvittele mielessäsi että ylin täppä on ruksattu):

<br>

![image](https://github.com/user-attachments/assets/eae9a96c-43e3-4b3b-94b3-33e0891ad926)

<br>

Avasin zaproxyn ja varmensin että sertifikaatti lähti toimimaan:

<br>

![image](https://github.com/user-attachments/assets/d641d56a-9dfa-457b-8725-a43badf75895)

<br>
<br>
<br>
<br>

# b) Kettumaista. Asenna "FoxyProxy Standard" Firefox Addon, ja lisää ZAP proxyksi siihen.

<br>
<br>

Latasin foxyproxyn:

<br>

![image](https://github.com/user-attachments/assets/2a144836-a15d-46ce-9c76-d2fcee9d2063)

<br>

Loin uuden proxyn:

<br>

![image](https://github.com/user-attachments/assets/07f70715-63c9-4885-8b22-ef6debb8ce3d)

<br>
<br>
<br>
<br>

# PortSwigger Labs.

<br>

## c) Reflected XSS into HTML context with nothing encoded

<br>

![image](https://github.com/user-attachments/assets/2458adcb-0c6b-469f-ba74-5cf9232f37d8)

<br>

Selitys: <script>alert(1)</script> komento toimii siksi, sillä se on javascriptiä. Tässä tapauksessa verkkosivu lukee käyttäjän antaman syötteen ja alkaa suorittamaan sitä. Alert(1) on javascriptissä popup alertin kutsukomento. Tältä pystyttäisiin suojautumaan mikäli verkkosivu lukisi käyttäjän syötteen pelkkänä tekstinä.

<br>
<br>

## d) Tämä on sama tehtävä uudelleen ainakin tehtävänannossa.

<br>
<br>

## e)  Tähän saakka pääsin aikarajoitteiden vuoksi.

<br>
<br>
<br>
<br>

# Lähteet:
1. FoxyProxy: https://addons.mozilla.org/en-US/firefox/addon/foxyproxy-standard/
2. Portswigger Lab: Reflected XSS into HTML context with nothing encoded. https://portswigger.net/web-security/cross-site-scripting/reflected/lab-html-context-nothing-encoded

