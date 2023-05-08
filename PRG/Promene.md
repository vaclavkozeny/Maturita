# Základní programové konstrukce

## Proměná

- místo v paměti
- musí se deklarovat
- Složená z
  - datový typ (int/string/float ...)
  - název
  - hodnota (pouze pokud ji při deklaraci i přizazujeme)

## Datový typ

- **Hodnotové** (přímo proměnná)
  - **čísla** (int, float, double...)
  - **Logické** (bool)
- **Referenční** (odkazují na místo v paměti)
  - **Class**(object, string,...)
  - **Interface**
  - **Array**

## Reference

- Odkaz na proměnnou nebo instanci objektu

```Csharp
public int DivideByTwo(int param)
{
  return param / 2;
}
```

## Hodnota

- Entita programu, se kterou může program pracovat

```Csharp
int num = 0;
```

## Program a podprogram

### Program

- Proces v projektu, který řídí fungování aplikace
- V C# Program.cs

### Podprogram

- Část programu
- Lze ji opakovaně využívat v programu
- Typicky funkce

## Podmínky

- Složený příkaz
- Příkaz se provádí za sebou
- Příkaz úplný podmíněný (2 větve)

### If / else

- Pokud platí podmínka, proveď příkaz
- Jinak proveď příkaz 2

```Csharp
if(value < 0){
    value++;
}
else{
    value--;
}
```

### If

- Příkaz neúplný podmíněný (1 větev)
- Pokud platí podmínka, proveď příkaz

```Csharp
if(value < 0){
    value++;
}
```

### Switch Case

- Více násobné větvení
- Pokud se hodnota rovná x, proveď příkaz 1
- Pokud se rovná y, proveď příkaz 2...

```Csharp
switch(value){
    case 1:
        value++;
        break;
    case 2:
        value--;
        break;
    default:
        break;
}
```

## Cykly

### **While**

- Podmínka na začátku
- Příkaz nemusí proběhnout
- Může běžet do nekonečna

```Csharp
int a = 0;

while(a < 10){
    a++;
}
```

### **Do-while**

- Podmínka na konci
- Vykonej příkaz, opakuj zda platí podmínka
- Příkaz proběhne minimálně 1

```Csharp
int a = 0;

do{
    a++;
} while (a < 10)
```

### **Foreach**

- Iterace prvků kolekce
- Provádí se pro každý prvek přítomný v poli

```Csharp
int[] a = {1,2,3,4,5,6}

foreach(var i in a){
    Console.WriteLine(i);
}
```

## Boxing / Unboxing

### Boxing

- Převod proměnné typu hodnota (int...) na typ reference (objekt)

```Csharp
int a = 20;
Object obj = a; //boxing
```

### Unboxing

- Převod proměnné typu reference (objekt) na typ hodnota (int...)

```Csharp
int b = (int)obj;
```

## Konverze typů

- Převedení jednoho datového typu na jiný
  - Implicitní
    - Přetypování se provede automaticky
    - Operand s nižší prioritou se konvertuje na operand s vyšší prioritou
  - Explicitní (vynucené)
    - Provede se tam, kde implicitní konverze není možná

## Struct

- Datový typ hodnotového typu
- Jedna proměnná obsahující související data různých typů dat

```Csharp
struct Book{
    public int Id;
    public string Name;
    public string Author;
}
```

## Operátory

- Aritmetické
  - \+
  - \-
  - \*
  - /
- Logické
  - && (and)
  - || (or)
  - ! (negace)
- Bitové
  - & (bitový and)
  - | (bitový or)
  - ~ (bitová negace)
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
