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
  p{
    font-size: 0.8rem;
  }


# header:
footer: Petr Kučera
paginate: false
backgroundColor: "#000"
size: 16:9

---

# IoT & AI

---

# Kdo jsem já

petrkucerak.cz

![bg right fit](image-4.png)

---

<!-- 
footer:  ""
paginate: true
-->

# Obsah
- očekávání
- IoT
- Embedded, safety development
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

# Můj vztah k IoT

- studium
- projekty - automatizace
- mikronotroléry
- bakalářka
- diplomka

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

- Fyzikální -> Signál (senzory)
- zpracování signálu (MCU)
- síťová (vysílání)
- informace -> znalost (IoT služba)

<!-- 
# Vrstvy IoT
Rozdelil jsem si sam, neni nijako standartizovano
- Fyzikální -> Signál (senzory)
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

## 1. Fyzikální -> Signál

- snímač, čidlo, převodník, detektor | RFID tag
- signál (napěťový, proudový, číslicový)
- dělení
  - pasivní x aktivní
  - výstup: analogový / číslicový / dvoustavový


---

## 1. Fyzikální -> Signál

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

## 1. Fyzikální -> Signál

- kasický měřící vzorec
  - senzor (snímač)
  - měřící obvod a zesilovač
  - obvod pro zpracování signálu
  - MCU

---

## 1. Fyzikální -> Signál
### CO2 senzor

![h:380](assets/co2-sensor.jpg)

---

## 1. Fyzikální -> Signál
### Lineární zrychlení (akcelerometr) (MEMS)

![h:380](assets/MEMS-sensor.ppm)

---
## 1. Fyzikální -> Signál
### Hallovy senzory

![h:380](assets/hall-sensors.jpeg)

---
## 1. Fyzikální -> Signál
### RFID tag

![h:380](assets/RFID-tag.png)

---

## 2. Zpracování signálu

- A/D převodník
- PWM modulace
- zlepšení hodnot (lock-in detekce, ...)
- problematika spotřeby energie
- OS, RT systems (Linux, FreeRTOS, WxWorks, ...)

![bg right fit](image-1.png)

---

## 2. Zpracování signálu

- A/D převodník
- PWM modulace
- zlepšení hodnot (lock-in detekce, ...)
- problematika spotřeby energie
- OS, RT systems (Linux, FreeRTOS, WxWorks, ...)

![bg right fit](image-2.png)

---

## 2. Komunikační periferie

- I2C
- SPI
- CAN Bus
- USB
- RS-232, RS-422
- UART

![bg right fit](image.png)

---

## 2. Zpracování signálu
### Moduly a mikrokontroléry

- výkonější
  - PC
  - Raspberry
  - FPGA
  - Sitara
- muduly a mikrokontroléry (ARM architecture)
  - ESP32, ESP8266
  - Raspberry PI Pico W
  - CC3200, CC3220 (TI), ATSAMW25 (Microchip), nucleo, STM32 (ST), ...


---

## 2. Zpracování signálu
### Programátorem

- Jazyky: Assembly, C/C++, Rust, *(Python)*
- PlatformIO, ESP-IDF, Kail, VxWorks, BSD, *(ArduinoIDE)*, ...

> ***Datasheet a multimetr jsou nejlepší kámošové***
  
---

## 3. Síťová
- energetická náročnost
- rozdílné požadavky
- typické hiearchické uspořádání
- bezdrátové / drátové připojení do sítě
- protokoly (MQTT, HTTP, SSH, ESPNOW, ...)

---

## 3. Síťová
### Technologie

- střední dosah
  - NB-IoT
  - Sigfox
  - LoRa
- malý dosah
  - ZigBee
  - Wi-Fi
  - Bluetooth

---

## 3. Síťová
### Narrowband IoT

- využívá již vybudovanou infrastrukturu mobilních sítí
- OFDM modulace
- přenosová rychlost dle verze 16 - 150 kbit/s
- vzdálenost 10 - 15 km

![bg right fit](assets/NB-IoT.png)

---

## 3. Síťová
### Sigfox

- globální **uzavřená** síť
- nelicencované pásmo 868 MHz
- *ekonomické problémy*
- omezené množství zpráv
- dosah 25 km

![bg right fit](assets/sigfox)

---

## 3. Síťová
### LoRa a LoRaWAN

- globální **otevřená** síť
- nelicencované pásmo 868 MHz
- LoRa vs. LoRaWAN
- dosah 5 - 10 km

![bg right fit](assets/LoRa)

---
<!-- footer: "" 
paginate: false
backgroundColor: "#FFF"
-->
![bg fit 90%](assets/long-randge-tech.png)

---
<!-- footer: "IoT: Vrstvy" 
paginate: true
backgroundColor: "#000"
-->

## 3. Síťová
### ZigBee

- senzorové, domácí a průmyslové sítě
- vzdálenost 75 m
- nelicencovaná pasmá 868 MHz a 2.4 GHz
- přenosová rychlost 20, 40 250 kbit/s

![bg right fit](assets/ZigBee.jpg)

---
## 3. Síťová
### IEEE 802.11

- specializované módy pro IoT řeší problematiku kolize
- krátký dosah
- energetický náročný
- veliké množství dat

![bg right fit](assets/Wi-Fi)

---
## 3. Síťová
### IEEE 802.15

- bezdrátová náhrada RS-232
- PAN malý dosah *(verze 5.0 více jak 200 m)*
- ve verzi 5.0 až 255 bajtů na jednu zprávu

![bg right fit](assets/bluetooth)

---

## 4. IoT služba
### Informace -> Znalost

![h:370](assets/IoT-as-Service.png)

<!--

Data Extraction
• Zachycení vnitřních / vnějších stavů IoT zařízení a schopnost 
zařízení tato data poskytnout

Data Ingestion
• zahrnuje získávání událostí ze zdrojů a jejich přenos do 
datového úložiště k dalšímu zpracování. Jde o přesun 
nestrukturovaných dat - z místa, kde vznikají, do systému, 
kde mohou být uložena a analyzována. 
• Batch x Stream data
• Přijímání dat může být kontinuální, asynchronní, dávkové, v 
reálném čase nebo jejich kombinace.

Data Storage
• Schopnost databáze přijímat vstupní data, ukládat je a 
následně poskytovat k analýze a vizualizaci
• TSDB x SQL x nonSQL x logging DB x BigData DB x Cloud based
DB

Parse / Transformation
• zahrnuje vytvoření požadované struktury dat, která jsou 
shromažďována ze zařízení IoT. Po této akci jsou výsledná 
data přenesena k dalšímu zpracování nebo uložení.

Data Enrichment
• proces obohacování dat je operace, při níž se data 
shromážděná IoT zařízeními kombinují s dalšími soubory dat 
(informacemi), aby měla výsledná data větší přidanou 
hodnotu.
• Např. do jednoho záznamu o teplotě připojíte informaci o 
vlhkosti apod ➔ větší přidaná hodnota informace

Analyse / Visualisation
• Schopnost nástrojů poskytovat nad uloženými daty analýzu a 
zprostředkovat vizuální zobrazení dat do lidsky čitelné 
podoby

ML / Anomaly Detection / Thresholds
• Kontinuální příchod dat z IoT zařízení umožňuje nad daty 
provádět např. near-realtime detekci událostí – aplikace / 
nástroj

-->

--- 

<!-- 
backgroundColor: #FFF
 -->

![bg fit 80%](assets/IoT-servies.png)

---

![bg fit 70%](assets/M2M.png)

---
<!-- 
backgroundColor: #000
footer: IoT: Trendy
 -->

# Trendy v IoT
## Průmysl 4.0

- analýza, reakce, predikce
- těžba dat
- AI & BigData

![bg right fit](assets/industry-revolutions)

---

# Trendy v IoT
## Digital Twins

- model reálného světa
- Azure Digital Twins
- optimalizace

![bg right fit](assets/digital-twins)

---

# Trendy v IoT
## Bezpečnost

- [nic.cz](https://www.iot-portal.cz/2018/03/02/bezpecnost-a-iot-vzdyt-se-nemuze-nic-stat/)
- aktualizace
- měnit nativní hesla (spotřebiče)
- safe booting

![bg right fit](assets/iot-security)

---

# Azure IoT
## IoT jako platforma

- Azure IoT Hub
- Azure Digital Twins
- Azure IoT Certification

![bg right 40%](assets/iot-hub.svg)

---

# Azure IoT
## Správa IoT Aplikací

- Azure IoT Central
- IoT Central app templates
- Azure IoT Certification

![bg right 40%](assets/iot-central-alt-2.svg)

---

# Azure IoT
## Další služby

- Azure IoT Edge
- Windwos for IoT
- Azure RTOS

![bg right 40%](assets/rtos.svg)

---
# Deep dive

- bastlení
- studium?
- fyzika
- vše pod kontrolou

---
<!-- footer: IoT: Shrnutí -->

**Základní vrstvy**
- fyzikálních dat
- zpracování signálu
- přenos dat
- vizualizace a těžba dat

**Azure IoT**
- Azure IoT Hub
- Azure IoT Central

---

<!-- footer: "" -->

![bg fit](assets/curpauza.png)

---

# Safety platform developement

- motivace
- automotive, railway, aerospace, medical, army, ...
- kolik stojí lidský život?

--- 

# Safety vs Security

- kde je důležitá?
- jak docílit safety?
- SIL, ASIL, ...

---

# Jak na safe-platform
## Co si je třeba hlídat

- systémová chyba - řešení: proces
- náhodná chyba - řešení: systém

---

# Jak na safe-platform
## Vývojový proces

- V-model
- jasně definované role
- analýza hazardu
- testování
- style guide & coding standard

![bg right fit](image-3.png)


---

# Jak na safe-platform
## Architektura

- Reactive safety (watchdog)
- Inherent safety (hardware)
- Composite safety (redudantion)

---

<!-- footer: AI: oblasti -->

# AI

- bayesovské sítě
- fuzzy logika
- evoluční algoritmy
- multiagetní systémy
- strojové učení
- neuronové sítě
- počítačové vidění
- zpracování přirozeného jazyka (NLP)

---

## Bayesovské sítě

- pravděpodobnostní model
- grafová reprezentace
- *teorie pravděpodobnosti*

![bg right:60%](assets/bayesian_network)

---

## Fuzzy logika

- rozdíl od výrokové logiky ($true$/$false$)
  $x \in [0;1]$

- fuzzy logika
  $\forall x \in \mathbb{R}\quad and\quad x \in <0;1>$

- vícehodnotová logika

---

## Evoluční algoritmy

- alogritmy inspirované přírodou, *přirozeným výběrem*
- pro úlohy s časovou náročnostní bez konvenční řešení,
  např.:
  - Lagrangelovy multiplikátory *(extrémy fce)*
  - lineární programování
  - kvadratické programování
$\quad$
- obecně spíše heruistické optimalizační technik
- genetické algoritmy, simulované žihání

---

## Multiagentní systémy

- interakce agentů
- každý má jinou znalost
- společně řeší problém
- robotika, DS, ...

![bg right](assets/multiagent.jpeg)

---

## Strojové učení

- učení
  - s učitlem
  - bez učitele
  - hybrid
  - zpětnovazební (posilování)
- elementární úlohy
  - shlukování (do skupin dle společných vlastností)
  - regrese (predikce výstupu podle vstupu)
  - klasifikace (rozdělování do tříd)
- vektor a matice

---

## Strojové učení
### Lineární regrese

- např. nejmenší čtverce
- v praxi mnohem více dimenzí
- *využití predikce zvuku*

$$
S(a,b) = \sum_{i=1}^{n}[f(x_i)-y_i]^2 = \sum_{i=1}^{n}(ax_i + b - y_i)^2,
$$
kde $[x_i,y_i]$ jsou souřadnice aporximovaných bodů

![bg right fit](assets/lin_regrerse)

---

## Neuronové sítě

- vzorem jsou biologické struktury
- distribuovaný a paralelní systém
- příměr *síla vazby*

![bg right](assets/neuron-network.jpeg)

---

## Počítačové vidění

- opak počítačové grafiky
- typické úlohy
  - poznování objektů
  - indetifikace
  - detekce
  - OCR
- *matice, optimalizace a lingebra*

![bg right](assets/computer-vision.jpeg)

---

## Zpracování přirozeného jazyka
- multidisciplinární obor
- snaha porozumět jazyku strojem
- jazyky, automaty, ...
- dílčí úlohy
  - *korektura textů*
  - extrakce infromací
  - generování přirozeného jazyka
  - atd.

![bg right](assets/NLP.jpeg)

<!-- (lingivistika, matematika, informatika) -->
  <!-- - *korektura textů*
  - extrakce infromací
  - generování přirozeného jazyka
  - rozpoznávání a sytnéza řeči
  - strojový překlad -->

--- 

<!-- footer: AI: Azure & AI -->
<!-- Druha část - Azure a AI služby -->

# Azure a AI

- [Azure Applied AI Services](https://azure.microsoft.com/en-us/products/applied-ai-services/#overview)
- [Azure Cognitive Services](https://azure.microsoft.com/en-us/products/cognitive-services/)
- [Azure Machine Learning](https://azure.microsoft.com/en-us/products/machine-learning/#product-overview)
- [AI infrastructure](https://www.microsoft.com/en-us/research/project/ai-at-scale/)

<!--
Na strankach MSFT o Azure AI, 4 kategorie

Otakzaaa?

- AI infrastructures
  - bezi na FPGAckach, kteras se prizpusobuji potrebam vypoctu

-->

---

# Azure Applied AI Services

![bg cover](assets/11.png)

<!--
Azure Applied AI Services (aplikovane sluzby) 
  - Bot Services
  - Form Recognizer
  - Cognitive Search (AI cloud search)
  - Metrics Advisor (sledovani metrik a analyza incidentu)
  - Video Indexor (extrakce vyznamu z audia nebo videoa)
  - Immersive Reader

-->

---

## Azure Cognitive Services

- speech
- language
- vision
- decision
- OpenAI

![bg right:60% cover](assets/12.png)



<!--

DALL-E input: digital art Congitive Services 

Azure Cognitive Services (jake mame smysly, ne doslova)
  - Speech (speech2text, text2speech, speech transaltion, speaker recognition)
  - Language (entity recognition, question answeing, translator, ...)
  - Vision (computer, custom fision, face API)
  - decision (anomaly detector, content moderator, personalizer)
  - Azure openAI Serivces (vyuziti jiz existujicich opensource modelu jako DALL-E 2, GPT-3, ...)
-->

---

## Azure Machine Learning

### Příprava dat

![bg fit](assets/prepare-data.png)

<!-- 
Azure Machine Learning
  - spracovani datasetu (oznaceni, uprava, kompletovani)
  - civceni a buildeni modelu
    - CLI, Python SDK
    - Notebooks
    - Automated
    - VS Code supports
    - Drag-and/Drop designer
    - Fraimeworks (TenserFlow, PyTorch, ...)
  - deploying a nasazeni do provozu
    - CI/CD pipelines
    - AI endpoins
    - optimalization
    - hybrid and multicloud
    - mode repository
    - prebuilt images
  - monitorovani a sprava
    - policies
    - security
    - error analytics
    - audits
-->
---
## Azure Machine Learning

### Trénování modelu

![bg fit](assets/build-and-train.png)

<!-- 
Azure Machine Learning
  - spracovani datasetu (oznaceni, uprava, kompletovani)
  - civceni a buildeni modelu
    - CLI, Python SDK
    - Notebooks
    - Automated
    - VS Code supports
    - Drag-and/Drop designer
    - Fraimeworks (TenserFlow, PyTorch, ...)
  - deploying a nasazeni do provozu
    - CI/CD pipelines
    - AI endpoins
    - optimalization
    - hybrid and multicloud
    - mode repository
    - prebuilt images
  - monitorovani a sprava
    - policies
    - security
    - error analytics
    - audits
-->
---
## Azure Machine Learning

### Validování a nasazení

![bg fit](assets/validate-and-deploy.png)

<!-- 
Azure Machine Learning
  - spracovani datasetu (oznaceni, uprava, kompletovani)
  - civceni a buildeni modelu
    - CLI, Python SDK
    - Notebooks
    - Automated
    - VS Code supports
    - Drag-and/Drop designer
    - Fraimeworks (TenserFlow, PyTorch, ...)
  - deploying a nasazeni do provozu
    - CI/CD pipelines
    - AI endpoins
    - optimalization
    - hybrid and multicloud
    - mode repository
    - prebuilt images
  - monitorovani a sprava
    - policies
    - security
    - error analytics
    - audits
-->
---
## Azure Machine Learning

### Monitorování a správa

![bg fit](assets/manage-and-monitor.png)

<!-- 
Azure Machine Learning
  - spracovani datasetu (oznaceni, uprava, kompletovani)
  - civceni a buildeni modelu
    - CLI, Python SDK
    - Notebooks
    - Automated
    - VS Code supports
    - Drag-and/Drop designer
    - Fraimeworks (TenserFlow, PyTorch, ...)
  - deploying a nasazeni do provozu
    - CI/CD pipelines
    - AI endpoins
    - optimalization
    - hybrid and multicloud
    - mode repository
    - prebuilt images
  - monitorovani a sprava
    - policies
    - security
    - error analytics
    - audits
-->

---

# Otázky a výzvy

- **etika v účení a používání AI**
- problematika výpočetní síly, *edge computing*
- **datasety pro učení**
- **legislativa a autorská práva**
- transformace pracovních pozic

<!-- 

OTÁZKY A VÝZVY, KTERÉ STOJÍ PŘED NÁMI

- O čem nevíme? Válka přispívá rozvoji, co přinese konflikt na ukrajině?
- Problematika výpočetního výkonu - edge computing
- Problematika data pro učení
- Problematika legislativy - nová osoba v EU
- Transformace pracovních pozic 
 
-->

---
<!-- footer: "" -->

![bg](assets/OIG.jpeg)

---
$\quad$
$\quad$
$\quad$
$\quad$
$\quad$$\quad$
$\quad$
$\quad$
$\quad$
$\quad$
# Chci feedback!
**A pojďme diskutovat**
![bg right:45%](assets/feedback.png)

