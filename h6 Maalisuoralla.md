# Tehtävänannon löytää osoitteesta: https://terokarvinen.com/tunkeutumistestaus/#h2-taysin-laillinen-sertifikaatti

<br>

Tämä on Tunkeutumistestaus - ICI005AS3A-3002 - 2025p4 -kurssin viimeisen viikon vastausdokumentti. Tässä dokumentissa dokumentoidaan opiskelijan tekemistä sekä tekemisen vaiheita tekstin ja kuvin. 

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

Videon linkki: https://youtu.be/KNlKXHaxSWs

- Videossa tarkastellaan Schlage nimisen valmistajan avaimia sekä lukkoja
- Videon lukkotyypit: C, CE, E, EF, F, FG, G
- Jokainen lukkotyyppie eroaa toisistaan pinnien, muodon, sekä false gatewayden suhteen.
- Yleisin Schlagen lukkotyyppi on C. Näissä on 6 tai 5 pinniä.
- Näitä lukkoja pystyy tiirikoimaan mm. videossa esitellyllä SC20 tiirikalla.
- Videon lopussa huomaa miten helppo videossa esiteltyjä lukkoja on avata.

<br>
<br>
<br>
<br>

# a) Lippuvalmistelu. Valmistele kone ensi viikon lipunryöstöön. Tästä kohdasta ei tarvita kattavaa raporttia, riittää pelkkä luettelo siitä, miten ratkaisit allaolevat kysymykset. Jos sinulla on esimerkiksi valmis, toimiva Kali VM tavallisella PC:llä, tässä ei tarvitse tehdä juuri mitään.

- Toimiva kali linux vm
- Isäntäkone amd64
- Virtualboxissa kalilla nat sekä bridged adapteri tehty, eli netin saa päälle ja pois.
- Koneessa ei ole salaisia tietoja.
- Koneessa ei ole muistiinpanoja tai tekoälyä

<br>
<br>
<br>
<br>

# b) Oma korkki. Demonstroi tunkeutumista itse valitsemallasi luvallisella maalilla.

Hackthebox tehtävä Three https://app.hackthebox.com/starting-point


# Task 1: How many TCP ports are open?

2

![image](https://github.com/user-attachments/assets/2ce8f009-c701-49ba-8163-fbc107a9719e)

<br>

# Task 2: What is the domain of the email address provided in the "Contact" section of the website?

![image](https://github.com/user-attachments/assets/cc093dc8-d1e9-4e33-8d25-5e57f9fe2f18)

thetoppers.htb

<br>

Task 3: In the absence of a DNS server, which Linux file can we use to resolve hostnames to IP addresses in order to be able to access the websites that point to those hostnames?

etc/hosts

<br>

Task 4: Which sub-domain is discovered during further enumeration?

![image](https://github.com/user-attachments/assets/decd8741-c6a3-48b2-b30f-360880178fd4)

<br>

Tähän kohtaan jäin jumiin sillä kun common.txt:n kokeilun jälkeen lataamani subdomain tekstilista oli liian suuri ffuffille. Antoi token too long erroria jatkuvasti jostakin syystä. Ratkaisun saa ajamalla "-mc all" komennon fuffilla ja sitten selaa kaikki tulokset läpi yksitellen. Tässä vaiheessa kuitenkin hermot ja aikataulu oli niin kireellä että päätin ryhtyä seuraavaan hommaan. 

<br>

![image](https://github.com/user-attachments/assets/16472936-bb81-4c9a-beb9-dc7a2d1a14cf)

<br>

Task 5: Which service is running on the discovered sub-domain?

Task 6: Which command line utility can be used to interact with the service running on the discovered sub-domain?

Task 7: Which command is used to set up the AWS CLI installation?

Task 8: What is the command used by the above utility to list all of the S3 buckets?

Task 9: This server is configured to run files written in what web scripting language?


# Lisälähteet:
1. https://linuxcommandlibrary.com/man/ffuf | Luettu 12.5.2025




