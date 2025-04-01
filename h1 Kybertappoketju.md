# Tehtävät ja tehtävänannon löytää osoitteesta https://terokarvinen.com/tunkeutumistestaus/

<BR>
<BR>
<BR>
<BR>

# x) Lue/katso/kuuntele ja tiivistä.

<BR>
<BR>

## Herrasmieshakkerit Tietoturvan Niksipirkka, vieraana Juho Rikala https://podcasts.apple.com/fi/podcast/tietoturvan-niksipirkka-vieraana-juho-rikala-0x34/id1479000931?i=1000670631512

<BR>

- Vieraana Keskon tietoturvajohtaja Juho Rikala
- Jaksossa käydään läpi tietoturvaan liittyviä teemoja
- Jaksossa käydään myös läpi luottamukseen liittyviä teemoja
- Pajatson manipulointi (Rikos jota ei saa ikinä anteeksi!)

<BR>
<BR>

## Lockheed martinin IT käännös kill chain -mallista https://lockheedmartin.com/content/dam/lockheed-martin/rms/documents/cyber/LM-White-Paper-Intel-Driven-Defense.pdf

<BR>

- Miten suojellaan tietoverkkoja?
- Kill chain (it) Tunnista -> Valjasta -> Toimita -> Aktivoi -> Wreak havoc.
- Pähkinänkuoressa artikkelissa käydään läpi kill chain, mikä se on, miten se toimii ja siitä esimerkkejä.

<BR>
<BR>

## Santos et al: The Art of Hacking https://www.oreilly.com/videos/the-art-of/9780135767849/9780135767849-SPTT_04_00/

<BR>

- Active ja passive reconnaisance mitä ne ovat ja miten ne eroavat toisistaan.
- Mikä on recon vaiheen tarkoitus, mitä löydetyllä tiedolla voidaan saavuttaa.
- Porttiskannauksen A ja O 
- Viimeisessä videossa luotellaan skannaustyökaluja
- Summasummarum: Videoissa opitaan porttiskannaamaan tehokkaasti.

<BR>
<BR>

## Esimerkki porttiskannauksen seuraamuksista https://finlex.fi/fi/oikeuskaytanto/korkein-oikeus/ennakkopaatokset/2003/36#OT2_OT1

<BR>

- Syytetty porttiskannasi osuuspankin tietojärjestelmän.
- jäi kiinni, sai syytöksen.
- korvausvaatimukset 75 000 markkaa, eli noin 20 000 euroa (1998 -> 2024)
- Yritti keplutella pois, oikeus ei antanut. Viimeinen päätös oli tuomion voimaan astumisesta.

<BR>
<BR>
<BR>
<BR>

# a) Asenna Kali virtuaalikoneeseen.

<BR>

Tehty ennen onnistuneesti.

<BR>
<BR>
<BR>
<BR>

# b) Irrota Kali-virtuaalikone verkosta. Todista testein, että kone ei saa yhteyttä Internetiin

<BR>

![image](https://github.com/user-attachments/assets/2cf8e5d2-eed5-4288-bb44-f463ea623576)

<BR>
<BR>
<BR>
<BR>

# c) Porttiskannaa 1000 tavallisinta tcp-porttia omasta koneestasi (nmap -T4 -A localhost).

<BR>

![image](https://github.com/user-attachments/assets/c13d8e55-d84e-4e6f-aaf1-4d55abadf1d3)

<BR>

Komennon parametrit:

-T = timing, eli kuinka tiheään tahtiin nmap alkaa portteja skannaamaan.
  - Arvot listattu nmapin verkkosivuilla osoitteessa: https://nmap.org/book/performance-timing-templates.html

-A = Skannauksen laajuus.
  - A eli Agressive tarkoittaa tässä tapauksessa sitä, että nmap pyrkii hakemaan skannattavasta laitteesta käyttöjärjestelmän, sen version, sekä pyrkii selvittäämään sen topologian.

Localhost = Kohde, eli tässä tapauksessa paikallinen kone.

<BR>

Kaikki virtuaalikoneen portit on tällä hetkellä kiinni joten mitään yllättävää ei löydy.

<BR>
<BR>
<BR>
<BR>

# d) Asenna kaksi vapaavalintaista demonia ja skannaa uudelleen. Analysoi ja selitä erot.

<BR>

Asensin koneelle apache2 ja openssh-serverin.

<BR>

![image](https://github.com/user-attachments/assets/38493630-b83a-4f5a-bbb4-63dfb08b5ed2)

<BR>

Kun skannaa nmapillä koneen uudelleen huomaa että portit 22 ja 80 on auenneet. 80 on apache2 ja 22 on openssh.

<BR>

![image](https://github.com/user-attachments/assets/b19fbec7-7bba-41a1-a358-28ea1fc957b4)

<BR>
<BR>
<BR>
<BR>

# e) Asenna Metasploitable 2 virtuaalikoneeseen

<BR>

![image](https://github.com/user-attachments/assets/aa6f34cb-f85d-44d7-b8dc-22ffc3104514)

<BR>

Hieman huono kuva mutta ajaa asiansa. Asensin metaexploitablen virtualboxiin. Uusi kone (ei ISO:a Linux, other) kaikki muu täysin samoin mutta storage -> select existing storage -> ladattu metaexploitable 2.

<BR>
<BR>
<BR>
<BR>

# f) Tee koneiden välille virtuaaliverkko.

<BR>

Tähän kohtaan tehtävät jäi kesken. Virtualboxin host adapteri ei lähtenyt pelaamaan. En saanut ratkaistua itse.

<BR>
<BR>
<BR>
<BR>
<BR>
<BR>
<BR>
<BR>

# Lisälähteet:

<BR>

Nmap man https://linux.die.net/man/1/nmap
https://tuomasvalkamo.com/PenTestCourse/week-2/










