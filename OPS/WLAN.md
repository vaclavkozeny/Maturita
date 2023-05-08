# Sítě standardu IEEE 802.11

`Přenosová trasa, přístup k médiu, IEEE 802.11a/b/g/n/ac/ad/ax WiFi x, 
AFHSS, DSSS, OFDM, QAM, MIMO, šířka pásma, kanály, přenosová rychlost,
Beamforming, RU, BSS Coloring, TWT, MU-MIMO, OFDMA
Ad-hoc, Wi-Fi Direct, infrastrukturní sítě, BSS, ESD, ESSID, MAC control,
Zabezpečení WLAN - WEP, WPA, WPA2, WPA 3, AAA , EAP, 802.1X, Radius
`

## WLAN

- BSA -> basic set area
- BSS -> basic service set
- SSID
  - service set id
  - jnémo
- BSSID
  - basic service set id
  - MAC adresa AP

<image src="./images/WLAN.png">

- ESSID
  - extended service set id
  - MAC adresa AP
- ESS
  - extended service set
  - více AP se stejným SSID
  - překrývají se
- ESA -> extended service area

<image src="./images/WLAN2.jpg">

## 802.11x

| Název    | Označení | Pásmo       | Rychlost | Charakteristika    |
| -------- | -------- | ----------- | -------- | ------------------ |
| 802.11   | a        | 2.4 GHz     | 2 Mbps   |                    |
| 802.11a  | Wifi 2   | 5 GHz       | 54 Mbps  |                    |
| 802.11b  | Wifi 1   | 2.4GHz      | 11 Mbps  |                    |
| 802.11g  | Wifi 3   | 2.4 GHz     | 54 Mbps  |                    |
| 802.11n  | Wifi 4   | 2.4 / 5 GHz | 600 Mbps | MIMO               |
| 802.11ac | Wifi 5   | 5 GHz       | 7 Gbps   | MU-MIMO (downlink) |
| 802.11ax | Wifi 6   | 2.4 / 5 GHz | 10 Gbps  | MU-MIMO (down/up)  |

## FHSS

- `Frequency Hopping Spread Spectrum`
- spektum je rozděleno na kanály mezi kterými je přeskakováno

<image src="./images/FHSS.jpg">

## DSSS

- `Direct-sequence spread spectrum`
- rezdělíme jednotlivé bity na více signálů

<image src = "./images/DSSS.jpg">

## OFDM

- `Orthogonal frequency-division multiplexing`
- data vyšleme více nosnými vlnami
- proti **vrchlu** jedné vlny je **minimum** jiné vlny => **nedochází k rušení**

<image src="./images/OFDM.png">

## OFDMA a RU

- `Orthogonal frequency-division multiple access`
- podobný jako OFDM
- každá subnosná může nést data jinému uživateli = **Recource Unit**

<image src="./images/OFDMA.png">

## QAM

- `Quadrature amplitude modulation`
- při použití QAM se digitální signál nejprve rozdělí na dvě části
  - in-phase (I)
  - quadrature (Q)
- poté jsou tyto dvě části modulovány různými **amplitudami** a **fázemi** signálu nosné vlny
- přenso více bitů najednou

<image src="./images/qam.png" >

## MIMO

- `Multiple Input Multiple Output`
- umožňuje současnou komunikaci jednomu zařízení přes více antén
- vyšší přenosová rychlost

## MU-MIMO

- `Multi-User Multiple Input Multiple Output`
- umožňuje přenos dat současně na více zařízení
- vyšší propustnost vytížených sítí

## Beamforming

- beamforming využívá signálů z více antén, které jsou vzájemně synchronizovány tak, aby se jejich signály spojily v určitém směru.
- tento proces umožňuje zvýšit sílu signálu v určeném směru a snížit rušení v ostatních směrech

<image src="./images/beam.jpg">

## BSS coloring

- každé AP svůj signál 'obarvuje'
- řešení problému interference mezi sousedními sítěmi

## TWT

- `Target wake time`
- hlavně v IoT
- stanice a AP se domluví kdy bude probíhat další vysílání
- stanice se následně odpojí a může přejít do uspornějšího režimu

## Infrastruktura a AD-HOC

- infrastruktura
  - alespoň jedno AP
- AD-HOC
  - zařízení se spojují navzájem
  - Peer-to-peer

## Zabezpečení

- **WEP**
  - `Wired Equivalent Privacy`
  - statické klíče symetrické šifry
  - ručně nastaveny na obou stranách spojení
- **WPA**
  - `Wifi Protected Access`
  - dynamické klíče symetrické šifry
  - **Pre-Shared Key** - obě strany mají stejnou heslovou frázi
  - **RADIUS server** - centralizované zabezepeční z databáze - jménem a heslem
- **WPA2**
  - šifra **AES**
  - protokol pro výměnu klíčů: **4-way handshake**
- **WPA3**
  - Simultaneous Authentication of Equals (**SAE**)
    - poskytuje silnější ochranu proti útokům typu "dictionary" a "brute force"
  - individuální šifrovací klíče pro každé zařízení připojené k síti

## Radius a 802.1X

- enterprise reření
- **AAA server** proti kterému se klienti oveřují
  - obsahuje databázi jmen a hesel
