# Podprogramy

`Podprogramy, funkce, delegáty, lambda operátory`

## Podprogramy

- část programu, kterou lze opakovaně použít
- můžeme k němu přistupovat pomocí identifikátoru
- může obsahovat vstupní parametry
- může vracet hodnotu použitelnou při jeho volání
- zavádíme tím vyšší míru abstrakce

### Syntax

- úroveň přístupu (private, public, protected, internal, file)
- volitelné modifikátory (abstract, sealed, virtual, static, override)
- návratová hodnota (object, void)
- název metody
- parametry metody

```CSharp
public static int Multiply(int x, int y)
{
    return x*y;
}
```

### Volání metody

```CSharp
Console.WriteLine(Multiply(2,8))
```

### Parametry

- podle hodnoty – vytvoří se kopie proměnné v metodě
- podle odkazu – předání přístupu k proměnné metodě

### Předání parametru

```CSharp
void Increment(ref /*reference -> předá přímo hodnotu, nedělá kopii*/ int num)
{
    num++;
}
int number = 5;
Increment(ref number);
Console.WriteLine(number);
```

### Proměnný seznam parametrů

- můžeme definovat parametr **params**, který přijímá proměnlivý počet argumentů
- typ parametru musí být jednorozměrné pole
- po klíčovém slově params nejsou povoleny žádné další parametry

<image src="./images/params.png">

### Parametry vs argumenty

- parametry se definují při deklaraci metody
- argumenty jsou konkrétní hodnoty pro jednotlivé parametry
- název argumentu nemusí být stejný jako název parametru
- datové typy argumentu a parametru ale musí být kompatibilní

```CSharp
int Sum(int x, int y) //x a y jsou parametry
{
    return x+y;
}

int cislo1 = 5, cislo2 = 8;
int sum = Sum(cislo1, cislo2); //cislo1 a cislo2 jsou argumenty
Console.WriteLine(sum);
```

### Pojmenované argumenty

<image src="./images/named.png">

### Volitelné argumenty

- v deklaraci mají 'defaul' hodnotu

### Return

```CSharp
return {návratová hodnota};
return; //když je návratový typ void
```

## Delegáty

- jsou podobné ukazatelům funkcí v jazyce C++
- umožňují předávání metod jako parametrů
- lze použít pro definování metod zpětného volání (callback)
- delegáty lze zřetězit

## Anonimní funkce

- anonymní funkce je blok kódu, který oproti funkci nemá identifikátor
- obvykle se používá pro předávání do jiných funkcí
- někdy se jí také říká arrow function

```
() => {}
```

### Lambda operátor

- anonymní delegát
- jako tělo můžou mít výraz nebo blok příkazu, takže lze použít i pro zkrácený zápis metod
- v C# např. **LINQ**

<image src="./images/linq.png">
