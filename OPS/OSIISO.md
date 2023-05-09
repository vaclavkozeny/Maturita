# OSI/ISO, síťové prvky

`Protokol, rozhraní, popis a funkce jednotlivých vrstev, PDU, zapouzdřování, porovnání s modelem TCP/IP, průchod dat přes síťové prvky, kategorie přepínačů pro jednotlivé vrstvy,
nástroje pro zachycování dat v síti, testování a oprava problémů v síti
Popis standardního chování opakovače, mostu, přepínače, směrovače, L3 switche, firewalu
`

## Protokol

- sada pravidel

## Rozhraní

- posílá a přijímá data

## PDU

- data
- každá vrstva přidá svou specifickou informaci

## Zapouzdření

- vložení PDU z vyšší vrstvy do těla dat

## Model

- vrstvy spolu komunikují na základě protokolů
- na výrobě se mohou podílet různí výrobci
- změny v jedné vrstvě neovlivní vrstvy další

## OSI/ISO vs TCPIP

<image src="./images/ositcp.jpg">

## OSI/ISO

- standardizace počítačových síťí
- 7 vsrtev
- **nespecifikuje implementaci**, ale uvádí všeobecné principy architektury
- encapsulation / decapsulation

<image src="./images/osihead.png">

### L1

- physical layer
- definuje elektrické a fyzikální vlastnosti
- modulace signálu
- stará se o dráty (i bezdrát)

- **Hub**
  - rozbočovač
  - data rozesílá na všechny svoje porty
  - jednoduchý
- **Repeater**
  - příjímá zkreslený / poškozený signál, opraví ho a posílá dál

### L2

- [více zde](./L1.md)
- link layer
- umožnuje komunikaci v LAN
- uspořádává data do rámců (**frame**)
- **MAC address** (fyzická adresa)
- detekuje a opravuje chyby vzniklé na fyzické vrstvě

- PDU: **frame**

<image src="./images/MACHead.png">

- **Bridge**

- **Switch**
  - posílá podle MAC adresy
  - když nemá adresu v CAM tabulce odešle na všecnhy porty (kromě vstupního portu)
  - **Store and forward**
    - ukládá framy
    - kontroluje CRC
    - pomalejší
    - různé přenosové rychlosti
  - **Cut-throught**
    - data posílá rovnou po přečtení cílové MAC adresy
    - nekontroluje CRC
    - rychlejší

### L3

- network layer
- protokoly pro směrování dat
- volí nejlepší cestu
- Media independent
- **IP adresy**

- PDU: **packet**

<image src="./images/iphead.png">

- **Router**
  - routovací tabulka
  - nezníme packety zahazuje
  - posílá packety do cílových síťí
  - výběr nejlepší cesty
- **L3 switch**
  - umí vše co L2 + router
  - routuje VLAN
  - rychlejší než router

### L4

- přídává **čísla portu** a protokol **TCP** / **UDP**
- stará se o
- umí segmentovat data
- dostane data od relační vrstvy, rozdělí ji na menší části - segmenty (?) a předá vrstvě L3
- segmentace, zpětné složení dat, číslování segmentů, multiplex segmentů
- PDU: **segment**

<image src="./images/l4head.png">

### L5

- session layer
- spravuje komunikaci mezi dvěma aplikacemi¨
- Zakládá a udržuje relaci (session) mezi aplikacemi
- synchronizace dat
- NetBIOS

### L6

- Presentation layer
- kóduje, komprimuje, šifruje, hashuje

### L7

- vrstvu představují konkrétní aplikace
- [více zde](./L7.md)
