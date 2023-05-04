# OSI/ISO, síťové prvky

`Protokol, rozhraní, popis a funkce jednotlivých vrstev, PDU, zapouzdřování, porovnání s modelem TCP/IP, průchod dat přes síťové prvky, kategorie přepínačů pro jednotlivé vrstvy,
nástroje pro zachycování dat v síti, testování a oprava problémů v síti
Popis standardního chování opakovače, mostu, přepínače, směrovače, L3 switche, firewalu
`

## Protokol

- sada pravidel

## Model

- vrstvy spolu komunikují na základě protokolů
- na výrobě se mohou podílet různí výrobci
- změny v jedné vrstvě neovlivní vrstvy další

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

- **Hub**
  - rozbočovač
  - data rozesílá na všechny svoje porty
  - jednoduchý
- **Repeater**
  - příjímá zkreslený / poškozený signál, opraví ho a posílá dál

### L2

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
- PDU: **segment**

<image src="./images/l4head.png">
