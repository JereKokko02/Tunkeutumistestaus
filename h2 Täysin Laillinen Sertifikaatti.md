





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
