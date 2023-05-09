# Základní deska

`Základní deska (čipová sada, bios), interní sběrnice (PCI, PCIe), externí sběrnice (usb, firewire)`

- srdce počítače
- spojuje komponenty dohromady
- napájí komponenty

<image src="./images/mb.PNG">

## Zadní panel

- externí konektory
- USB, USC-C, Ethernet, Audio, DisplayPort, HDMI, PS/2
  <image src="./images/backpanel.jpg">

## Napájení

- ATX 8pin
  - může být více i méně
  - napájení CPU
- ATX 24pin
  - napájení MB
  - skoro vždy

## CPU socket

- patice na procesor
- **PGA**
  - piny na CPU
  - AMD
  - při neopatrném sundání chladiče lze vytáhnout CPU
- **LGA**
  - piny v socketu
  - bezpečnejší

## Super IO kontrolér

- slouží pro komunikaci se staršími rozhraními
- floppy disk, paralelní porty, PS/2

## Napájecí kaskáda

- slouží k dodání stabilního napětí do procesoru
- okolo CPU socketu

## DIMM sloty

- sloty pro pamět RAM
- v dnešní době 2 / 4 u consumer MB

## Chipset

- starý
  - severní můstk
    - rychlé komponenty
    - CPU, RAM, PCIe
  - jižní můstek
    - pomalejší komponenty
    - PCI, USB, SATA, **BIOS**
  - spojení severního a jižního můstku pomocí DMI (Direct Media Interface) nebo PCIe
- nový
  - funkce severního můstku jsou integrované v CPU
  - Čipset má funkce jižního můstku, může ale pracovat i s rychlejšími sběrnicemi

## BIOS / UEFI

- BIOS
  - `Basic input output system`
  - starší
- UEFI
  - `Unified Extensible Firmware Interface`
  - novejší
  - grafický
- firmware vestavěný na základní desce
- inicializuje hardware po spuštění počítače
- jeho obsah je uložen na nevolatilním čipu

## CMOS

- nastavení uživatele v BIOSujsou uložena na CMOS čipu
- volatilní pamět
- po odstranění baterie se odstarní jeho obsah

## Interní sběrnice

- SATA
  - pro připojení disků
- USB
  - vývody do předního panelu
- PCI
  - předchůdce PCIe
  - bitová šířka 32/64 bitů, taktovací frekvence 33, 66 nebo 133 MHz
  - rychlosti od 132 MB/sdo 1066 MB/s
  - sdílená sběrnice – komunikace mezi zařízeními připojenými ke sběrnici
  - bus mastering – přístup k ostatním zařízením nezávisle na procesoru
- PCIe

  - full-duplex sériová linka
  - přenos dat na základě paketů, maximální velikost 128B
  - bitová šířka 1 – 16 bit, závisí na počtu linek
  - stromová struktura
    - RootComplex – centrální bridgemezi CPU, pamětí a PCIe
    - Endpoint - koncová zařízení
    - Switch – přepíná mezi více linkami

    <image src="./images/pci.PNG">

## Externí rozhraní

- USB
  - `Universal series bus`
  - univerzální rozhraní
  - data i napájení
- Thunderbolt
  - USB-C konektor
  - data, napájení, video
  - možnost řetězení (daisy chain)
  - až 40 Gbps
