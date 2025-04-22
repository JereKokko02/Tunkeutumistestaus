# Tehtävänannon löytää osoitteesta: https://terokarvinen.com/tunkeutumistestaus/#h2-taysin-laillinen-sertifikaatti

<br>

Tämä on Tunkeutumistestaus - ICI005AS3A-3002 - 2025p4 -kurssin neljännen viikon vastausdokumentti. Tässä dokumentissa dokumentoidaan opiskelijan tekemistä sekä tekemisen vaiheita tekstin ja kuvin. 

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
<br>
<br>
<br>

# x) Lue/katso ja tiivistä. (Tässä x-alakohdassa ei tarvitse tehdä testejä tietokoneella, vain lukeminen tai kuunteleminen ja tiivistelmä riittää. Tiivistämiseen riittää muutama ranskalainen viiva kustakin artikkelista. Kannattaa lisätä myös jokin oma ajatus, idea, huomio tai kysymys.)

## Karvinen 2022: https://terokarvinen.com/2022/cracking-passwords-with-hashcat/

- Hashcat harjoitus
- Hashcatin käyttöohjeet
- Hashien perusteet (md5 jne)
- Rockyou.txt joka on itestä hyödyllinen
- -- show komento

## Karvinen 2023: https://terokarvinen.com/2023/crack-file-password-with-john/

- John the ripper ohjelman käyttö sekä asennus
- Kuinka sitä käytetään
- Mihin sitä käytetään
- Esimerkkiharjoitus
- Outputin analysointia paljon

##  Santos et al 2017: Security Penetration Testing: https://www.oreilly.com/videos/security-penetration-testing/9780134833989/9780134833989-sptt_00_06_00_00/

- Videoissa katsotaan salasanojen ja niihin liittyvien tietojen murtamista.
- Hyökkäyksiä, mitä haetaan ja miten?
- John the ripper ja hashcat tekee paluun
- Lopussa suojautumisehdotuksia
- Summa summarum video --> Nopeasti paljon tietoa.

## Kennedy et al 2025: Metasploit: File-Format Exploits (sivun loppuun, eli Wrapping Up loppuun): https://www.oreilly.com/library/view/metasploit-2nd-edition/9798341620032/xhtml/chapter9.xhtml#:-:text=File-Format%20Exploits

- Browser exploit ja file-format exploit
- Mitä enemmän tieto murrestavasta kohteesta, sitä helpompaa
- Onnistuminen siis riippuu murtajasta ja kohteen tasosta.


## Singh 2025: The Ultimate Kali Linux Book: Understanding Active Directory (Vain tuo kappale, ei enää "Enumerating Active Directory") https://learning.oreilly.com/library/view/the-ultimate-kali/9781835085806/Text/Chapter_12.xhtml#_idParaDest-272

- Active directoryn toiminta
- Toimialueen rakenne
- Toimialueiden suhteet
- Keskitettyä hallintaa
- Winows palvelimet -kurssin sisältöä.

## Vapaaehtoinen: Kennedy et al 2025: Metasploit: https://learning.oreilly.com/library/view/metasploit-2nd-edition/9798341620032/xhtml/chapter6.xhtml#toc-link_88

- Metasploitable 3 meterprer.
- Meterprer mahdollistaa hallinnan onnistuneen hyökkäyksen jälkeen.
- Meterprerillä hyökkääjä pääsee siis tekemään tihutöitä
- Listataan mm kiwi, kuvankaappausten ottaminen, käyttäjien syötteen tallennus jne.
- Meterprer on siis payload työkalu.

<br>
<br>
<br>
<br>

# a) Asenna Hashcat ja testaa sen toiminta murtamalla esimerkkisalasana. 

<br>

Latasin rockyou.txt tiedoston Tero Karvisen [Ohjeita](https://terokarvinen.com/2022/cracking-passwords-with-hashcat/) seuraamalla ja valitsin satunnaisen sanan:

<br>

![image](https://github.com/user-attachments/assets/66dff66d-7dea-4620-9880-9e5586184c22)

<br>

Tässä tehtävässä käytettäväksi Salasanaksi tuli "kahloista"

<br>

Tämän jälkeen menin sivustolle https://www.browserling.com/tools/all-hashes ja loin salasanan MD5 hashin:

<br>

![image](https://github.com/user-attachments/assets/2c72e968-7784-4cc8-882e-30c50bf4cfbf)

<br>

Valitsin md5 hashin jonka kopioin leikepöydälle. Tämän jälkeen loin uuden tekstitiedoston johon liitin sen:

<br>

![image](https://github.com/user-attachments/assets/2595ce67-7f09-4a34-83c4-baeb4fe0e7af)

<br>

Varmistin vielä että hashi on toimiva käyttämällä hashcatin "hashid" komentoa. 

<br>

![image](https://github.com/user-attachments/assets/7431fb8a-c1d8-45ad-9ee5-08dc62cece08)

<br>

Hashcat tunnisti salasanan mahdolliset hashit ja yksi niistä oli MD5.

<br>

## Tilanne tässä vaiheessa on siis seuraava:

1. Olen luonut murrettavalle salasanalle md5 hashin ja liittänyt sen uuteen tekstitiedostoon josta tulee hashcatin kohdetiedosto (md5hash.txt)
2. Valittu salasana on osa rockyou.txt sanalistaa jota hashcat käyttää hyödykseen salasanan murtamisessa. Hashcat toimii tässä esimerkissä vähän kuten ffuf: Se testaa valitun wordlistin sisällön kohdetiedostoon.
3. Tämä on hyvin simppeli harjoitus sillä eihän kukaan kirjoita salasanojen hasheja muuten tyhjään tekstitiedostoon varsinkaan käyttäen tunnettua menetelmää. Tässä vaan testataan hashcatin käyttöä.

<br>

Enää jäljellä oli testata saako hashcat murrettua salasanan hashin. Tämän testasin ajamalla komennon "hashcat -m 0 md5hash.txt rockyou.txt ja hashcat mursi hashin paljastaen sen sisällön:

<br>

![image](https://github.com/user-attachments/assets/c9724770-345f-4bf8-9f87-d4daa22d70f3)

<br>
<br>
<br>
<br>

# c) Asenna John the Ripper ja testaa sen toiminta murtamalla jonkin esimerkkitiedoston salasana.

Minulla alkoi John temppuilemaan ja sen käyttäminen johti virtuaalikoneen jatkuvaan kaatumiseen. En saanut ratkaistua syytä mutta ymmärrän kuitenkin ripperin toiminnan. Yritän vielä selvittää mistä tämä johtuisi.
Hyvä video käytöstä on mm. [tämä](https://youtu.be/IM8x_ddNsSc).

<br>
<br>
<br>
<br>

# e) Tiedosto. Tee itse tai etsi verkosta jokin salakirjoitettu tiedosto, jonka saat auki.

<br>

Päätin kokeilla zippitiedoston murtamista. Loin zippitiedoston jonka salasin salasanalla "aapo" tämän jälkeen latasin ohjelman nimeltä fcrackzip komennolla sudo apt-get install fcrackzip:

<br>

![image](https://github.com/user-attachments/assets/6d6e3274-2e92-4aa3-a170-54d23d0866b0)

<br>

Ajoin komennon "fcrackzip -vul 1-4 zippikansio.zip ja ohjelma löysi salasanan:

<br>

![image](https://github.com/user-attachments/assets/576e52b0-9adc-4424-85c2-d44e4ba964f1)

<br>

Fcrackzip on melko hidas työkalu. Mikäli sillä yritetään ratkaista 6-kirjaimista salasanaa joka on "aaaaaa" kestää siinä noin 20 min. Jos salasana on vaikka ApiLaS12-: , voin kokemuksesta sanoa että menee yli tunti. Mutta kyseinen ohjelma on ihan kiva ja simppeli brutefroce -työkalu.

<br>
<br>
<br>
<br>

# f) Tiiviste. Tee itse tai etsi verkosta salasanan tiiviste, jonka saat auki. Murra sen salaus. (Jokin muu formaatti kuin aiemmissa alakohdissa kokeilemasi. Voit esim. tehdä käyttäjän Linuxiin ja murtaa sen salasanan.)

<br>

Tämän tehtävän tekemisessä on nyt ongelmaa kun Johnny boy ei vieläkään toimi. Alustavasti tehtävät jää nyt tähän pisteeseen ja palaan niihin jos/kun saan ratkaistua Johnnyn ongelman.

<br>
<br>
<br>
<br>
<br>
<br>
<br>

Lisälähteet:
1. https://www.youtube.com/watch?v=W6SIU-ggTDI&t=60s | Katsottu 20.4.2025
2. https://www.youtube.com/watch?v=z4_oqTZJqCo | Katsottu 21.4.2025
3. https://www.youtube.com/watch?v=RyQL9AdxHqY | Katsottu 21.4.2025
4. https://youtu.be/b4b8ktEV4Bg | Katsottu 22.4.2025
5. https://youtu.be/DMtFhACPnTY | Katsottu 22.4.2025
6. https://hashcat.net/hashcat/ | Silmäilty 22.4.2025
