# TPC a UDP

`Přepínání datagramů vs. přepínání obvodů, TCP komunikace, segmentace, multiplexování segmentů, formát datagramu, řízení toku, omezení režie, navázání a ukončení spojení (tří a čtyřcestný handshake), plovoucí okno.
Porovnání komunikace s použitím TCP a UDP, čísla portů, příklady
`

## TCP

- `Transmission Control Protocol`
- přenosový protokol
  - vytváří spojení, přes které lze obousměrně přenášet data
- vrstva L4
- data jsou doručena **spolehlivě** a ve **správném pořadí**
- TCP využívá služby protokolu IP, který rozšiřuje o kontrolu dat
- **vyžití**
  - HTTP/S
  - email
  - FTP
  - telnet/SSH

### Výhody

- spolehlivost
- správné pořadí doručení
- data se posílají dokola dokud nejsou všechna potvrzena

### Nevýhody

- blokuje frontu (neposílá další data, než jsou doručena předchozí)
- pomalejší oproti UDP
- hlavička obsahuje velké množství informací
- vetší zátěŽ pro síť

### Segmentace

- TCP dostává data z vyšších vrstev
- rozkouskuje je na menší díly
- přidá k nim TCP hlavičku => tím vzniká **TCP segment**
- následně je segment zapouzdřen do IP datagramu (o vrstvu níž)
- MTU
  - `maximum transmission unit`
  - maximální velikost segmentu
- klient posílá potvrzení zda segment obdržel
- pokud klient nepotvrdí přijatý segment (za určitý čas RTT(`round-trip time`)) je odeslán znovu
- přidává CRC

### Formát datagramu

<image src="./images/tcphead.png">

## Řízení toku

- TCP - protokol s posuvným okénkem
- nesmí dojít k přehlcení příjemce
- příjemce specifikuje, kolik dat dokáže zpracovat

### Navázání a ukončení spojení

#### navázání spojení

- server čeká na žádost od klienta
- three-way handshake, detekce chyb a znovu odesílání poškozených či nedoručených paketů (potvrzení přijatých dat)
- navázání spojení: třícestný handshake
  - klient -> server – příznak SYN, pořadové číslo = x (náhodné), potvrzovací číslo = 0
  - klient <- server – příznak SYN+ACK, číslo sekvence = y (náhodné), potvrzovací číslo = x+1
  - klient -> server – příznak ACK, pořadové číslo = x+1, potvrzovací číslo = y+1

#### ukončení spojení

- čtyřcestný handshake
  - klient odešle na server FIN a ten mu odpoví ACK
  - server odešle klientovi FIN a ten mu odpoví ACK

## UDP

- `User Datagram Protocol`
- PDU: UDP datagram
- obsahuje:
  - zdrojový a cílový port
  - délka, kontrolní součet
  - data
- nezaručuje se vůbec nic
- real-time přenos
- rychlejší
- není spolehlivý
- **využití**
  - real-time aplikace
  - průmyslové sítě
  - VoIP
  - stream
  - online hry

## TCP vs UDP

<image src="./images/tcpprehled.png">

## Porty

- 0 - 1023
  - well known
  - známe aplikace

<image src="./images/porty.png">

- 1024 - 49151

  - registrované

- 49152 - 65535
  - dynamické a soukromé porty
  - volné použití
