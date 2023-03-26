# Mikrokontroléry (mcu) – základní pojmy

`Vysvětlení pojmu mikrokontrolér, harvardská a von Neumannova architektura, hlavní vlastnosti
mikrokontrolérů Atmel AVR, popis blokového schématu`

## MCU

- Microcontroler unit
- **Mikroprocesor**
  - **Řadič**
    - řídí tok dat a instrukcí uvnitř procesoru
    - obsahuje dekodér instrukcí
    - řídí zpracování dat
  - **ALU**
    - provádí výpočty a aritmetické operace
  - **Registry**
    - Dočasné úložište procesoru
  - **Paměť instrukcí**
    - zde jsou uloženy kroky které mají být provedeny
  - **Paměť**
    - zde jsou uložena data se kterými program pracuje

<img src='./images/pc143-1.gif'>

## Von Neumann

- architektura
- zpracování je sekvenční
- paměť programu i instrukcí je spojena
- pouze jedna sběrnice na přenos instrukcí a dat

<img src='./images/neumann.png'>

## Hardvard

- architektura
- paměti jsou odděleny
- každá pamět má svojí sběrnici (lze zasahovat do obou najednou)
- rychlejší a efektivnější zpracování dat

<img src='./images/hardvard.webp'>

## RISC a CISC

- `Reduced Instruction Set Computer`
- `Complex Instruction Set Computer`

<img src='./images/risc.PNG'>

## Atmel AVR

- rodina 8bit kontrolerů
