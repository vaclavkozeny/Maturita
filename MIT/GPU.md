# Grafické karty

`Struktura, základní parametry, akcelerace, vytváření 3D scény, použití pro negrafické výpočty`

- jedna ze základních komponent počítače
- zajišťuje grafický výstup na zobrazovací jednotku
- integovaná
- dedikovaná
- GPU (Graphics Processing Unit)
  - provádí grafické výpočty
  - přizpůsoben pro rychlou práci s videopamětí
  - oproti CPU více jader a ALU

## Struktura

- GPU
  - `Graphics Processing Unit`
  - grafický čip
  - stará se o výpočty a vykreslování dat
- paměť
  - ukládání dat používaných pro výpočty
- jako systémová sběrnice se většinou používá PCI / PCI-e
  - `Peripheral Component Interconnect (Express)`
- unifikované shadery
  - výpočetní jednotky, které umožňují programovatelný a flexibilní proces vykreslování grafiky
- TMU
  - `Texture mapping unit`
  - bere informace o texturách a aplikuje je na 3D modely během procesu vykreslování
- ROP
  - `Render output unit`
  - převod výstupu grafické pipeline do formátu, který lze zobrazit na obrazovce
-

## Parametry

- počet execution units
- velikost grafické paměti
- typ grafického čipu
- obnovovací frekvence jádra
- spotřeba
- výkon

## Vytváření 3D scény

- potřeba nejdříve vytvoření 3D modelů
  - tisíce geometrických ploch (polygony)
- na polygony naneseny textury a shadery
- rasterizace přes geometrickou pipeline a zobrazení na monitoru
- při zjištění uživatelského vstupu se celá scéna překreslí znovu
- raytracing
  - po dopadu paprsku na objekt se odrazí a je zaznamenávána jeho další činnost

## Negrafické účely

- stovky až tisíce jader => rozsáhlé možnost pro paralelizaci(pipelining)
- mnohem rychleji řeší složité matematické problémy
- lepší poměr výkon / watt
- vědecké účely
- machine learning
- prolamování hesel
- crypto
