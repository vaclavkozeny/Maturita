# 05 - Čítačové podsystémy mcu

`Režim čítače/časovače, podrobný popis pro Atmel AVR. Režimy CAPTURE, COMPARE, PWM.
Dohlížecí časovač WDT`

<a href='https://www.electronicwings.com/avr-atmega/atmega1632-timer'>Dokumentace</a>

- je to register
- přičítá nebo odečítá jedničku
- když přeteče dostanu o tom zmínku

<img src='./images/atmega.png'>

- `TCNTn` -> timer/counter
- `OCRn` -> output compare register
  - snížení maximální hodnoty čítače
  - porovnává se s aktuální hodnotou čítače
  - dostaneme znamení o dosažené hodnotě

<img src='./images/atmega2.png'>

- `count Increment or decrement TCNT0 by 1`
- `direction Selects between increment and decrement`
- `clear Clear TCNT0 (set all bits to zero)`
- `clkT0 Timer/Counter clock`
- `top Signalizes that TCNT0 has reached maximum value`
- `bottom Signalizes that TCNT0 has reached minimum value (zero)`

## Co to je čítač

- počítá pulsy vnějšího signálu
- připojen na externí pin
- třeba tlačítka nebo jiná externí vstupní periferie

<img src = './images/counter.png'>

## Co to je časovač

- počítá pulsy vnitřího signálu
- obvykle clock signál procesoru
- lze generovat přesné časové prodlevy (čeká)

- prescaler zvyšuje 'velikost'
  - dělí puls proto register nepřeteče tak rychle

<img src = './images/timer.png'>

## Capture

- zachycení vnější události
- umožňuje zachytit okamžik, kdy na pinu dojde ke změně úrovně
- zaznamená hodnotu v tomto okamžiku do záchytného registru

<img src='./images/capture.png'>

## Compare

- časovač doplněn komparátorem a porovnávacím registrem
- vyšle signál, když je hodnota v čítači a OCRn stejná

<img src='./images/compare.png'>

## PWM

- pulse width modulation
- slouží pro generování signálu s nastavitelnou střídou
- střída = délka puslu / perioda

<img src='./images/pwm.png'>

<br/>

<img src='./images/pwm2.png'>

## Watch Dog timer

- Na reset je speciální instrukce (WRD)
- monitoruje běh programu
- když SW neresetuje WDT tak WDT resetuje systém
- v případě zaseknutí resetuje mikrokontoler
- pracuje nezávisle na systémovém clock signálu
- má vlastní oscilátor
- také na wake ze sleep modu
