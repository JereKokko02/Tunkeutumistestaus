# Tehtävänannon löytää osoitteesta: https://terokarvinen.com/tunkeutumistestaus/#h2-taysin-laillinen-sertifikaatti

<br>

Tämä on Tunkeutumistestaus - ICI005AS3A-3002 - 2025p4 -kurssin kolmannen viikon vastausdokumentti. Tässä dokumentissa dokumentoidaan opiskelijan tekemistä sekä tekemisen vaiheita tekstin ja kuvin. 

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

# x) Lue/katso/kuuntele ja tiivistä.

<br>

## 1. Karvinen 2023: Find Hidden Web Directories - Fuzz URLs with ffuf [Linkki](https://terokarvinen.com/2023/fuzz-urls-find-hidden-directories/)
- Tero Karvisen lyhyt artikkelu Ffuf -työkalusta sekä sen testaamiseen tarkoitettu dirtfuzt0 Maali.
- Artikkelissa ffuffin käyttöohje
- Artikkelissa käydään läpi myös ffuffin palautusarvoja ja mitä ne tarkoittaa.
- Kyseessä on harjoitus jota on käytetty mm. Webbiin tunkeutumisen kurssilla.
- Artikkeli on siis tehty opetustarkoitukseen havannollistamaan ffuffin toimintaa sille luodussa ympäristössä.

<br>

## 1. Hoikkala 2023: ffuf README.md [Linkki](https://github.com/ffuf/ffuf/blob/master/README.md)
- Ffuf työkalun readme
- Sisältää kaiken aina asennuksesta käyttöön ja ongelmanratkaisuun.
- Omistaja herra Hoikkala itse
- Sisältää ffuffin maskotista muutaman kuvan
- Huomasitko että readmen lopussa linkki lisenssiin?

<br>
<br>
<br>
<br>

# a) Fuzzzz. Ratkaise dirfuz-1 artikkelista Karvinen 2023

<br>
<br>

Asensin maalin käyttäen tehtävänannon ohjeita: https://terokarvinen.com/2023/fuzz-urls-find-hidden-directories/

<br>

![image](https://github.com/user-attachments/assets/41538f43-9457-49a3-b164-c93191ea29e0)

<br>

![image](https://github.com/user-attachments/assets/1546f7c2-84ea-4efa-9dce-c6cf583201c7)

<br>

Ratkaisin sen ffuffilla. Filtteröin -154 ja löysin "admin-wp":

<br>


![image](https://github.com/user-attachments/assets/de1ba71b-4b93-495e-a8e3-42a3dc83be9d)

<br>

Laitoin sen verkkosivun urliin, ja pam:

<br>

![image](https://github.com/user-attachments/assets/a3a6d1c7-881e-453e-865f-5727aa7e5633)

<br>
<br>
<br>
<br>

# b) Fuff me. Asenna FuffMe-harjoitusmaali. Karvinen 2023

Asensin tehtävänannossa olleiden ohjeiden mukaan: https://terokarvinen.com/2023/fuffme-web-fuzzing-target-debian/

<br>

![image](https://github.com/user-attachments/assets/c23e8d50-64cf-43ca-a1c5-be4493006c71)

<br>

# c) Basic Content Discovery

<br>

![image](https://github.com/user-attachments/assets/d043edb2-7530-42c1-aef3-aeffdebdb923)

<br>

![image](https://github.com/user-attachments/assets/1f916325-ffa0-46b4-a4f2-bb74d5bc0d73)


# d) Content Discovery With Recursion

<br>

![image](https://github.com/user-attachments/assets/a8793724-518c-4392-806f-90f3394b32bd)

<br>

![image](https://github.com/user-attachments/assets/c427e5cf-814b-4af4-a9c9-b03ac520c28d)

<br>

# e) Content Discovery With File Extensions

<br>

![image](https://github.com/user-attachments/assets/1fcee516-3a3e-4a12-a662-0a0555c1a97f)

<br>

![image](https://github.com/user-attachments/assets/6d023bc2-8b58-4622-8221-bdda3497974b)

<br>

# f) No 404 Status

<br>

![image](https://github.com/user-attachments/assets/fecad75d-1264-44d6-9d4d-bcbea0c42242)

<br>

![image](https://github.com/user-attachments/assets/cf0c7dce-fa9d-4b7b-b582-957e1f5b665a)

<br>

# g) Param Mining

<br>

![image](https://github.com/user-attachments/assets/4ad9b243-a29b-480e-be28-1f52b9d19232)

<br>

# h)  Rate Limited

<br>

![image](https://github.com/user-attachments/assets/6f24fd7c-9fc4-4bdc-b80f-a7275743b0a3)

<br>

![image](https://github.com/user-attachments/assets/63411062-a62a-4467-a4dc-37fed4112798)

<br>

# i) Subdomains - Virtual Host Enumeration

<br>

![image](https://github.com/user-attachments/assets/6faf1c58-0ec9-4eaf-b167-016af48280e3)

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

# Lähteet

1. https://github.com/ffuf/ffuf
2. https://hackviser.com/tactics/tools/ffuf

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









# Mitä astronautti sanoi kun löysi luurangon kuusta?

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
<br>
<br>
<br>
<br>
<br>
<br>
<br>

# "Mitä kuuluu?"



