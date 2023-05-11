# Zabezpečení komunikace, ACL

`Kryptografie symetrická a asymetrická, hashování, certifikáty a certifikační autorita, elektronický podpis, VPN, příklad implementace (SSL)
ACL standardní a rozšířený, jmenný ACL, zabezpečení přístupu k managování switche a routeru,
Vytvoření ACL a nasazení ACL na porty směrovače (filtrace provozu dovnitř a ven – porovnání)`

## Kryptoanalýza

- Zabývá se luštění šifer

## Kryptografie

- Zabývá se tvorbou šifer

## Symetrická

- použit pouze jeden klíč
- rychlá a snadná implementace
- hůře zabezpečené

<image src="./images/sifra.png">

### proudová šifra

- šifrování proudů dat
- bit po bitu
- RC4 - šifrování přenosu webových stránek

### bloková šifra

- šifrování pevně velkých částí dat - bloků (textové soubory)
- RC5

## Asymetrická

- používá dva různé klíče – soukromý a veřejný
- veřejný slouží k šifrování dat, soukromý k dešifrování dat
- vztah mezi klíči je výpočetně velmi náročný
- bezpečnější, hůře prolomitelná
- mnohonásobně pomalejší, nutnost ověření pravosti klíče
- např. RSA

<image src="./images/sifra2.png">

## Hash

- proces = hashování
- pomocí hashovací funkce získává výsledný hash
- použití
  - ověření integrity dat
    - když stahuju soubor tak vím že nemám virus
    - hash je stejný
  - ukládání hesel do databáze
    - není dobrý nápad ukládat hesla jako plain text
    - sůl a pepř
    - přidává se k heslu před hashováním
- Požadavka na HASH
  - Jednoznačnost - pro každý vstup produkuje jedinečný výstup
  - Nepřevoditelnost - není možné získat původní data
  - Rychlost - pro praktické použití musí být funkce rychle výpočetně proveditelná
  - Fixní délka výstupu - pro libovolný vstup má hash stále stejnou délku
  - Unikátnost - malé změny na vstupu způsobují velké změny na výstupu

## Digitální certifikát

- používán v asymetrické kryptografii (HTTPS/VPN)
- **digitálně podepsaný veřejný šifrovací klíč** (soukromým klíčem)
- vytváří ho certifikační autorita
- obsahuje mj. údaje o majiteli/vydavateli, použitý algoritmus, samotný podpis, účel, platnost, …
- **certifikační autorita**
  - vydává za poplatek certifikáty
  - na základě principu přenosu důvěry je možné důvěřovat neznámým certifikátům, které jsou podepsány důvěryhodnou certifikační autoritou
- **self-signed certifikát**
  - certifikát podepsal sám jeho tvůrce, který se tak stává CA

## Elektronický podpis

### Co to je?

- specifický typ podpisu, který je zajištěný digitálním certifikátem
- je kryptograficky svázán s podepsaným dokumentem
- dá se ověřit
- pokud je certifikát vydán důvěryhodnou CA, je podpis prakticky nezfalšovatelný
- k podpisu se používá příslušný soukromý klíč

### Vlastnosti

- Autenticita
  - ověření identity subjektu na základě přenosu důvěry
- Integrita
  - od vytvoření elektronického podpisu nedošlo k žádné změně v podepsaném dokumentu
- Nepopiratelnost
  - autor nemůže tvrdit, že elektronický podpis příslušný k dokumentu nevytvořil
- Časové razítko
  - prokazuje datum a čas podepsání dokumentu, vydává CA
- Schéma

<image src="./images/podpis.png">

### Využití podpisu

- VPN
  - virtuální privátní síť
  - propojení několika počítačů prostřednictvím nedůvěryhodné počítačové sítě
  - extranet = „intranet přes internet“ – tunelování sítě
  - šifrovaná komunikace, totožnost obou stran ověřována pomocí certifikátů
- SSL
  - `Secure Sockets Layer`
  - protokol poskytující zabezpečení komunikace šifrováním a autentizaci komunikujících stran
  - TLS
    - `Transport Layer Security`
    - následník SSL
    - v zásadě stejná funkcionalita
    - bezpečná komunikace s webovými servery pomocí HTTPS
  - využití:
    - online obchody, které přijímají objednávky a údaje platebních karet
    - www portály a projekty s administrací pro zabezpečení hesel a dat
    - komunikace s obchodním partnerem (výměna důvěrných informací)
    - zabezpečení přístupu k poště mimo firemní síť (Exchange, ...)
    - zpracování citlivých osobních údajů
    - dodržení regulačních ustanovení (legislativa), která vyžadují zabezpečené přenosy

## ACL

- `Access control list`
- seznam oprávnění připojený k objektu
- určuje, kdo nebo co má povolení přistupovat k objektu a jaké operace s ním může provádět
- např. Windows → zabezpečení souborů a složek, systém se seznamem probírá postupně
- v oblasti PC sítí
  - standardní ACL filtruje pakety na vrstvě L3
  - forma firewallu na routeru,,
- omezení provozu může zvýšit průchodnost sítě
- zabezpečení přístupu do sítě
- lze filtrovat provoz podle jeho druhu (jen rozšířený ACL)
- umožňuje/zakazuje přístup k síťovým službám (jen rozšířený ACL)

### standardní ACL

- používá čísla 1 - 99 a 1300 - 1999 v rozšířeném módu
- je jednoduchý na konfiguraci
- filtruje (dívá se) pouze podle zdrojové adresy a používá se jako odchozí
- používá se pro blokování provozu blízko cíle

### rozšířený ACL

- používá čísla 100 - 199 a 2000 - 2699 v rozšířeném módu
- dívá se na IP adresu zdroje i cíle
- kontroluje řadu položek v hlavičce vrstvy 3 a 4 (protokol, port apod.)
- může blokovat provoz kdekoliv (nejlépe blízko zdroje)

### jmenný ACL

- můžeme jej použít pro standardní i rozšířený ACL
- umožňuje upravovat či mazat jednotlivá pravidla v ACL
- jména se lépe pamatují
- můžeme použít "neomezený" počet pojmenovaných ACL
- jako jméno můžeme použít i číslo, ale to musí patřit do správného rozsahu

### Nastavení

- výchozí pravidlo, které je implicitně použito na konci ACL → deny any (zakaž všechno všem)
  - 1. necháme deny any a budeme jen povolovat přístup
  - 2. povolíme všechno všem (permit any) a budeme zakazovat
- záleží na aktuální konfiguraci – co je výhodnější
- ACL nastavujeme až nakonec, předtím máme ověřenou funkčnost sítě

- **standardní** – co nejblíže k cíli
- **rozšířený** – co nejblíže ke zdroji, ušetříme provoz
- ACL pro management – připojování přes telnet/ssh
  - nastavíme na VTY
- měli bychom aplikovat pouze jedno ACL, i když se vytváří více spojení pro více uživatelů (protože je nemůžeme rozlišovat - nevíme, přes které se uživatel připojí)
