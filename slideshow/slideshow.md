---
marp: true
theme: gaia
_class: lead
style: |
  section {
    font-family: 'Roboto Mono', monospace;
    color: white;
  }
  code {
   font-family: 'Roboto Mono', monospace;
  }
  a {
   color: #40798C;
  }
  h2 {
    font-size: 1.1rem;
    color: #E9B44C;
    margin-bottom: 0.5rem
  }
  h3 {
   font-size: 1.05rem;
  }
  h1 {
   color: #E9B44C;
  }
  li{
    font-size: 0.8rem;
  }
  ul {
    margin: 0;
  }
  footer {
   color: grey;
  }


# header:
footer: Petr Kučera
paginate: false
backgroundColor: "#000"
size: 16:9

---

# IoT & AI

---

<!-- 
footer:  ""

-->

# Obsah
- očekávání
- IoT
- AI
- diskuze

<!-- 

# NOTES

- IoT
  - co to je
  - celkove schema, od hardware az po vizualizace a zpracovani dat
    - fyzikalni signal -> interpretovatelna informace (senzory, RFID tagy)
    - napeti -> prevod na digitalni podobu (MCU)
      - typy modulu
      - setreni energie
    - zpracovani dat a odeslani do koncentratoru (sit)
      - zpusoby pripojeni na internet (NB-IoT, ZigBee, Sigfox, LoRa a LoRaWAN, WiFi)
      - protokoly (MQTT, ESPNOW, HTTP, SSH)
    - efektivni sbirani dat, jejich zpracovani, filtrovani
    - tezba dat (vizualizace, aplikace, rozhodovani)
  - trendy
    - Prumysl 4.0
    - Digital Twins
    - Bezpečnost
  - co nabizi Azure pro IoT

- AI
  - co to je
  - jak funguje
  - zakladni modely
  - co nabizi Azure pro AI
  - diskuze nad danou problematikou

 -->

---

# Vaše očekávání

---

<!--
footer: IoT: Úvod
-->

# Co vše je IoT

- domácí spotřebiče (lednička, rychlovarka, ...)
- samoobslužná prodejna
- klasický nákupák (Tesco, Globus, Kaufland, Lidl, ...)
- chytré hodinky
- automatizovaná výrobní linka, sklad, nemocniční lůžko...

---

# Internet of things

- zařízení (MCU, spotřebiče, auta, ...)
- komunikace
- *těžba dat*

<!--
Co to tedy vlastne je?
- sit zarizeni, ktere mezi sebou dokazou komunikovat
- nejcasteji pomoci zprav

Ma smysl se IoT věnovat?
- 
-->

---

<!-- footer: IoT: Vrstvy -->
# Vrstvy IoT

- fyzikální -> signál (senzory)
- el. napětí -> digitální (MCU)
- lokální -> globální (síť)
- informace -> znalost (těžba)

<!-- 
# Vrstvy IoT
Rozdelil jsem si sam, neni nijako standartizovano
- fyzikální -> signál (senzory)
  - úvod do problematiky - zdá se jednoduché, není, dle mého nejkomplikovanější část
- el. napětí -> digitální (MCU)
  - převod, lockin detekce, PWM, ...
  - typy používaných modulů a zařízení
- lokální -> globální (síť)
  - technologie pro připojení k internetu (NB-IoT, ZigBee, Sigfox, LoRa a LoRaWAN, WiFi)
  - protokoly (MQTT, ESPNOW, HTTP, SSH)
- informace -> znalost (těžba)
  - vizualizce (Elastic Stack)
  - AI a cviceni dat
  - akce



-->

---

## 1. fyzikální -> signál

- snímač, čidlo, převodník, detektor | RFID tag
- signál (napěťový, proudový, číslicový)
- dělení
  - pasivní x aktivní
  - výstup: analogový / číslicový / dvoustavový


---

## 1. fyzikální -> signál

- měřená veličina
  - mechanické a tepelné
  - optické a jaderné
  - el. a mag. veličiny
  - chemické a bio, akustické, ...
- technologie
  - polovodičová
  - MEMS (Micro Electro-Mechanical Systems)
  - tenkovrstvé a tlustovrstvé, integrovaný senzor, ...

---

## 1. fyzikální -> signál

- kasický měřící vzorec
  - senzor (snímač)
  - měřící obvod a zesilovač
  - obvod pro zpracování signálu
  - MCU

---

## 1. fyzikální -> signál
### CO2 senzor

![h:380](assets/co2-sensor.jpg)

---

## 1. fyzikální -> signál
### Lineární zrychlení (akcelerometr) (MEMS)

![h:380](assets/MEMS-sensor.ppm)

---
## 1. fyzikální -> signál
### Hallovy senzory

![h:380](assets/hall-sensors.jpeg)

---
## 1. fyzikální -> signál
### RFID tag

![h:380](assets/RFID-tag.png)

---
## Chci feedback!
![bg w:450](assets/feedback.png)

