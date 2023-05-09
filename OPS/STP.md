# Spolehlivá síť – STP, Etherchannel, FHRP

`Problém vytváření záložních cest, redundandní sítě
Redundance na vrstvě L2, protokol STP (druhy), smyčky, broadcastová bouře, STA, priorita, výpočet
Agregace linky, Etherchannel, protokoly, výhody, konfigurace (switch Cisco)
Virtuální výchozí brána, redundance směrovače, protokoly, nastavení FHRP (router Cisco)
`

## Backup route

- nastavíme statickou route s vyšší prioritou

## STP

- `Spanning Tree Protocol`
- zabraňuje vzniku smyček
- smyčka = broadcast packet dorazí do cíle a znovu vyšle broadcast
- zajištění redundance v případě poruchy
- topologie
- STA (spanning tree algorithm) vybere root bridge (hlavní switch)
- STA určí cesty z ostatních switchů k root bridge (blokuje porty)

- druhy
  - **STP**
  - **RSTP**
    - vylepšené STP
    - rozdíl v ceně cesty
  - **PVSTP**
    - per VLAN
    - lze definovat v každé VLAN

## Etherchanennl

- agregovaná linka
- spojení více fyzických rozhraní do jendoho virtuálního
- zvyšuje propustnost
- nabízí alternativní trasu v případě výpadku jedné z linek
- STP neblokuje ostatní cesty, protože svazek EtherChannel je jeden virtuální port
- load balancing provozu
- druhy
  - `Link Aggregation Control Protocol` (LACP)
    - mód
      - active
      - passive
  - `Port Aggregation Protocol` (PAgP)
    - Cisco proprietální
    - Auto
    - Desirable

<image src="./images/eth.jpeg">

## FHRP

- `First hop redundancy protocol`
- virtuální brána
- když selže brána nemůžeme komunikovat
- proto máme virtuální bránu (více edge routerů) které jsou virtuálně agregované
- druhy
  - **HSRP**
    - `Hot Standby Router Protocol`
    - Cisco proprietální
  - **VRRP**
    - `Virtual Router Redundancy Protocol`
    - standardizovaný
  - **GLBP**
    - `Gateway Load Balancing Protocol`
    - Cisco proprietární
    - umožnuje balancovat provoz mezi oba (více) routerů
    - zvyšuje propustnost
