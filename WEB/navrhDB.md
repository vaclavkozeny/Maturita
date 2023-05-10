# Konceptualní návrh databáze

`Entita, relace, entitní typ, klíč, kandidátní klíč, primární klíč, silná a slabá entita, kardinalita a parcialita, agregace, kompozice`

- proces navrhování databáze
- definuje strukturu dat a vztahů mezi nimi​
- cílem je vytvořit logický model databáze
- představuje jaká data budou uložena a jak budou mezi sebou propojena​
- umožňuje lépe pochopit a popsat požadavky na databázi​
- umožňuje lépe vytvořit strukturu, která bude efektivně ukládat a používat data​

## Entita

- jakákoli věc / osoba, která je předmět modelování DB
- Entitní typ
  - tato část specifikuje jaké typy objektů budou v databázi uchovávány​
  - student
- Entita
  - konkrátní pojmenovaná věc/osoba
  - Jan Novák

## Relace

- propojení mezi entitami, které popisují jakým způsobem jsou data v databázi spojena​
- např. třída bude mít více žáků -> vztah mezi třídou a žáky​

## Atribut

- vlastnosti, co definují entitní typ
- např. student – jméno, příjmení, datum narození, třída​

## Primary Key

- unikátní hodnota, která **jednoznačně** identifikuje záznam (řádek) v tabulce ​
- musí mít nenullovou hodnotu​
- většinou se jako primární klíč dává **ID**
- **kandidátní klíč** - způsob identifikace entity

## Foreing key

- primární klíč z **jiné** tabulky realizující nějakou **vazbu**

## Kardinalita

- vyjadřuje, **kolik entit** daného typu se na relaci podílí/může podílet​
  - např. učitel vyučuje více studentů
- 1 : 1 - one-to-one - člověk a jeho židle
- 1 : N - one-to-many - student je ve třídě
- N : M - many-to-many - knihy a jejich autoři

## Parcialita

- vyjadřuje povinnost účasti v relaci
  - 0 - nepovinná účast (**nemandatorní** relace)
  - 1 - povinná účast (**mandatorní** relace)

## Silná entita

- lze ji popsat jen pomocí jejich atributů​
- může existovat i bez vazby se slabou entitou

## Slabá entita

- má povinnou účast ve vazbě​
- **nemůže existovat** bez vazby se **silnou entitou** ​
- klíč nelze vytvořit bez atributů jiné entity (cizích klíčů)

## Agregace

- vztah celek-část
- část **může** existovat i bez celku
- celek není unikátní pro všechny části
  - př.: manželství a muž / žena

## Kompozice

- vztah celek-část
- část **nemůže** existovat bez celku
- mezi silnou a slabou entitou
  - př.: člověk a jeho ruka
