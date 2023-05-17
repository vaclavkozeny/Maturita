# Paměti

`Typy pamětí, struktura, základní parametry, optimalizace přístupu do paměti (cache)`

## Paměť

- fyzické zařízení schopné ukládat data a následně s nimi pracovat
- základní parametry:
  - časování (zpoždění mezi operacemi)
  - frakvence (takt paměti, zvyšuje výkon)
  - kapacita (objem dat, se kterými může paměť pracovat)
- **nevolatilní**
  - data jsou zachována i po ztrátě napájení
- **volatilní**
  - data jsou po ztrátě napájení ztracena

<image src="./images/pameti.png">

### Typy

#### ROM

- `Read Only Memory`
- nevolatilní
- obsah je dán při výrobě a nelze ho měnit (pouze pro čtení)

##### PROM

- `Programable ROM`
- nemají data z výroby
- data do paměti lze zapsat právě jednou

##### EPROM

- `Erasable PROM`
- stejné jako paměti PROM
- navíc dokáží data smazat pomocí UV zařízení

##### EEPROM

- `Eletrically Erasable PROM`
- maže data pomocí napětí

##### FLASH

- paměť dělená v buňkách
- oproti EEPROM se nemusí přepisovat celá paměť
- např. SD karty, USB flash disky, SSD

#### RAM

- `Random Access Memory`
- volatilní
- elektronicky přepisovatelná
- téměř okamžitý přístup k datům
- **operační paměť v PC**
- téměř neomezený počet přepisů

- SPD
  - `Serial Presence Detect`
  - čip, na kterém je uložena konfigurace RAM

##### SRAM

- `Static RAM`
- každá paměťová buňka obsahuje několik tranzistorů, které uchovávají data
- paměť je rychlá, ale drahá
- používá se v CPU cache

##### DRAM

- `Dynamic RAM`
- každá paměťová buňka obsahuje tranzistor a kondenzátor
- pro uchovávání dat je nutno periodicky obnovovat paměť a data znovu zapisovat
- paměť je pomalá, ale levná

##### SDRAM

- `Synchronous Dynamic RAM`
- operace synchroně s clock procesoru
- snižuje se čekací doba
- zvyšuje se výkon
- reaguje na náběžnou hranu

###### DDR

- `Double Data Rate`
- reaguje jak na náběžnou, tak sestupnou hranu

## Cache

- mezipaměť
- malá, rychlá paměť
- urychlení přístupu k často používaným datům
- oproti bufferu může cache data poskytovat opakovaně

<image src="./images/cache.webp">
