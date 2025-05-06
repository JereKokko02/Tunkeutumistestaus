
# x) Lue/katso ja tiivistä. (Tässä x-alakohdassa ei tarvitse tehdä testejä tietokoneella, vain lukeminen tai kuunteleminen ja tiivistelmä riittää. Tiivistämiseen riittää muutama ranskalainen viiva kustakin artikkelista. Kannattaa lisätä myös jokin oma ajatus, idea, huomio tai kysymys.)

## Karvinen 2025: Start Your Research with a Review Article https://terokarvinen.com/review-article/

- JUFO 1,2,3 eli luokitteluperusteet (https://julkaisufoorumi.fi/fi/arvioinnit/luokitteluperusteet)
- Tero KArvisen artikkeli
- Scholar.google.com on googlen tarjoama palvelu josta voi hakea varmistettuja tutkimusartikkeleita
- Artikkelissa opetetaan tunnistamaan tutkimusmateriaaleja
- Eli artikkeli on siis tutkivan tutkimuksen tutoriaali (Olen ylpeä näistä sananvalinnoista)

<br>
<br>
<br>
<br>

## Review. Etsi vapaavalintainen review eli katsausartikkeli, joka liittyy kurssin aiheisiin.

<br>

Artikkeli: https://ieeexplore.ieee.org/abstract/document/10381703

<br>

M. B. Muzammil, M. Bilal, S. Ajmal, S. C. Shongwe and Y. Y. Ghadi, "Unveiling Vulnerabilities of Web Attacks Considering Man in the Middle Attack and Session Hijacking," in IEEE Access, vol. 12, pp. 6365-6375, 2024, doi: 10.1109/ACCESS.2024.3350444.
keywords: {Surveys;Security;Protocols;Databases;Metadata;Blockchains;STEM;Privacy;Hypertext systems;Privacy;Man-In-The-Middle attack;session hijacking;hypertext transfer protocol (HTTP) hijacking},

<br>

- Reilusti yli 4 sivua eli tiivistelmä perustuu silmäilyyn
- Artikkelissa käydään läpi man-in-the-middle hyökkäyksen toimintaa ja siihen liittyviä haavoittuvuuksia
- Man-in-the-middle hyökkäyksessä hyökkääjä pyrkii saamaan luotua uuden yhteyden lähettäjään ja täten saamaan lähettäjän luulemaan että hyökkääjä on vastaanottaja. KS. artikkelin kuva 3
- Artikkeli on tutkiva artikkeli
- Artikkelissa tutkitaan myös session hijacking hyökkäyksen eroja man-in-the-middleen.
- Man-i-the-middle on vain yksi hyökkäys hyökkääjän laajassa työkalupakissa.

<br>
<br>
<br>
<br>

# a) HTB Dancing. Ratkaise HackTheBox.com: Starting Point: Tier 0: Dancing.

Aloitin tehtävän seuraamalla dancing tehtävän ohjeita. Tehtävässä käynnistettiin ensin openvpn yhteys koneeseen:

<br>

![image](https://github.com/user-attachments/assets/6c6819a6-10b9-4826-85a8-72c2532ba4c3)

<br>

HTB kone heräsi!

<br>

![image](https://github.com/user-attachments/assets/b48b1be5-3552-49d0-828b-725282032df0)


<br>

## Task 1: What does the 3-letter acronym SMB stand for?

  - SMB = Server Message Block.

<br>

## Task 2: What port does SMB use to operate at?

  - SMB toimii portissa 445.

<br>

## Task 3: What is the service name for port 445 that came up in our Nmap scan?

- Tässä vaiheessa tuli tenkkapoo: kohdekoneeseen pystyy hyökkäämään vain mikäli hyökkääjän kone on yhdistetty internettiin. Jos kali linuxin verkkokortiksi laittaa nat, ei saa enää yhteyttä kohdekoneeseen. Tässä vaiheessa yritin etsiä tieto netistä miten tehtävän saisi tehtyä turvallisesti, mutta en löytänyt vastausta. Tämän tehtävän saisi helposti tehtyä ihan vaan nmappiä käyttäen mutta en osaa tehdä sitä turvallisesti. Koska haluan joskus vielä omistaa vuoden 1968 punaisen Dodge Chargerin, päätin että en ota turhaa riskiä. Tästä tehtävästä eteenpäin teen ne tehtävät mitkä pystyn turvallisesti suorittamaan. Näihin tehtäviinhän siis löytyy valmiit vastaukset ja tutoriaalit netistä että oikeiden vastausten kopioiminen olisi lastenleikkiä, mutta en käy sitä tekemään.

<br>

## Task 4: What is the 'flag' or 'switch' that we can use with the smbclient utility to 'list' the available shares on Dancing?

- -L (man sivut) eli syntaksi olisi "smbclient -L <kohdeosoite> (10.129.41.129) https://linux.die.net/man/1/smbclient

<br>

Task 5: How many shares are there on Dancing?

-

<br>

## Task 6: What is the name of the share we are able to access in the end with a blank password?

-

<br>

## Task 7: What is the command we can use within the SMB shell to download the files we find?

- Get

<br>
<br>
<br>
<br>

# b) HTB Responder. Ratkaise HackTheBox.com: Starting Point: Tier 1: Responder.

Kone käynnistettiin samalla tavalla kuin aikaisemmin.

## Task 1: When visiting the web service using the IP address, what is the domain that we are being redirected to?

- unika.htb

<br>

![image](https://github.com/user-attachments/assets/bb5d9029-9293-4b42-8438-04f254aa159a)

<br>

<br>

## Task 2: 

- PHP

<br>

## Task 3: What is the name of the URL parameter which is used to load different language versions of the webpage?

- Tässä vaiheessa tuli taas paikka jossa pitää porttiskannata. Vastauksen saisi taas helposti nmapilla (Tällä kertaa ip 10.129.123.146).

<br>

## Task 4: Which of the following values for the `page` parameter would be an example of exploiting a Local File Include (LFI) vulnerability: "french.html", "//10.10.14.6/somefile", "../../../../../../../../windows/system32/drivers/etc/hosts", "minikatz.exe"

-

<br>

## Task 5: Which of the following values for the `page` parameter would be an example of exploiting a Remote File Include (RFI) vulnerability: "french.html", "//10.10.14.6/somefile", "../../../../../../../../windows/system32/drivers/etc/hosts", "minikatz.exe"

-

<br>

## Task 6: What does NTLM stand for?

- New Technology LAN Manager

<br>

## Task 7: Which flag do we use in the Responder utility to specify the network interface?

-

<br>

## Task 8: There are several tools that take a NetNTLMv2 challenge/response and try millions of passwords to see if any of them generate the same response. One such tool is often referred to as `john`, but the full name is what?.

- John the ripper!

<br>

## Task 9: What is the password for the administrator user?

-

<br>

## Task 10: We'll use a Windows service (i.e. running on the box) to remotely access the Responder machine using the password we recovered. What port TCP does it listen on?

-

<br>
<br>
<br>
<br>




