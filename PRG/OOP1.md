# Objektové programování

`Strukturované a objektové programování, objekt, třída, základní objektové vlastnosti, třídy abstraktní, zapouzdřené a rozhraní`

## Strukturované programování

- skoky
- použití funkcí
- vše v jednom souboru
- řídící struktury

## Objektové programování

- použití objektů a tříd
- většinou ve více souborech

## Třída

- vzor, podle kterého se vytváří objekty
- vytvořené objekty se nazývají instance
- třída určuje, jaká se v objektu nacházejí data
- může obsahovat atributy, vlastnosti, konstruktor, metody...
- **this**
  - odkazuje na aktuální instanci třídy

## Objekt

- je instancí třídy
- z jedné třídy se vytvoří několik objektů
- více objektů se stejnou třídou se liší svými atributy (daty)

### Základní objektové vlastnosti

#### Zapouzdření

- umožňuje skrýt určité funkce nebo atributy tak, aby byly přístupné pouze uvnitř objektu
  - typicky modifikátory přístupu private, protected
- umožní použít jen některé metody

```
příklad:
    pro editaci atributu se vytvoří veřejná metoda a atribut se nastaví jako soukromý
```

#### Dědičnost

- umožňuje jednotlivým objektům, aby mohly dědit z jiných objektů
- objekt tím předává své vlastnosti dalšímu objektu (mají je společné)

```
příklad:
    třída člověk (atributy jméno, věk)
    třída dospělý - dědí z člověka (atribut práce)
    třída student - dědí z člověka (atribut škola)
        dospělý a student mají oba společné atributy jméno a věk ze třídy člověk
```

#### Polymorfismus

- umožňuje používat jednotné rozhraní pro práci s různými třídami
- pro každou třídu můžeme definovat různé fungování určité metody, kterou mají společnou

```
příklad:
    více zvířat (objektů), každý má svou vlastní metodu pro mluvení, ale každý mluví jinak
```

## Statická třída

- slovo **static**
- nařizuje všem atributům a metodám, které obsahuje, aby byly statické
- od třídy nelze vytvořit instance - nedávalo by smysl

## Abstraktní třída

- slovo **abstract**
- z této třídy nelze vytvářet instance (objekty)
- její jediné využití je, aby jí dědila jiná třída

## Zapouzdřená třída

- slovo **sealed**
- ze zapouzdřené třídy nelze dále dědit

## Interface / Rozhraní

- rozhraní definuje, jaké má třída obsahovat metody
- třída spojena s tímto rozhraním musí metodu obsahovat
