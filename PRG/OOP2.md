# Objektové programování

`Zapouzdření, dědičnost, polymorfismus, přepsání a překrytí (virtual, override, new), přetížení`

## Dědičnost

- tvorba nových objektů na základě jiných
- dědící třída používá (dědí), rozšiřuje, nebo modifikuje chování rodičovské třídy
- třídy mohou dědit pouze z jednoho předka
- specializace
  - třída Child zvláštním případem objektu Parent
- generalizace
  - třída Parent zobecněním objektu Child

## Zapouzdření

- umožňuje restrikci přístupu dat a metod třídy
- private (přístup mají nested třídy - třída ve třídě) 
- private protected (přístup mají třídy, které dědí a jsou ve stejném sestavení dll) 
- protected (přístup mají třídy, které dědí) 
- internal (přístup mají třídy ve stejném sestavení dll) 
- public (přístup mají všechny třídy) 

## Polymorfismus

- použití metod rodiče jiným způsobem
- umožňuje používat jednotné rozhraní pro práci s různými třídami
- pro každou třídu můžeme definovat různé fungování určité metody, kterou mají společnou

```
příklad:
    více zvířat (objektů), každý má svou vlastní metodu pro mluvení, ale každý mluví jinak
```

### Přepsání (overriding)

- mění chování zděděné metody
- **virtual**
  - deklarujeme metodu, která půjde v děděných třídách přepsat
- **override**
  - deklarujeme metodu, kterou ve zděděné třidě přepisujeme

### Přetížení (overload)

- umožňuje deklarovat více metod se stejných jménem
- tyto metody se od sebe liší parametry (počet, jméno, pořadí)
- program poté podle počtu zadaných parametrů vybere, kterou z deklarací má použít
