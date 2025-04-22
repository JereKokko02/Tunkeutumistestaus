














# a) Asenna Hashcat ja testaa sen toiminta murtamalla esimerkkisalasana.

Latasin rockyou.txt ja valitsin satunnaisen sanan (grep loista ja valitsin sopivan):

![image](https://github.com/user-attachments/assets/66dff66d-7dea-4620-9880-9e5586184c22)

Salasanaksi tuli "kahloista"

br

Tämän jälkeen menin sivustolle https://www.browserling.com/tools/all-hashes ja loin salasanan MD5 hashin:
![image](https://github.com/user-attachments/assets/2c72e968-7784-4cc8-882e-30c50bf4cfbf)

Valitsin md5 hashin jonka kopioin leikepöydälle. Tämän jälkeen loin uuden tekstitiedoston johon liitin sen:
![image](https://github.com/user-attachments/assets/2595ce67-7f09-4a34-83c4-baeb4fe0e7af)

Tilanne tässä vaiheessa on siis seuraava:

1. Olen luonut murrettavalle salasanalle md5 hashing ja liittänyt sen hashcatin kohdetiedostoon md5hash.txt
2. Valittu salasana on osa rockyou.txt sanalistaa jota hashcat käyttää hyödykseen salasanan murtamisessa.

Ajoin komennon "hashcat -m 0 md5hash.txt rockyou.txt ja hashcat mursi hashin:

![image](https://github.com/user-attachments/assets/c9724770-345f-4bf8-9f87-d4daa22d70f3)





















Lähteet:
https://www.youtube.com/watch?v=W6SIU-ggTDI&t=60s
