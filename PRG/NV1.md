# Návrhové vzory I

`Návrhové vzory pro vytváření instancí, rozšiřování funkcionality`

- programátorský ekvivalent matematických vzorečků
- popisují řešení problémů při vývoji softwaru
- nízká chybovost díky ověřené funkčnosti
- rychlejší a kvalitnější návrh

- **Vzory chování**
  - mění nebo vytváří chování objektů
  - MVC, interpreter, observer, iterátor
- **Strukturální vzory**
  - řeší strukturu systému a jeho komponent
  - zástupce, adaptér, prázdný a neměnný objekt
- **Vzory pro vytváření**
  - řeší problémy v souvislosti s tvorbou objektů
  - singleton, pool, knihovna, tovární metoda

## Creational patterns

### Singleton

- **maximálně jedna instance dané třídy**
  - tato instance by měla být centralizovaně dostupná
- nesmí být umožněno vytvářet instance mimo samotný singleton

```CSharp
    private static Predskolak instance { get; set; }
    private Predskolak(int age, int gender, string name) : base(age, gender, name)
    {
        //dědíme od Osoba
    }
    public static Predskolak getInstance(int age, int g, string n)
    {
        if (instance == null) //oveříme zda je instance prázná
        {
            instance = new Predskolak(age, g, n); //pokud ano tak vytvoříme instanci
        }
        return instance; //jinak vrátíme už existující instanci
    }
```

### Factory method

- definuje statickou metodu, která nahrazuje konstruktor
- vytvoření nové instance třídy na základě parametrů
- využití, kde jsou vytvářené objekty odvozeny od stejné třídy
- **podle vstupních parametrů se rozhoduje jaká instance se vytvoří**

```CSharp
    static public Osoba GetInstance(int age, int g, string n)
    { //podle vstupních parametrů se rozhoduje jaká instance se vytvoří
        if(age < 0)
        {
            return null;
        }
        else if(age > 0 && age <= 7)
        {
            return Predskolak.getInstance(age, g, n);
        }
        else if (age >= 8 && age <= 19)
        {
            return Skolak.getInstance(age, g, n);
        }
        else if (age >= 20 && age <= 65)
        {
            return Pracujici.getInstance(age, g, n);
        }
        else
        {
            return new Duchodce(age, g, n);
        }
    }
```

### Pool

- umožňuje znovu použít existující instance třídy
- řešení paměťově náročných tříd nebo tříd s velkým množstvím instancí
- implementace pomocí kolekce, která bude obsahovat všechny instance
- př: projektily ve hře (**místo abych je ničil a znovu vytvářel, tak je dám do listu odkud je budu moci znovu využít**)

### Utility

- **knihovna**
- skupina metod, které spolu nějak souvisí
- třída by neměla být schopna dědit a vytvářet instance (static)
- zlepšuje přehlednost kódu a jeho znovupoužitelnost
- **prostě je to jako knihovna v C**

## Stractural patterns

### Flyweight

- sdílení prostředků mezi více instancí
- nahrazuje vytváření prostředků pro každou instanci zvlášť
- př: **vystřelené kulky ve hře (Každá potřebuje znát pozici, ale všechny používají stejný sprite, zvuky)**

<image src="./images/flyweight.png">

### Imutable

- hodnotový objekt, u kterého nejde změnit hodnota
- zvyšuje bezpečnost programu

### Crate

- podobné Immutable objektu
- předávání několika samostatných informací
- atributy jsou readonly, aby byla zajištěna neměnnost
- př: **souřadnice; všechna data (x, y, z) jsou uložena v přepravce**

## Behavioral patterns

### servant (služebník)

- **třída ovládá jinou třídu nebo skupinu tříd**
- potřebné objekty se služebníkovi předávají jako parametry

```CSharp
    internal class Ovladac
    {
        public Ovladac()
        {
        }
        public string PosliPozadavek(Povel p, Robot robot) //ovládá třídu Robot
        {
            return $"Pozadavek [{p.Cinnost}] poslan na [{p.Misto}]. {robot.ProvedPozadavek(p)}";
        }
    }
```

### null object (prázdný objekt)

- použití tam, kde se nehodí čistý null (Např. hází to chyby)
