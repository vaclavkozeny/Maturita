# Internet věcí

## IoT

- Internet of Things
- síť propojených objektů, které jsou jednoznačně adresovatelné
- využívají komunikačních protokolů, které umožňují výměnu dat
- cíl IoT je propojení systému dohromady, jejich data se poté dají různě využít
- rozdělen na:
  - **PAN**
    - Personal Area Network
    - osobní elektronika, lokální zařízení
    - Bluetooth
  - **WLAN**
    - chytrá domácnost, firma
    - více zařízení, větší prostor
    - WiFi
  - **LPWAN**
    - majitel zařízení si pouze pronajímá infrastrukturu
      - není provozovatelem
    - LoRaWAN, Sigfox, NB-IoT

## Požadavky na IoT

- sběr dat
- uložení dat
- analýza dat
- sdílení výsledků
- bezpečnost
- zpracování velkých objemů dat

## Spotřebitelský IoT

- zlepšení uživatelského zážitku
- zjednodušení každodenního života
- spotřebitelských zařízení v IoT **není tolik**, jako průmyslových
- **použití:**
  - chytré domácnosti
    - dálkové ovládání spotřebičů, detekce otevření dverí, monitorování elektrické energie

## Průmyslový IoT

- použití chytrých zařízení v průmyslových oblastech
- efektivnější využívání zdrojů
- zvýšení pracovní produktivity
- zvýšení bezpečnosti pracovniků
- předcházení vypadkům systému
- tento segment je **převládající**
- **použití:**
  - průmyslová automatizace
    - automatická diagnostika přístrojů
  - energetický průmysl
    - monitorování spotřeby energie

## Architektura

### Hardware

- fyzické systémy
- generují data
- senzory

### Middleware

- komunikace mezi prvky

### Software

- použit pro **analýzu**, **ukládání**
- cloudové úložiště
- **prezentace výsledků**, zobrazení hodnot

## Sítě typu LPWAN

### LoRaWAN

- využívá rádiovou komunikaci
- pro přenos **menšího** množství informací na **velkou vzdálenost**
- nízká energetická náročnost
- obousměrná komunikace

### Sigfox

- nízká rychlost
- nízká energetická náročnost
- omezení maxima zpráv pro jedno zařízení za den
- hodí se více na jednosměrnou komunikaci
  - obousměrná komunikace je omezená

### NB-IoT

- mobilní operátoři
- náročnější na spotřebu
- nejvyšší rychlost
- zařízení musí obsahovat SIM kartu

### MQTT

- `Message Queue Telemetry Transport`
- typicky používá TCP
- určen pro výměnu dat na vzdálená místa

<image src="./images/mqtt.png">

#### Publisher

- poskytovatel zpráv
- komunikuje s brokerem

#### Broker

- centrální bod komunikace
- navazuje s publisherem a subscriberem komunikaci, vyměňuje mezi nimi data
- **prostředník**
- **komunikuje s publisherem a subscriberem**

#### Subscriber

- příjemce zpráv
- komunikuje s brokerem
- může přijímat data od více publisherů

#### Topic

- téma dané zprávy
- mají stromovou podobu
