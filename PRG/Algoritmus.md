# Algorimus, algoritmická složitost

`Algoritmus, algoritmická složitost, rekurze, náhodnost`

## Algoritmus

- je to přesný postup, kterým lze vyřešit určitý problém
- základní pořadavky
  - elementárnost
    - skládá se z konečného počtu jednoduchých a srozumitelných kroků
  - konečnost
    - konečný počet kroků
    - pro každý vstup musí mít konec
  - obecnost
    - neřesí kolik je 3\*7
    - řeší problém **obecně** -> **x\*y**
  - determinovanost
    - ze stejného vstupu generuje vždy stejný výstup
    - pokud nejde o náhodný proces
    - **každý krok algoritmu musí být jednoznačně definován**
  - výstup
    - musí vracet výsledek, jinak je zbytečný

## Algoritmická složitost

- rychlost vzhledem k množině vstupních dat
- dva faktory
  - čas (časová složitost)
  - paměť (paměťová složitost)
- pro označení doby se používá symbol **`O()`**
- **nejhorší případ**
  - ze vstupních dat uvažujeme ta kde je výpočet (časově) nejnáročnější
- **nejlepší případ**
  - opak nejhoršího
- **průměrný případ**
  - průměr ze všech vstupních hodnot

## Rekurze

- rekurzivní algoritmy volají samy sebe
- je paměťově náročná
- rekurze musí být ukončena, jinak dojde k tzv. **zacyklení** - program nepokračuje dál a zasekne se na rekurzi
- **Přímá rekurze**
  - funkce volá přímo sama sebe
- **Nepřímá rekurze**
  - funkce A volá funkci B, ta poté volá funkci A - vzniká kruh
- **Lineární rekurze**
  - funkce volá sama sebe jednou
- **Stromová rekurze**
  - funkce volá sama sebe vícekrát

## Náhodnost

- náhodné algoritmy se snaží nalézt řešení problému náhodným rozhodováním o svém postupu
- je třeba předem myslet na všechny možnosti
- **pravá náhodná čísla**
  - použity fyzikální/hardwarové metody
    - snímky lávové lampy
    - mikroskopické jevy (např. tepelný šum)
- **pseudonáhodná čísla**
  - zdánlivě náhodná čísla, později se sekvence opakují
  - jako základ jsou použity např. hodiny v PC, které měří čas v ms
