# Strukturové datové typy

- Objekty skládající se z několika komponent (členů)
- Používá se pro uložení více spolu souvisejících prvků, které mohou být různého typu (na rozdíl od pole)
- 2 druhy
  - **Homogenní** – komponenty jsou stejného typu
  - **Heterogenní** – komponenty různého typu

## Struktura

- skupina více proměnných dohromady (mohou mít různé datové typy)
- hodnotový typ
- nepodporuje dedičnost, nemá konstruktor

```Csharp
struct Book{
    public int Id;
    public string Name;
    public string Author;
}
```

## Objekt

- abstraktní datový typ
- všechny .NET funckce jsou jeho následníky
- obsahuje vlastnosti, funkce
- základní stavební kámen OOP
- obsahuje možnost zapouzdření
- existující objekty mohou být v programu uprovovány

## Pole

- Množina proměnných stejného datového typu
- homogenní strukturovaný datový typ
- K jednotlivým proměnným se přistupuje přes index.
- oproti listu má **pevný počet položek**, který **nelze** měnit

```Csharp
int[] pole = new int[50];
pole[0] = 4;
Console.WriteLine($"První položka z pole: {pole[0]}");
```

### Vícerozměrná pole

- jde o pole, ve kterých se nachází další pole
- můžou být N-rozměrná
- nejčastěji jsou ovšem 2D

## Kolekce

- soubor dat
- slouží jako úložiště objektů a zajištění přístupu k nim
- např.
  - list
  - pole
  - seznam
  - Tree
  - Dictionary
  - Stack – LIFO (Last In First Out)
  - Queue – FIFO (First In First Out)

### Generická kolekce

- obecné kolekce
- Datový typ se specifikuje ve chvíli vytvoření instance
- Generický typ slouží jako zástupce pro budoucí datový typ