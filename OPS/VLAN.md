# VLAN, návrh podnikové sítě

`Koncepce VLAN, výhody nasazení VLAN, access VLAN, trunk VLAN, IEEE802.1Q, native VLAN, management VLAN, voice VLAN.
Tři způsoby propojení VLAN, porovnání metod z hlediska efektivity.
Nastavení směrovače pro propojení VLAN (legacy, Router-on-a-Stick)
Nastavení přepínače L3 pro Inter-VLAN, možnost směrování přepínače L3
Návrh podnikové sítě s např. 6 sekcemi – VLAN, podsíťování, propojování VLAN
`

## VLAN

### Koncepce VLAN

- logické rozdělení sítě
- nemění se fyzické umístění stroje
- virtuální skupiny
- obvykle na switchi
  - rozdělen na více VLAN
- lze provádět **interVLAN routing**
- zmenšení broadcostové domény
- izolace uživatelů
- lepší správa a zabezpečení
- priorita určitým datovým tokům

### Access VLAN

- pouze data přizařené VLAN mohou procházet portem

```
SW(config-if)# switchport mode access
SW(config-if)# switchport access vlan 10 //bude pouštět pouze data VLAN 10
```

### Trunk VLAN

- umožnuje přenášet více VLAN jedním kabelem
- umožňuje přenášet data z více VLAN pomocí speciálního protokolu VLAN Tagging
- používá se v případech, když potřebujeme přenášet data mezi switchem a routrem nebo mezi dvěma switche, které mají přiřazené různé VLAN
- data jsou označena (tagged) pomocí příslušného protokolu, jako je například IEEE 802.1Q, což umožňuje rozlišit jednotlivé VLAN v rámci sítě

```
SW(config-if)# switchport mode trunk
SW(config-if)# switchport trunk allowed vlan 10,20,30 //bude pouštět pouze data VLAN 10,20,30
```

#### VTP

- `VLAN Trunking Protocol`
- umožňuje automatizovanou správu VLAN
- switche používají VTP ke sdílení informací o názvu VLAN, čísle VLAN a typu přístupu k VLAN

#### DTP

- `Dynamic Trunking Protocol`
- protokol, který automaticky zjistí, zda je daný port trunk
  - poté vyjedná přepnutí druhé strany do trunk režimu
- doporučeno **nepoužívat** kvůli bezpečnosti

### 802.1Q / dot1Q

- taggovací protokol / encapsulation
  - označí packet a přidá mu infoirmace o jeho VLAN
- informace jako ID VLAN, prioritu provozu, typ protokolu

### Native VLAN

- netaggovaná
- packety bez tagu, co přijdou do trunk portu, jsou přesměrovány na native VLAN
- musí být nastavena shodně na obou stranách komunikace
- útok typu **VLAN hopping**
  - kdy útočník využije nemožnosti tagování dané VLAN a dostane se i do dalších VLAN v síti

### management VLAN / voice VLAN

- oddělují svůj provoz od bežného provozu
- bezpečnejší a kvalitnejší (priorita)
- management
  - switch, router, firewall
- voice
  - telefon

### VLAN routing

#### Legacy

- každá VLAN má svůj vlastní router / port na routeru
- ten je použit jako gateway
- cena roste s každou VLAN

```
# vlan 1
# interface f0/1
# switchport mode acces
# switchport acces vlan 1
```

<image src="./images/inter.jpg">

#### Router on stick

- každá VLAN má svůj subinterface (jeden fyzický interface je rozdělen)
- subinterface je gateway každé VLAN
- router a switch jsou spojeny jedním ethernet kabelem nakonfigurovaným jako trunk
- router musí znát koncept VLAN a IEEE 802.1q standard

```
# vlan 1
# interface f0/1
# switchport mode acces
# switchport acces vlan 1
Nastavení routeru:
# interface g0/0.1
# encapsulation dot1q 1
# ip address {adresa}
```

<image src="./images/ros.png">

#### Multilayer switch

- L3 switch
- pro každou VLAN je vytvořen SVI (switch virtual interface)
- každé SVI má jinou IP adresu a funguje jako default gateway pro svůj VLAN

```
# ip routing
# interface Vlan1
# ip address {adresa}
# interface f0/1
# no switchport
# ip address {adresa}
```

<image src="./images/l3.jpg">
