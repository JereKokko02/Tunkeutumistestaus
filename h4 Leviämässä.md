














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

<br>

Ajoin komennon "hashcat -m 0 md5hash.txt rockyou.txt ja hashcat mursi hashin:

![image](https://github.com/user-attachments/assets/c9724770-345f-4bf8-9f87-d4daa22d70f3)





















Lähteet:
https://www.youtube.com/watch?v=W6SIU-ggTDI&t=60s
