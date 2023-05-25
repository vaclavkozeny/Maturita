# Sériová rozhraní MCU

`Popis sériových sběrnic USART, RS422/485, SPI/Microwire, I2C, 1Wire, CAN. Popis sériového portu Atmel AVR`

## RS232

- rychlost: ~100kbps
- vzdálenost: ~100m
- adersace: není / SW
- duplex: full (UART) / half (USART)
- vodiče: 3
- řízení: P2P
- arbitrace: ne
- nemá odolnost proti rušení
- zabezpečení: 1bit
- frame: startBit/data/parita/stopBit

## I2C

- 3,4 Mbps
- ~1m
- 7/10 bit adresa
- halfDuplex
- 2 vodiče + (GND, PWR)
- 0 silnější než 1, 1 se musí odpojit
- MultiMaster
- nená odolnost proti rušení
- startBit/adresa nebo data/ACK/stopBit

## 1Wire

- rychlost: 125kbps
- vzdálenost: ~10m
- 64bit adreas
- halfDuplex
- vodiče: data + GND + (PWR)
- řízení: SingleMaster
- arbitrace: NE
- nemá odolnost proti rušení
- zabezpečení: 8bit CRC
- adresa/příkaz/data, bit orientace
- podporuje zapojení za běhu
- napájení ze sběrnice

## CAN

- ~10Mbps
- ~1km
- adresa: ID zprávy
- halfDuplex
- vodiče: 2/3
- řízení: MultiMaster
- odolnost proti rušení (diff vedení)
- zabezpečení: 16bit CRC
- SOF/ID/RTR/CT/DATA/CRC/ACK/EOF
- **automibily**
