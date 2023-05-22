# Výběr dat v SQL

`SELECT, projekce, restrikce, podmínky, seskupování, agregace, spojování tabulek`

## SELECT

- pro získání informací z tabulky
- vrací množinu záznamů z jedné / více tabulek
- v příkazu se specifikuje jaké sloupce chceme získat a z kterých tabulek
- příkaz lze omezit pomocí podmínek `WHERE`

```SQL
SELECT jmeno FROM lide​ -- jeden sloupec
SELECT jmeno, prijmeni FROM lide​ -- více sloupců
SELECT * FROM lide​ -- všechny sloupce

-- pojmenované sloupce
SELECT jmeno first_name FROM lide​
SELECT jmeno as first_name FROM lide
```

## Projekce

- určení dat (konkrétních sloupců), které se mají vybírat z databáze

## Restrikce a podmínky

- `WHERE`

  - omezení na určité řádky při výběru dat
  - definice podmínek, které musí být při výběru splněny
    - skládají se z logických výrazů, spojek AND, OR, NOT a závorek

- `LIKE`
  - vyhledá podle zadaného výrazu​
  - % představuje 0, 1, nebo více znaků​
  - \_ představuje 1 znak

```SQL
SELECT jmeno FROM lide WHERE jméno = “Michal“;
SELECT jmeno, prijmeni FROM lide WHERE jmeno LIKE “J%“;
```

## Řazení dat

- `ORDER BY`
  - `ASC` -> vzestupně
  - `DESC` -> sestupně

## Slučování

- `DISTINCT`
  - slučování stejných řádků ve výsledku dotazu​
  - něco jako unikátní atribut

```SQL
SELECT DISTINCT jméno FROM lidé --když t DB bude více Josefů tak vrátí pouze jeden záznam
```

## Agregace

- `GROUP BY`
  - seskupení
  - odstraňuje duplicity
    - když se najdou dva řádky se stejnou určitou hodnotou, SQL na ně kouká jako na jeden
  - typicky použité s agregační funkcí `COUNT`​
- `MIN` - minimum
- `MAX` - maximum
- `AVG` - průměr
- `SUM` - suma
- `COUNT` - počet prvků
- `ROUND` - zaokrouhlení

## Omezení počtu

- `TOP` -> prvních x řádků
- `OFFSET`
- `LIMIT` -> MySQL

## Spojení tabulek

- **JOIN** 
  - tab1 JOIN tab2 USING(klíč) 
  - tab1 JOIN tab2 ON tab1.id = tab2.id 
- **INNER** 
  - data s odpovídajícími klíči na obou stranách 
- **OUTER** 
  - všechny řádky 
  - chybějící data doplněny null 
- **LEFT** 
  - všechny řádky z levé tabulky 
  - prázdná data z pravé tabulky doplněny null 
- **RIGHT** 
  - všechny řádky z pravé tabulky 
  - prázdná data z levé tabulky doplněny null 

```SQL
SELECT tab1.sl1, tab2.sl1 ​
FROM tab1 ​
JOIN tab2 ON tab1.klíč = tab2.klíč ​
WHERE podmínka ORDER BY tab1.sl1​


SELECT tab1.sl1, tab2.sl1 ​
FROM tab1 ​
JOIN tab2 USING (klíč)​
WHERE podmínka ORDER BY tab1.sl1
```
