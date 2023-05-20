# Zařízení pro ukládání dat

`Pevné disky (HDD/SSD), optická média (CD, DVD, BlueRay), rozhraní PATA, SATA, SCSI, SAS, M.2.`

## HDD

- `Hard Disk Drive`
- ukládání a čtení dat pomocí magnetické indukce
- elektromechanické zařízení pro zápis/čtení dat
- **nevolatilní**
  - nepotřebuje napájení pro uchování dat
- pomalý
- velká kapacita
- může obsahovat vyrovnávací paměť (cache)

### princip

- v HDD se točí několik ploten s magnetickou vrstvou
- řadič řídí elektromagnetické hlavy
- elektromagnetické hlavy mění magnetickou orientaci částic na kotoučích
- vše je v héliu, aby nedošlo k mechanickému poškození

### technologie

- **PMR**
  - `Perpendicular Magnetic Recording`
  - kolmý zápis
- **SMR**
  - `Shingled Magnetic Recording`
  - šindelový zápis
  - stopy se částečně překrývají
- **HAMR**
  - `Heat Assisted Magnetic Recording`
  - tepelně asistovaný magnetický zápis
  - zahřátím se dá zapisovat do menších oblastí
- **MAMR**
  - `Microwave Assisted Magnetic Recording`
  - mikrovlnami asistovaný magnetický zápis

### parametry

- cena
- kapacita
- rychlost čtení / zápisu
- rychlost otáčení
- rozhraní
- cache
- technologie zápisu
- Mean Time Before Failure

### Výhody / nevýhody

- dobrý poměr cena / kapacita
- hrozí mechanické poškození
- nízká rychlost

## SSD

- `Solid State Drive`
- polovodičový disk
- neobsahuje mechanické komponenty, ale integrované obvody
- data jsou v podobě elektrických nábojů na flash paměti
- obsahuje
  - ovladač
  - cache
  - kondenzátory
- **trim**
  - V nečinnosti či mírné zátěži prochází tabulku smazaných dat a dané buňky přepisuje na nuly
- **Wear leveling**
  - Uspořádává data tak, aby cykly zápisu/mazání byly rovnoměrně rozloženy mezi všechny bloky v zařízení

### Princip

- flash paměť ukládá data do polí paměťových buňek
- `SLC, MLC, TLC, QLC, PLC`
  - počet stavů na buňku
  - čím menší tím rychlejší, ale dražší

### Výhody / nevýhody

- rychlejší
- horší poměr cena / kapacita
- menší
- nehrozí mechanické poškození

## Rozhraní

- **SATA**
  - `Serial Advanced Technology Attachment`
  - sériová, obousměrná
  - standard dnešní doby
  - není nutnost rozlišovat Master/Slave
  - podporuje Plug & Play
  - nejvyšší rychlost - 600MB/s (SATA III)
- **PATA**
  - `Parallel Advanced Technology Attachment`
  - též nazývána IDE
  - paralelní
  - už historie
- **SAS**
  - `Serial Attached Small Computer System Interface`
  - sériové
  - náhrada za SCSI pro servery
  - kompatibilní se SATA
  - největší rychlost - 1200MB/s
- **NVMe**
  - `Non-Volatile Memmory Express`
  - připojení pomocí linek PCIe
  - velmi vysoká rychlost (přes 7 GBps)

## Optická média

- zapisují se digitální data optickou cestou
- data jsou uložena v prohlubních (pity)
- prohlubně odrážejí laserové světlo
- při zápisu se vypálí polykarbnoátová vrstva a tím se odhalí prohlubeň
- při čtení laser svítí na prohlubeň a určuje logické 1 a 0 podle toho, zda se světlo odrazí
- **CD**
  - `Compact Disc`
  - původně pro digitální audio
  - 700 MB
- **DVD**
  - `Digital Versatile Disc`
  - kratší vlnová délka oproti CD → větší kapacita
  - 4,7 GB (17 GB oboustranné dvouvrstvé)
- **Blu-ray**
  - modrý laser → větší hustota
  - až 128 GB

## RAID

- `Redundant Array of Independent Disks`
- metoda zabezpečení dat proti selhání pevného disku
- pokud jeden selže, data jsou zachována

- **0**
  - zřetězení
  - prokládání - ukládání dat střídavě
- **1**
  - mirroring - obsah se současně zaznamenává na dva disky

<image src="./images/raid01.png">

- **5**
  - alespoň 3 disky (ochrana proti výpadku 1)
  - s daty se ukládá parita
- **6**
  - alespoň 4 disky (ochrana proti výpadku 2)
  - na každém disku jsou dvě parity

<image src="./images/raid56.png">

- **01**
  - nejdříve střídavě ukládáme na A a B, poté provedeme to samé na C a D
- **10**
  - nejdříve stejná data na A a B, poté střídavě na C a D
