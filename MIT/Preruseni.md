# Přerušovací podsystém mcu

`Přerušení, obsluha, vektor, povolení, příznak, priorita, kontext, zpracování, přerušovací systém
Atmel AVR`

https://docs.google.com/document/d/1ArHcuaoh3mnlHWGmcuHV1eEjppzmmxIWrL955c7_I3Y/edit#heading=h.qv6q645jm894

## Přerušení

- reaguje na určitou událost
- signály
- vyvolány hardwarovými nebo softwarovými událostmi
- **Hardwarové**
  - **externí**: změna hodnoty IO pinu
  - **interní**: přetečení čítače
- **Softwarové**
  - neplatná adresa
  - neplatný operační znak
- dočasné pozastavení běhu programu
- spuštění přerušení obslužné rutiny (**obsluha**)

## Obsluha

- kód
- spouští se při přerušení
- obslužná rutina musí být rychlá a efektivní

## Vektor

- adresa v paměti programu
- nachází se zde obslužné rutiny pro přerušení (asi její adresa)
- umístěn na začátek paměti FLASH
- **General Interrupt Control Register**
  - 1 bit ovládá umístění (INPUT VECTOR SELECT | **IVSEL**)
    - 0 -> Začátek FLASH
    - 1 -> Začátek BOOTLOADERU
  - 0 bit (INPUT VECTOR CHANGE ENABLE | **IVCE**)
    - IVCE bit must be written to logic one to enable change of the IVSEL bit

#### Příklady

- RESET
- External interrupt 7 - 0
- Timer
  - Compare
  - Capture
  - Overflow

## Příznak

- **oznámení události**
- můzu si ho přečíst
- když je povoleno přerušení -> spouští se obsluha

## Povolení

- povolujeme "obsluhu" přerušení
- po resetu jsou všechny defaultně zakázané

<hr/>

- Interrupt lze povolit v **SREG** (Status register)
  - 7 bit
  - I (interrupt)
- používá se když nějaké přerušní obsluhujeme aby se nemohlo skočit na další
- na začátku obsluhy ho nastavíme na 0 a na konci zpět na 1

<img src='./images/sreg.PNG'>
<hr/>

- Také lze povolit external interrupt
- **EIMSK** (External Interrupt Mask Register)
  - External interrupt mask register
  - povoluje jednotlivé externí přerušení
  - každé má jeden bit a jeden vector

<img src='./images/eimsk.PNG'>

## Priorita

- jaké přerušení má být obslouženo dříve
- u **ATmega64**
  - pořadí interrupt vektorů v paměti určuje prioritu
  - **adresa vektoru = priorita**

## Kontext

- jaký je aktuální svav procesoru (stack, registry)
- uloženy před spuštením obsluhy
  - do paměti
  - u **ATmega64** do stacku
- po dokončení obsluhy jsou proměnné obnoveny z paměti
