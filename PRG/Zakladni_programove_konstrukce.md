# [Základní programové konstrukce](<./PDF/MT_01_Princ_Mrnka_Zakladni_Programove_Konstrukce%20(1).pdf)

## Proměná

- místo v paměti
- musí se deklarovat
- Složená z
  - datový typ
  - název
  - hodnota (pouze pokud ji při deklaraci i přizazujeme)

## Datový typ

- Hodnotové (přímo proměnná)•
  - čísla (int, float, double...)
  - Logické (bool)
- Referenční (odkazují na místo v paměti)
  - Class(object, string,...)
  - Interface
  - Array

## Reference

- Odkaz na proměnnou nebo instanci objektu

<img src="./IMG/01/01.PNG" width="300">

## Hodnota

- Entita programu, se kterou může program pracovat

<img src="./IMG/01/02.PNG" width="200">

## Program a podprogram

#### Program

- Proces v projektu, který řídí fungování aplikace
- V C# Program.cs

#### Podprogram

- Část programu
- Lze ji opakovaně využívat v programu
- Typicky funkce

## Podmínky

- Složený příkaz
- Příkaz se provádí za sebou
- Příkaz úplný podmíněný (2 větve)
- If/else–pokud platí podmínka, proveď příkaz; jinak proveď příkaz 2

<img src="./IMG/01/03.PNG" height="200">

- Příkaz neúplný podmíněný (1 větev)
- If–pokud platí podmínka, proveď příkaz

<img src="./IMG/01/04.PNG" width="200">

- Více násobné větvení
- Pokud se hodnota rovná x, proveď příkaz 1; pokud se rovná y, proveď příkaz 2...

<img src="./IMG/01/05.PNG" height="250">

## Cykly

- **While**
  - Podmínka na začátku
  - příkaz nemusí proběhnout, může běžet do nekonečna

<img src="./IMG/01/06.PNG" width="250">

- **Do-while**
  - Podmínka na konci
  - vykonej příkaz, opakuj zda platí podmínka

<img src="./IMG/01/07.PNG" width="250">

- **Foreach**
  - Iterace prvků kolekce
  - provádí se pro každý prvek přítomný v poli

<img src="./IMG/01/10.PNG" width="250">

## Boxing / Unboxing

#### Boxing

- Převod proměnné typu hodnota (int...) na typ reference (objekt)

#### Unboxing

- Převod proměnné typu reference (objekt) na typ hodnota (int...)

<img src="./IMG/01/08.PNG" width="250">

## Konverze typů

- Převedení jednoho datového typu na jiný
  - Implicitní
    - Přetypování se provede automaticky
    - Operand s nižší prioritou se konvertuje na operand s vyšší prioritou
  - Explicitní (vynucené)
    - Provede se tam, kde implicitní konverze není možná

## Struct

- Datový typ hodnotového typu•
- Jedna proměnná obsahující související data různých typů dat

<img src="./IMG/01/09.PNG" width="250">

## Operátory

- Aritmetické
  - \+
  - \-
  - \*
  - /
- Logické
  - &&
  - ||
  - !
- Bitové
  - &
  - |
  - ~
- Relační
  - <
  - \>
  - ==
- Přístupové
  - []
  - \.
  - ()
- Ostatní
  - =
  - =>
