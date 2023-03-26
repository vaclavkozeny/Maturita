# IEEE 802.11

## Kanály

- rozdělení pásma na menší kousky
- 2.4 GHz (13 kanálů)

## Šířka pásma

## Beamforming

- formování paprsku
- směřuje signál k jednomu cíli

## BSS coloring

- obarvuje svůj signál
- snižuje rušení
- každý stroj přijímá jen svůj signál

## AFHSS

- adaptive frequency hopping spread spectrum
- minimalizace rušení bezdrátové komunikace

## DSSS

- Direct sequence spread spectrum
- zvyšuje spolehlivost přenosu
- rozprostírá signál
- možnost posílat signály blízsko sebe

## OFDM

- orthogonal frequency division multiplex
- dělí signál na více subnosných
- proti vrcholu jedné vlny je minimum druhé vlny
- snižuje se rušení

## QAM

- přenos více bitů v jeden časový okamžik
- 16b, 64b atd...

## MIMO

- Single user, Multiple user
- současná komunikace přes více antén
- SU: pro jedno zařízení
- MU: více zařízení
- vyšší efektivita a rychlost

## TWT

- AP a zarízení se domluví na dalším spopjení
- zařízení se může vypnout (úsporný režim)

## AD-HOC

- síť mezi zařízeními (telefon telefon)
- nově Wifi Direct

## Infrastruktura

- sítě kde je AP
- BSS (basic service set)
- jedno AP (kolem něj ne BSA (basic set area))
- SSID identifikuje síť (název)
<hr>

- ESS (extanded service set)
- více AP (stejné SSID)
- přelínání BSA AP

## Zabezpečení

- EAP (extanded authentication protocol)
- 802.1x (radius server)
- MAC control (řízení přístupu(zařázení nově mění MAC adresy))
- WEP (wired equvivalent privacy)
  - statické klíče
- WPA (wifi protected access)
  - dynamické klíče
  - preshared key (na jeho základě se vytváří klíče)
  - PSK -> pro všechna zařízení stejný preshared key
  - enterprice -> využívá RADIUS
- WPA 2
  - využívá AES (advanced encryption standard) -> symetrická šifra
- WPA 3
  - SAE
  - dragonfly (Defie-Helmann)
